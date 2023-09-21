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

* control always enters basic block at entry and exits from exit
* can't halt, exit, or enter inside a basic block



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

<figure><img src="../../.gitbook/assets/image (3).png" alt="" width="375"><figcaption></figcaption></figure>

![](../../.gitbook/assets/image.png)















## Tools&#x20;

Tool1 (link)
