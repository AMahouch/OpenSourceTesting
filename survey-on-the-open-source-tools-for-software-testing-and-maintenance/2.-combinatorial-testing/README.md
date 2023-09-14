# 2. Combinatorial Testing

## Description

Combinatorial, or t-way combinatorial testing, is a testing technique in which a t-way test set covers all the t-way combinations, instead of all possible combinations. This method of testing is effective and reduces the number of tests needed, reducing effort, time, and cost.

There are several strategies of combination to test multiple parameters, including:

* All combinations coverage
* Each choice coverage
* Pairwise coverage
* T-wise coverage
* Base choice coverage
* Multiple base choices coverage

_Note: pairwise, all combinations, and each choice coverage are all special cases of t-wise coverage._

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Subsumption relationship between different coverage criteria, demonstrating the strength of each method<br><br>(source: Introduction to Software Testing, Ammann &#x26; Offutt)</p></figcaption></figure>

### NIST

Research at the National Institue of Standards and Technology (NIST) confirms that [combinatorial methods can reduce costs for software testing, and have significant applications in software engineering](#user-content-fn-1)[^1]. NIST's research revealed that the majority of software defects and failures can be attributed to the manipulation of just one or two parameters, with progressively fewer arising from the interaction of three or more parameters.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>(source: NIST)<br><a href="https://csrc.nist.gov/CSRC/media/Projects/Automated-Combinatorial-Testing-for-Software/images-media/fault-stats.jpg">https://csrc.nist.gov/CSRC/media/Projects/Automated-Combinatorial-Testing-for-Software/images-media/fault-stats.jpg</a></p></figcaption></figure>

### Pairwise Testing

Pairwise testing is a specific form of combinatorial testing. It focuses on testing combinations of input parameters in pairs, ensuring that **every possible pair of parameter values is tested at least once**.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>A set of pairwise test cases<br><br>(source: Introduction to Software Testing, Ammann &#x26; Offutt)</p></figcaption></figure>

## Tools&#x20;

Microsoft PICT (Pairwise Independent Combinatorial Testing):

{% embed url="https://github.com/microsoft/pict" %}

{% embed url="https://learn.microsoft.com/en-us/windows-hardware/drivers/taef/pict-data-source" %}

[^1]: [https://csrc.nist.gov/Projects/Automated-Combinatorial-Testing-for-Software](https://csrc.nist.gov/Projects/Automated-Combinatorial-Testing-for-Software)
