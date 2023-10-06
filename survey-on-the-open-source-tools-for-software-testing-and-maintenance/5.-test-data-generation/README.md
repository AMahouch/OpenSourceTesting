# 5. Test Data Generation

## Description

Test data generation is the process of creating input data for a software program to test its functionality. Test data can be generated manually or automatically. Automated test data generation can help to improve the coverage and quality of testing.

#### Symbolic Execution

Symbolic execution is a technique that executes a program using symbolic values instead of concrete values. Symbolic execution can be used to generate test data by solving the path conditions for a given path through the program.

#### Search-Based Generation

Search-based generation is a technique that uses search algorithms to generate test data. Search-based generation can be used to generate test data for complex programs with many inputs.

\


## Tools&#x20;



{% embed url="https://github.com/SymbolicPathFinder/jpf-symbc" %}



<table data-full-width="true"><thead><tr><th>Tool</th><th>Description</th><th width="100" data-type="content-ref">Link</th></tr></thead><tbody><tr><td>Symbolic Pathfinder</td><td>Symbolic execution tool built on Java Pathfinder Supports multiple constraint solvers, lazy initialization, etc.</td><td><a href="https://github.com/SymbolicPathFinder/jpf-symbc">https://github.com/SymbolicPathFinder/jpf-symbc</a></td></tr><tr><td>JDart</td><td>Dynamic symbolic execution tool built on Java PathFinder. Supports multiple constraint solvers using JConstraints.</td><td><a href="https://github.com/psycopaths/jdart">https://github.com/psycopaths/jdart</a></td></tr><tr><td>CATG</td><td>Concolic execution tool that uses ASM for instrumentation. Uses CVC4.</td><td><a href="https://github.com/ksen007/janala2">https://github.com/ksen007/janala2</a></td></tr><tr><td>LIME Testbench</td><td>Concolic execution tool that uses Soot for instrumentation. Supports Yices and Boolector. Concolic execution can be distributed.</td><td><a href="http://www.tcs.hut.fi/Software/lime/">http://www.tcs.hut.fi/Software/lime/</a></td></tr><tr><td>Automated Concolic Testing of Smartphone Apps (acteve)</td><td>Concolic execution tool that uses Soot for instrumentation. Originally for Android analysis. Supports Z3.</td><td><a href="https://code.google.com/archive/p/acteve/">https://code.google.com/archive/p/acteve/</a></td></tr><tr><td>jCUTE</td><td>Concolic execution tool that uses Soot for instrumentation. Supports lp_solve.</td><td><a href="http://osl.cs.illinois.edu/software/jcute/">http://osl.cs.illinois.edu/software/jcute/</a></td></tr></tbody></table>

#### Symbolic PathFinder

#### JDart

{% embed url="https://github.com/psycopaths/jdart" %}

#### CATG

{% embed url="https://github.com/ksen007/janala2" %}

#### LIME Testbench

{% embed url="http://www.tcs.hut.fi/Software/lime/" %}

#### Automated Concolic Testing of Smartphone Apps (acteve)

{% embed url="https://code.google.com/archive/p/acteve/" %}

#### jCUTE

{% embed url="http://osl.cs.illinois.edu/software/jcute/" %}
