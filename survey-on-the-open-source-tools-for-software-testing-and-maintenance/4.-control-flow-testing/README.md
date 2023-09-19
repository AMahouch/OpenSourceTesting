# 4. Control Flow Testing

## Description

Control Flow Testing is a form of graph-based testing. Graph-based testing is a model approach in which a model (abstraction) of the program is generated and tested over certain elements.&#x20;



#### The following components contribute to control flow testing:

**Basic block -** sequence of consecutive statements with a single entry and a single exit point (one statement executed, all the statements must be executed)

* control always enters basic block at entry and exits from exit
* can't halt, exit, or enter inside a basic block

Take for example, this example program and its associated blocks:   &#x20;

{% code lineNumbers="true" fullWidth="false" %}
```
begin
    int x, y, power;
    float z;
    input (x, y);
    if(y < 0)
        power = -y;
    else
        power = y;
    z = 1;
    while(power != 0) {
        z = z * x;
        power = power - 1;
    }
    if(y < 0)
        z = 1/z;
    output(z);
end
```
{% endcode %}

<figure><img src="../../.gitbook/assets/image (3).png" alt="" width="375"><figcaption></figcaption></figure>

















## Tools&#x20;

Tool1 (link)
