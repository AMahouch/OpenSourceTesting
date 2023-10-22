# 4. Control Flow Testing

## Description

Control Flow Testing is a form of graph-based testing. Graph-based testing is a model approach in which a model (abstraction) of the program is generated and tested over certain elements.&#x20;

#### The following components contribute to control flow testing:

**Graph** consists of a set of nodes and edges that connect pairs of nodes.

**Path** is a sequence of nodes, where each pair of adjacent nodes is an edge.

* **Length** of a path refers to number of edges in the path.
* **Subpath** of a path is a subsequence
* **Test path** is a path that starts with an initial node and ends at a final node
* **Simple path** is a path where no node appears more than once in the path, excluding the first and last nodes being identical.
* **Prime path** is maximum simple path. It does not appear as a proper subpath of any other simple path.

**Basic block** is a sequence of consecutive statements with a single entry and a single exit point (one statement executed, all the statements must be executed)

* Control always enters basic block at entry and exits from exit
* Cannot halt, exit, or enter inside a basic block

**A control flow graph is a graph with two distinguished nodes, start and end**

* **Node start has no incoming edges, and node end has no outgoing edges.**
* **Every node can be reached from start, and can reach end.**

### Example

Take for example, this example program and its associated blocks:   &#x20;

{% code lineNumbers="true" fullWidth="false" %}
```pascal
begin
    int x, y, power;
    float z;
    input (x, y);
    if(y < 0)
        power = -y;
    else
        power = y;
    z = 1;
    while(power != 0) 
        z = z * x;
        power = power - 1;
        
    if(y < 0)
        z = 1/z;
    output(z);
end
```
{% endcode %}

<table data-full-width="true"><thead><tr><th>Block</th><th>Lines</th><th>Entry</th><th>Exit</th></tr></thead><tbody><tr><td>1</td><td>2, 3, 4, 5</td><td>2</td><td>5</td></tr><tr><td>2</td><td>6</td><td>6</td><td>6</td></tr><tr><td>3</td><td>8</td><td>8</td><td>8</td></tr><tr><td>4</td><td>9</td><td>9</td><td>9</td></tr><tr><td>5</td><td>10</td><td>10</td><td>10</td></tr><tr><td>6</td><td>11, 12</td><td>11</td><td>12</td></tr><tr><td>7</td><td>14</td><td>14</td><td>14</td></tr><tr><td>8</td><td>15</td><td>15</td><td>15</td></tr><tr><td>9</td><td>16</td><td>16</td><td>16</td></tr></tbody></table>

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt="" width="233"><figcaption><p>Control flow graph for the code and defined basic blocks above</p></figcaption></figure>

***

Coverage criteria are used to define the specific requirements that test cases must fulfill to ensure thorough testing. These criteria encompass various aspects of the program's control flow, striving to examine every conceivable path and component within the codebase.

**Node Coverage**

* TR: each reachable node in a graph G.

**Edge Coverage**

* TR: each reachable path of length up to 1, inclusive, in a graph G.

**Edge-Pair Coverage**

* TR: each reachable path of length up to 2, inclusive, in a graph G.

**Complete Path Coverage**

* TR: all paths in a graph G.

**Prime Path Coverage**

* TR: every prime path in a graph G.

## Tools



| Tool         | Description                                                                                                                                                                                                                                                              | Link                                                                                                                         |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| Soot         | Soot is an open-source framework for analyzing and transforming Java bytecode. While it's more comprehensive than just control flow testing, it offers control flow analysis capabilities that can be useful in software engineering.                                    | [https://github.com/soot-oss/soot](https://github.com/soot-oss/soot)                                                         |
| CoFlo        | CoFlo is an open-source control flow analysis tool for C and C++ programs. It generates control flow graphs, supports data flow analysis, and helps identify potential issues related to control flow.                                                                   | [https://sourceforge.net/projects/coflo/](https://sourceforge.net/projects/coflo/)                                           |
| py2cfg       | py2cfg is a Python-based tool for generating control flow graphs from Python code. It can be used to visualize and analyze the control flow of Python programs.                                                                                                          | [https://pypi.org/project/py2cfg/](https://pypi.org/project/py2cfg/)                                                         |
| cfg-gen-draw | Simple Java code that generates every method's CFG of a given Java software. The CFG generation is powered with Soot. Then these CFG's are generated in ".dot" format. Then these dot files parsed by Graphviz and each CFG is visualized with any image format desired. | [https://github.com/ekincanufuktepe/cfg-gen-draw#cfg-gen-draw](https://github.com/ekincanufuktepe/cfg-gen-draw#cfg-gen-draw) |
| CFGScanDroid | CFGScanDroid is a utility for comparing control flow graph (CFG) signatures to the control flow graphs of Android methods.                                                                                                                                               | [https://github.com/TACIXAT/CFGScanDroid#cfgscandroid](https://github.com/TACIXAT/CFGScanDroid#cfgscandroid)                 |

