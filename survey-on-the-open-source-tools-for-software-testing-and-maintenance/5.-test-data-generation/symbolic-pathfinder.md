# Symbolic PathFinder

## Description

[Symbolic Pathfinder (SPF) combines symbolic execution with model checking and constraint solving for automated test case generation and error detection in Java programs with unspecified inputs. In this tool, programs are executed on symbolic inputs representing multiple concrete inputs. Values of variables are represented as constraints generated from the analysis of Java bytecode. The constraints are solved using off-the shelf solvers to generate test inputs guaranteed to achieve complex coverage criteria. SPF has been used successfully at NASA, in academia, and in industry.](#user-content-fn-1)[^1]

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Sample diagram of SPF<br>(source: <a href="https://github.com/SymbolicPathFinder/jpf-symbc/tree/master/doc">https://github.com/SymbolicPathFinder/jpf-symbc/tree/master/doc</a>)</p></figcaption></figure>

## Setup

Ensure Java 8 is installed. Symbolic PathFinder may not work with newer versions of Java.

{% embed url="https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html" %}

SPF developers recommend using the Eclipse Integrated Development Environment.

{% embed url="https://www.eclipse.org/downloads/" %}

**Download JPF Core:** Download the JPF Core library from one of the following sources:

[yannicnoller/jpf-core](https://github.com/yannicnoller/jpf-core/tree/0f2f2901cd0ae9833145c38fee57be03da90a64f)

[corinus/jpf-core](https://github.com/corinus/jpf-core)



**Download JPF Symbolic Extension:** Download the JPF Symbolic extension from the following source:

[SymbolicPathFinder/jpf-symbc](https://github.com/SymbolicPathFinder/jpf-symbc)



**Import Projects:** Import both the JPF Core and JPF Symbolic extension as separate Java projects into your Eclipse workspace.



**Create a Configuration File:** Create a `.jpf` directory in your home directory and create a file named `site.properties` within it. This file should contain the following content:

```bash
bashCopy codejpf-core = ${user.home}/.../path-to-jpf-core-folder/jpf-core
jpf-symbc = ${user.home}/.../path-to-jpf-core-folder/jpf-symbc
extensions = ${jpf-core},${jpf-symbc}
```



## Demo

[^1]: [https://dl.acm.org/doi/10.1145/1858996.1859035](https://dl.acm.org/doi/10.1145/1858996.1859035)
