# 1. Input Space Partitioning

The input space of a program consists of all possible inputs that could be taken by the program. Input space partitioning involves the selection of all possible inputs in the input space such that execution will reveal all the faults of the program. The goal of input space partitioning is to select a set of test cases that will reveal as many faults as possible. ISP is achieved through two approaches, which are often intuitive:

*   **Equivalence partitioning**

    A set of equivalent classes in which all members contribute to fault detection in the same way. Such partitions are usually based on a certain characteristic. A partition must satisfy two properties:

    * Completeness: A partition must cover the entire domain
    * Disjoint: The blocks must not overlap
*   **Boundary-Value Analysis**

    A test selection technique that targets faults in applications at or near the boundaries of equivalence classes.

In addition, ISP can be seen through Input Parameter Modeling, in which testable components, input parameters, and environment configurations are identified and partitioned based on characteristic.&#x20;

* **Interface-Based IPM** uses syntactical interface
* **Functionality-Based IPM** uses semantics

## Tool

Java Code Coverage (JaCoCo):

{% embed url="https://github.com/jacoco/jacoco" %}

{% embed url="https://www.eclemma.org/jacoco/" %}
