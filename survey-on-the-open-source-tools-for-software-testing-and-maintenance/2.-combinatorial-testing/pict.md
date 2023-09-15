# PICT

{% embed url="https://github.com/microsoft/pict" %}
All code can be found at Microsoft's PICT repository
{% endembed %}

## Description

**Pairwise Independent Combinatorial Testing** (**PICT**) is an open source software tool developed by Microsoft Research for automating the process of combinatorial testing. With PICT, [you can generate tests that are more effective than manually generated tests and in a fraction of the time required by hands-on test case design.](#user-content-fn-1)[^1] It generates a set of test cases that cover all possible combinations of input parameters while keeping the number of test cases relatively small. This is especially useful when dealing with systems with a large number of configuration options

## Setup

PICT can be installed in several forms depending on the machine's operating system. The latest **`pict.exe`** release can be found at [https://github.com/microsoft/pict/releases/](https://github.com/microsoft/pict/releases/).



The repository can also be cloned and built on the command line:

1. **Clone the root repository**\
   `git clone https://github.com/microsoft/pict.git`
2.  **Build PICT on Windows**

    a. Open Visual Studio 2022 (or a compatible version).

    b. Open the `pict.sln` solution file located in the PICT repository directory.

    c. Build the solution in Visual Studio.

    d. Alternatively, you can use the provided `_build.cmd` script in the root directory to build both Debug and Release versions from the command line.

    e. To run tests, use the `_test.cmd` script. It requires Perl to run the tests.
3.  **Build PICT on Linux or macOS**

    a. Navigate to PICT repository directory in command line\
    b. Run the following commands (requires cmake)

{% code fullWidth="false" %}
```bash
cmake -DCMAKE_BUILD_TYPE=Release -S . -B build
cmake --build build
pushd build && ctest -v && popd
```
{% endcode %}

For simplicity, the demonstration video uses Homebrew for macOS:

```sh
brew install pict
```

### Create input model file

1. In the directory where PICT is located, create a test text file containing parameter names and values. Below is used in the demonstration from Microsoft as an example test suite for partition and volume creation:

{% code title="input.txt" %}
```
Type:          Single, Span, Stripe, Mirror, RAID-5
Size:          10, 100, 500, 1000, 5000, 10000, 40000
Format method: Quick, Slow
File system:   FAT, FAT32, NTFS
Cluster size:  512, 1024, 2048, 4096, 8192, 16384, 32768, 65536
Compression:   On, Off
```
{% endcode %}

2. Add conditionals at bottom of input file. Specific documentation can be found at [http://www.amibugshare.com/pict/help.html#\_Conditional\_Constraints](http://www.amibugshare.com/pict/help.html#\_Conditional\_Constraints)

{% code title="input.txt" %}
```
# ------------------------------------------------------------------------
# File systems have constraints on volume size
# ------------------------------------------------------------------------

IF [FSYSTEM] = "FAT"   THEN [SIZE] <= 4096;
IF [FSYSTEM] = "FAT32" THEN [SIZE] <= 32000;

# ------------------------------------------------------------------------
# Compression can be applied only for volumes
# formatted as NTFS and with cluster size <= 4K
# ------------------------------------------------------------------------

IF [FSYSTEM] in {"FAT", "FAT32"} or 
  ([FSYSTEM] = "NTFS" and
   [CLUSTER] >  4096) THEN [COMPRESSION] = "off:";
```
{% endcode %}

### Run pict command and review generated tests

1. Run pict command on the text file, redirecting the output to a file called `output.txt`:\
   `pict input.txt  > output.txt`
2. View the created tests to see the combinations of parameter values PICT has generated for testing:

```
TYPE	SIZE	FORMAT	FSYSTEM	CLUSTER	COMPRESSION
Single	10	quick	NTFS	2048	off
Mirror	5000	slow	FAT32	16384	off
Span	1000	quick	FAT	16384	off
Stripe	40000	slow	NTFS	32768	off
RAID-5	1000	slow	NTFS	2048	on
RAID-5	5000	quick	FAT32	65536	off
Single	10	slow	FAT	65536	off
Span	10	quick	FAT32	32768	off
Stripe	5000	quick	NTFS	4096	on
Single	40000	quick	NTFS	512	on
Stripe	10	quick	NTFS	1024	on
Mirror	1000	quick	FAT	32768	off
Mirror	40000	quick	NTFS	65536	off
RAID-5	1000	slow	FAT	1024	off
Stripe	5000	slow	NTFS	2048	on
RAID-5	10	slow	FAT32	4096	off
Span	40000	slow	NTFS	4096	on
Mirror	10	slow	NTFS	2048	on
Span	1000	slow	FAT32	2048	off
RAID-5	5000	quick	FAT32	8192	off
RAID-5	10	slow	FAT32	512	off
Stripe	1000	quick	FAT	512	off
Mirror	1000	quick	NTFS	4096	on
Single	5000	quick	NTFS	4096	on
Span	5000	quick	NTFS	1024	on
Stripe	1000	quick	FAT32	65536	off
Stripe	10	slow	NTFS	16384	off
Span	5000	slow	NTFS	512	on
RAID-5	10	quick	FAT	16384	off
Span	10	quick	NTFS	65536	off
Single	1000	slow	FAT32	8192	off
Single	1000	slow	FAT	32768	off
Stripe	10	slow	FAT	8192	off
Single	40000	slow	NTFS	16384	off
Mirror	40000	slow	NTFS	1024	on
RAID-5	40000	quick	NTFS	32768	off
Span	40000	quick	NTFS	8192	off
Mirror	40000	slow	NTFS	8192	off
Single	10	quick	FAT	2048	off
Mirror	40000	quick	NTFS	2048	off
RAID-5	1000	slow	FAT	4096	off
Single	1000	slow	NTFS	1024	on
Stripe	5000	quick	NTFS	32768	off
Mirror	1000	quick	FAT	512	off
Stripe	1000	quick	FAT32	1024	off
```



## Demo

{% embed url="https://youtu.be/EOES8EjEbFQ" %}

[^1]: [https://github.com/microsoft/pict/tree/main](https://github.com/microsoft/pict/tree/main)
