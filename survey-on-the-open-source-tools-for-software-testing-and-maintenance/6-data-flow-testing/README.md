# 6. Data Flow Testing

## Description

#### Definition/Use

* a definition is a location where a value for a variable is stored into memory
* a use is a location where a variable's value is accessed

#### Data Flow Graph (DFG)

A data flow graph captures the flow of data in a program. It is fundamentally built upon Control Flow Graph (CFG), with each node annotated with either

* def(n) : set of variables defined in node n
* use(n): the set of variables used in node n



The images below show pseudocode for a simple program, as well as a chart with its associated blocks/nodes.  &#x20;

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>(source: CSE 4321, Jeff Lei, UTA)</p></figcaption></figure>

This data flow graph corresponds to the above code and blocks, displaying the nodes that define and/or use the variables x, y, and z.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption><p>(source: CSE 4321, Jeff Lei, UTA)</p></figcaption></figure>

#### DU Pair/Path

* A du-pair is a pair of locations (i, j) such that a variable is defined in i and used in j
* A du-path is a simple path from a definition to a use for a variable, with no redefinition within the path (def-clear)

<table><thead><tr><th>Coverage</th><th data-hidden>Requirements</th><th data-hidden></th></tr></thead><tbody><tr><td>All-Defs Coverage</td><td>For each def, we need to tour at least one path for at least one use</td><td></td></tr><tr><td>All-Uses Coverage</td><td>Tour at least one path for every def-use pair</td><td></td></tr><tr><td>All-DU-Paths Coverage</td><td>Tour every du-path</td><td></td></tr></tbody></table>



## Tools&#x20;

Tool1 (link)
