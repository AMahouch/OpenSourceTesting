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

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Subsumption relationship between different coverage criteria, demonstrating the strength of each method<br><br>(source: Introduction to Software Testing, Ammann &#x26; Offutt)</p></figcaption></figure>





## Tools&#x20;

Microsoft PICT (Pairwise Independent Combinatorial Testing):

{% embed url="https://github.com/microsoft/pict" %}

{% embed url="https://learn.microsoft.com/en-us/windows-hardware/drivers/taef/pict-data-source" %}
