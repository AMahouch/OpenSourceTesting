# 7. Predicate Testing

## Description

Predicate testing is a software testing technique that focuses on ensuring that the predicates in a program are implemented correctly. Predicates are Boolean expressions that can be evaluated to either true or false, often used in decision statements to determine which path of execution to take.

Predicate testing can be used to test both **program-based predicates** and **specification-based predicates**.

* Program-based predicates are those that can be identified from the branching points of the source code.
* Specification-based predicates are those that can be identified from the formal and informal requirements for the program, as well as from behavioral models such as finite state machines.

There are several test coverages in predicate testing, using the basic concepts of booleans, logical operators, clauses, and active clauses.

| Coverage                                 | Description (test requirements)                                                                                                                                                  |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Predicate Coverage                       | p evaluates to true and p evaluates to false for every predicate p.                                                                                                              |
| Clause Coverage                          | c evaluates to true and c evaluates to false for every clause c.                                                                                                                 |
| Combinatorial Coverage                   | For each predicate p, clauses in p evaluate to each possible combination of truth values.                                                                                        |
| Active Clause Coverage (ACC)             | For each predicate p and each major clause c of p, choose minor clauses so that c determines p. TR has two requirements for each c: c evaluates to true and c evaluates to false |
| General Active Clause Coverage (GACC)    | The same as ACC, and it does not require the minor clauses have the same values when the major clause evaluates to true and false.                                               |
| Correlated Active Clause Coverage (CACC) | The same as ACC, but it requires the entire predicate to be true for one value of the major clause and false for the other.                                                      |
| Restricted Active Clause Coverage (RACC) | The same as ACC, but it requires the minor clauses have the same values when the major clause evaluates to true and false.                                                       |

In practicality, there are two challenges when applying predicate testing to programs:

* **Reachability**: A test must be able to reach the predicate being tested.
* **Controllability**: Internal variables must be rewritten in terms of external input variables.

### Importance

Predicate testing is required by US FAA for safety critical avionics software in commercial aircraft. Similarly in the [medical device industry](#user-content-fn-1)[^1], predicate testing is crucial for ensuring that software embedded in devices like pacemakers, infusion pumps, and MRI machines operates correctly and safely.

## Tools&#x20;

There is no singular, universally acknowledged open source tool specifically designed for predicate testing. Predicate testing is a niche testing technique. It is not as widely used as other testing techniques, such as unit testing and regression testing. As a result, there is less demand for dedicated predicate testing tools. In our systematic exploration of the open-source landscape to discover tools suitable for predicate testing, we undertook an exhaustive search methodology encompassing:

* Search engines (i.e. Google, Bing)
* Open source directories (i.e. GitHub, SourceForge, GitLab)
* Academic research papers (i.e. Google Scholar, ACM Digital Library, IEEE Xplore)
* Large language models (i.e. GPT-3.5, PaLM 2)

Search terms on these platforms included:

* "Predicate testing open source tools"
* "Boolean expression testing open-source tools"
* "Predicate coverage open-source tools"
* "Predicate test case generator open-source tools"
* "Predicate coverage criteria open-source tools"
* "Predicate-based test cases open-source tools"
* "Predicate testing frameworks"
* "Predicate analysis tools"
* "Predicate coverage analysis open source"
* "Open source tools for clause coverage"
* "Predicate-based testing tools"

_(search performed Oct. 23-26, 2023)_



[^1]: [https://www.mdpi.com/2079-9292/11/13/2062](https://www.mdpi.com/2079-9292/11/13/2062)
