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

| Coverage              | Requirements                                                         |
| --------------------- | -------------------------------------------------------------------- |
| All-Defs Coverage     | For each def, we need to tour at least one path for at least one use |
| All-Uses Coverage     | Tour at least one path for every def-use pair                        |
| All-DU-Paths Coverage | Tour every du-path                                                   |



## Tools&#x20;

<table><thead><tr><th>Tool</th><th>Description</th><th data-type="content-ref">Link</th></tr></thead><tbody><tr><td>Bitwise Algorithm - powered Definition-Use Association<br>(ba-dua)</td><td>an intra-procedural data-flow testing tool for Java programs.</td><td><a href="https://github.com/saeg/ba-dua">https://github.com/saeg/ba-dua</a></td></tr><tr><td>JavaDataFlow</td><td>Creating Data Flow Graphs from java input classes</td><td><a href="https://github.com/daanvdh/JavaDataFlow">https://github.com/daanvdh/JavaDataFlow</a></td></tr><tr><td>VisualDFA</td><td>sophisticated educational tool for interactively visualizing data-flow analyses using Java/Jimple.</td><td><a href="https://github.com/ppati000/visualDFA">https://github.com/ppati000/visualDFA</a></td></tr><tr><td>jdataflow</td><td>jdataflow is a Z3 solver based data-flow analyzer for Java source code.</td><td><a href="https://github.com/Egor18/jdataflow">https://github.com/Egor18/jdataflow</a></td></tr><tr><td>Soot</td><td>Analyze, instrument, optimize and visualize Java and Android applications. This tool can be used for Data Flow Analysis on simple Java programs.</td><td><a href="https://aamodkore.github.io/notes/dfa-tutorial.html">https://aamodkore.github.io/notes/dfa-tutorial.html</a></td></tr></tbody></table>

