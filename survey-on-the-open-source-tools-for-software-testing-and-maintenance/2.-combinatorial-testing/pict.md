# PICT

{% embed url="https://github.com/microsoft/pict" %}
All code can be found at Microsoft's PICT repository
{% endembed %}

## Description

**Pairwise Independent Combinatorial Testing** (**PICT**) is an open source software tool developed by Microsoft Research for automating the process of combinatorial testing. With PICT, [you can generate tests that are more effective than manually generated tests and in a fraction of the time required by hands-on test case design.](#user-content-fn-1)[^1] It generates a set of test cases that cover all possible combinations of input parameters while keeping the number of test cases relatively small. This is especially useful when dealing with systems with a large number of configuration options

## Setup

PICT can be installed in several forms depending on the machine's operating system. The latest **`pict.exe`** release can be found at [https://github.com/microsoft/pict/releases/](https://github.com/microsoft/pict/releases/).



The repository can also be cloned and built on the command line:

1. Clone the root repository `git clone https://github.com/microsoft/pict.git`
2.  Build PICT on Windows

    a. Open Visual Studio 2022 (or a compatible version).

    b. Open the `pict.sln` solution file located in the PICT repository directory.

    c. Build the solution in Visual Studio.

    d. Alternatively, you can use the provided `_build.cmd` script in the root directory to build both Debug and Release versions from the command line.

    e. To run tests, use the `_test.cmd` script. It requires Perl to run the tests.
3.  Build PICT on Linux or macOS

    a. Navigate to PICT repository directory in command line\
    b. Run the following commands (requires cmake)

<pre class="language-bash" data-full-width="false"><code class="lang-bash">cmake -DCMAKE_BUILD_TYPE=Release -S . -B build
cmake --build build
<strong>pushd build &#x26;&#x26; ctest -v &#x26;&#x26; popd
</strong></code></pre>

## Demo

{% embed url="https://youtu.be/EOES8EjEbFQ" %}

[^1]: [https://github.com/microsoft/pict/tree/main](https://github.com/microsoft/pict/tree/main)
