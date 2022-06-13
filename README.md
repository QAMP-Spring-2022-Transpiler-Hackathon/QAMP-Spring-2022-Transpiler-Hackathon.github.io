# QAMP Spring 2022 Transpiler Hackathon

Our Qiskit Advocate Mentorship Project for Spring, 2022 is a [Transpiler Hackathon](https://github.com/qiskit-advocate/qamp-spring-22/issues/1).

Our Github organization is [here](https://github.com/QAMP-Spring-2022-Transpiler-Hackathon).

[View this document formatted on GitHub Pages](https://qamp-spring-2022-transpiler-hackathon.github.io/)

Table of Contents
=================

* [QAMP Spring 2022 Transpiler Hackathon](#qamp-spring-2022-transpiler-hackathon)
* [Table of Contents](#table-of-contents)
   * [Our team (listed in alphabetical order by last name):](#our-team-listed-in-alphabetical-order-by-last-name)
      * [Vishnu Ajith](#vishnu-ajith)
      * [Harshit Gupta](#harshit-gupta)
      * [Pulkit Sinha](#pulkit-sinha)
      * [Oskar Słowik](#oskar-słowik)
      * [Jack Woehr (mentor)](#jack-woehr-mentor)
   * [Blog](#blog)
      * [2022-04-28](#2022-04-28)
         * [Progress](#progress)
         * [Tasks](#tasks)
         * [General](#general)
      * [2022-04-11](#2022-04-11)
         * [Progress](#progress-1)
         * [Tasks](#tasks-1)
      * [2022-04-07 QAMP Spring 2022 Checkpoint #1](#2022-04-07-qamp-spring-2022-checkpoint-1)
      * [2022-04-04](#2022-04-04)
         * [Presentation](#presentation)
         * [Issues](#issues)
      * [2022-03-28](#2022-03-28)
         * [Discussion](#discussion)
         * [Agenda / Tasks](#agenda--tasks)
      * [2022-03-24](#2022-03-24)
         * [Agenda for this week](#agenda-for-this-week)
         * [PR development layout](#pr-development-layout)
         * [Tasks](#tasks-2)
      * [2022-03-14](#2022-03-14)
      * [2022-03-04:](#2022-03-04)
      * [A blue-sky thought about Optimization](#a-blue-sky-thought-about-optimization)
      * [Project plan](#project-plan)
         * [First step](#first-step)

_TOC created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)_

## Our team (listed in alphabetical order by last name):

### Vishnu Ajith

* Final year undergrad student in computer science
* Took part in a summer school on compiler analysis
* Trained computer vision edge based products
* Very interested in the transpiler and simulators.
* Part of QAMP Fall 2021

### Harshit Gupta

* [Résumé](https://bit.ly/resume_harshit)
* QAMP Fall 2021 with Aboulkhair Foda under the mentorship of Kevin Krsulich wrote [Transpiler Debugger](https://github.com/TheGupta2012/qiskit-timeline-debugger)

### Pulkit Sinha

* 4th year Mathematics Major at Indian Institute of Science
* Silver medal at IMO 2018
* 2nd in the ICPC Quantum Challenge 2021
* 3rd in IBM Quantum Challenge Fall 2020
* Working under Prof. Ashwin Nayak from University of Waterloo (IQC) on research problems in Quantum Learning Theory

### Oskar Słowik

* [Résumé](http://quantmath.pl/cv2/)
* PhD student in mathematical aspects of quantum computing
* MSc in Math
* [Two publications in Quantum Journal](https://scholar.google.com/citations?user=ZFtNZFEAAAAJ&hl=en&oi=ao)
* Open-source contributions, e.g. [QREM](https://pypi.org/project/QREM/)

### Jack Woehr (mentor)

* Programming 40 years
* Open Source author
* Contributing editor 1991-2011 _Dr. Dobb's Journal_
* Qiskit Advocate since 2019
* IBM Champion 2021-2022
* Current secretary of of the OpenQASM 3 Technical Steering Committee

## Blog

### 2022-06-13
[QAMP Spring 2022 final presentation video](https://drive.google.com/file/d/13-asuitwPUZTHN9J2nfQtgltPpkh3JgX/view?usp=sharing)

### 2022-05-05
[QAMP Spring 2022 Checkpoint Presentation #2](https://github.com/QAMP-Spring-2022-Transpiler-Hackathon/QAMP-Spring-2022-Transpiler-Hackathon.github.io/tree/main/checkpoint_presentations/checkpoint_2_20220505)

### 2022-04-28
In attendance Harshit Gupta, Oskar Słowik, Jack Woehr, Matthew Treinish

#### Progress
* PRs
    * 7913 merged
    * 7990 ready for review
    * 7879 ready for review
    * 7875 had review, needs work, less substantial than work on issue 7485
* Issues
    * 7485
    * 7705

#### Tasks
* Harshit
    * Regression from PR 7181 (merged)
    * Issue 7485
* Oskar
    * Graphs to show Matthew
    * Work on 7705
* All
    * Discuss May 5 overview on Slack

#### General
* Matthew
    * Team can help on reviews
    * Look at open Transpiler PRs
        * provide feedback
        * familiarize self with code and see where things are going
        * team can see bugs as well as anyone
* Harshit
    * Exams May 5 - May 15
* Oskar & Jack
    * Meet via Slack during Harshit's hiatus for exams.

### 2022-04-11
In attendance Harshit Gupta, Oskar Słowik, Jack Woehr

#### Progress
PR 7193 for 7181 - Harshit submitted substantial improvements
PR 7875 for 7296 - Harshit submitted ... work in progress ...add Gate attribute qubit_symmetric
7113 .. if PR 7193 gets accepted would simplify tackling 7113.
7705 .. Oscar benchmarking
7485 .. BasisTranslator taking up to 1G of memory ... attractive and substantial issue because level 1,2,3 all use BasisTranslator

#### Tasks
* Examine where should we place the check for the symmetric qargs in the InverseCancellation pass? - Harshit
* With 7181 working pretty good now, one thought is that should we try to make it target aware? Matthew had included it in the list of passes to make target aware and since Harshit got a bit familiar with it during optimization, he will try doing that.
* Continue 7705 Discover some parameters for the tuning of the time for search - Oskar
* 7485 - Oskar
* Jack will keep lines of communication open with IBM team.

### 2022-04-07 QAMP Spring 2022 Checkpoint #1
Our [Checkpoint #1 presentation PDF](https://github.com/QAMP-Spring-2022-Transpiler-Hackathon/QAMP-Spring-2022-Transpiler-Hackathon.github.io/blob/main/checkpoint_presentations/checkpoint_1_20220407/%231_Transpiler_Hackathon.pdf)

### 2022-04-04
In attendance Harshit Gupta, Oskar Słowik, Jack Woehr

#### Presentation
  * 8-10 slides
  * We first try to give brief overview of the transpiler, where it is situated, how it works and what are its major components
  * Then move on to the goals of our project and discuss how we are going to contribute to the qiskit transpiler
  * After that, bring in our project plan - working on two major issues and being helpful on the side.
  * At the end, show the current PRs and our progress on the issues, to show proof of initial work.
  * Questions
  * Jack -- intro slide, project plan slide
  * Oskar, Harshit -- 2 issues slides each
  * Jack -- slide for link to blog

#### Issues
  * [7296](https://github.com/Qiskit/qiskit-terra/issues/7296) .. PR [7875](https://github.com/Qiskit/qiskit-terra/pull/7875) ready for review
  * [7386](https://github.com/Qiskit/qiskit-terra/issues/7386) .. PR [7542](https://github.com/Qiskit/qiskit-terra/pull/7542) was merged
  * [7387](https://github.com/Qiskit/qiskit-terra/issues/7387) .. stalled
  * [7705](https://github.com/Qiskit/qiskit-terra/issues/7705) .. Oskar to continue on this
  * [7181](https://github.com/Qiskit/qiskit-terra/issues/7181) .. Oskar and Harshit take this one up after presentation
  * [7113](https://github.com/Qiskit/qiskit-terra/issues/7113) .. Deal with this after 7181

### 2022-03-28
In attendance Vishnu Ajith, Harshit Gupta, Oskar Słowik, Jack Woehr

#### Discussion
We discussed an apparent anomaly in DAG generation as exemplified by Harshit's example:
```
from qiskit.converters import circuit_to_dag
from qiskit import QuantumCircuit
from qiskit.circuit import QuantumRegister, ClassicalRegister
from qiskit.visualization import dag_drawer

qr = QuantumRegister(3)
cr = ClassicalRegister(3)
circ_reg = QuantumCircuit(qr, cr)
circ_reg.h(qr[0])
circ_reg.h(qr[1])
circ_reg.measure(qr[0], cr[0])
circ_reg.measure(qr[1], cr[1])
circ_reg.x(qr[0]).c_if(cr, 0x3)
circ_reg.measure(qr[0], cr[0])
circ_reg.measure(qr[1], cr[1])
circ_reg.measure(qr[2], cr[2])

# direct
circ_no_reg = QuantumCircuit(3, 3)
circ_no_reg.h([0, 1])
circ_no_reg.measure([0, 1, 2], [0, 1, 2])
circ_no_reg.x(0).c_if(circ_no_reg.cregs[0], 0x3)
circ_no_reg.measure([0, 1], [0, 1])

# print("Circuit is :", circ_no_reg.draw())

dag_in = circuit_to_dag(circ_no_reg)
dag_in_reg = circuit_to_dag(circ_reg)

dag_drawer(dag_in, scale=0.7, filename="dag_in_no_reg.png")
dag_drawer(dag_in_reg, scale=0.7, filename="dag_in_with_reg.png")
```
The circuits are semantically equivalent but draw quite different DAGs.
Harshit will run this by Matthew Treinish.

#### Agenda / Tasks

* Previously we had looked at how to write benchmarks for different mappings w/r/t #7705 Add adaptive limits for VF2Layout in preset passmanagers
  * Oskar start working on tools for benchmarking for #7705.
  * Can have substantial progress (Harshit)
  * Harshit has some code to send Oskar as a template for writing the benchmarking code.

* We were also intending to work on #7113 Add support for BackendV2 and Target to transpiler
  * Current IBM backend devices seem to have mostly Heavy Hex mapping.
  * Earlier QPUs had Heavy Square
  * Vishnu on #7113

* Harshit still working on #7387
  * Possibility of reaching a dead end in an intrinsic difficulty problem.
  * Polling Kevin and Matthew

* Structure with fork and branches is good
* Metric of our effort is PR's: reviews and acceptance

### 2022-03-24
In attendance Harshit Gupta, Pulkit Sinha, Jack Woehr

#### Agenda for this week
Focus on [parallelization / depth reduction pass](https://github.com/Qiskit/qiskit-terra/issues/7387)

There are promising heuristic strategies but not all guarantee either a solution nor an optimal solution.

Create transpiler pass DagDependencyReducer which will wrapper 3 algorithms

1. GlobalMaxDAGDepthReducer
1. InteractiveDAGDepthReducer
1. IterativeDAGDepthReducer

The 3 algorithms will be coded (at first) in individual files.
The question arose in the discussion whether the team should present 3 separate PRs for the 3 algorithms.
We decided that we should submit as one PR and let the IBM engineers decide how to mix and match.

#### PR development layout
1. Create local branch `dagdependencyreducer`
1. Check in an empty Transpiler pass as `dagdependencyreducer.py`
1. Push branch to our fork.
1. Team clones our `qiskit-terra` fork.
1. Team does `git fetch` then `git checkout dagdependencyreducer`
1. From the `dagdependencyreducer` branch,  create sub-branches of the branch as follows:
  1. `git checkout -b GlobalMaxDAGDepthReducer`
  2. `git push -u origin GlobalMaxDAGDepthReducer`
  3. Repeat from `dagdependencyreducer` branch for `InteractiveDAGDepthReducer` and `IterativeDAGDepthReducer`

As work progresses on individual sub-branches, the team can:
* commit and stash changes
* checkout the parent branch `dagdependencyreducer` and start building out the master `DagDependencyReducer` class in `dagdependencyreducer.py`
* commit and push the `dagdependencyreducer` branch
* checkout the sub-branch and merge the parent branch by `git merge dagdependencyreducer`

Continue development …

#### Tasks
1. Incorporate qubit args in the GlobalMaxDAGDepthReducer (Harshit)
1. Write basic code for InteractiveDAGDepthReducer and IterativeDAGDepthReducer (Pulkit)

### 2022-03-14
Our team met today with Kevin Krsulich of the IBM Q team to examine promising transpiler issues to address. Two major issues that came up in discussion are:
* [Add adaptive limits for VF2Layout in preset passmanagers](https://github.com/Qiskit/qiskit-terra/issues/7705)
  * The transpiler VF2Layout component, if successful, is very effective, but if unsuccessful, can take a long time to fail. This can be partly addressed by proving the user with a "knob" to dial back how long or how many tries VF2Layout takes before giving up. Currenty, there are fixed time limits, but such limits to be effective need to be sensitive to device size and input circuit size. We need examples of perfect layouts which are hard to solve within the current mapping. The solution to the problem is driven by different applications, demonstrations, and examples. There does not yet exist a sufficient body of benchmarks. There are a few papers on VF2, but experimentation will be needed to yield substantial improvement.
* [Add support for BackendV2 and Target to transpiler](https://github.com/Qiskit/qiskit-terra/issues/7113)
  * The previous version, Backend V1, is still in use in most places, and deals with configuration, coupling, and basis gates. Backend V2 extends these notions and provides better support for different hardware architectures, e.g., ion traps, which are not well represented by V1. V2 is more general,and expresses gates independently. Support for V2 within existing transpiler passes very limited. All passes must be updated for V2: this one issue will spawn nultiple PRs. The effort is made difficult in that there exists many hard-coded assumptions in the transpiler code.

Additionally, team member Harshit Gupta is currently finishing up work he previously undertook on the following to issues:
* [better convergence criteria in preset passmanagers](https://github.com/Qiskit/qiskit-terra/issues/7386)
* [parallelization / depth reduction pass](https://github.com/Qiskit/qiskit-terra/issues/7387)

For this coming week, the team is going to all work together on finishing up issue 7387 ("better convergence") with Harshit, in part, to become oriented in the transpiler. Then we will proceed to one of the major issues, either dividing into two groups to address both 7705 and 7113, or working together on one or both of those issues.

Our team may also undertake _inter alia_ to address a few smaller issues that can more easily be closed. Jack Woehr will sift through the transpiler issues for smaller issues.

### 2022-03-04:

Our team of Harshit Gupta, Vishnu Ajith, Oskar Słowik, and Jack Woehr met today via Zoom.
We discussed the following points

* The 3 aspects of the Qiskit Transpiler
  * Coupling map
  * Basis gates
  * Optimization

### A blue-sky thought about Optimization

- Circuit optimization may be a paradigmatic example of quantum computation

- Current devices at our disposal are probably not powerful enough to achieve much in this respect. But see [this discussion about performing certain transpiler passes on the quantum device itself](https://github.com/qiskit-community/feedback/discussions/3#discussioncomment-1485832).

### Project plan

- Tackle [Qiskit Terra transpiler issues](https://github.com/Qiskit/qiskit-terra/issues?q=is%3Aissue+is%3Aopen+transpiler) as recommended by the IBM Qiskit Team, particularly

  - Matthew Treinish
  - Kevin Krsulich

- We have no specific goal other than to be useful to Qiskit Transpiler development. We may find ourselves performing any mixture of the following:

  - PR many small issues
  - Work as a team on one or more major issues
  - Invent a new feature ourselves

- We will meet weekly starting 2022-03-14

#### First step

Matthew Treinish requests that the team help out with [#7113 Add support for BackendV2 and Target to transpiler](https://github.com/Qiskit/qiskit-terra/issues/7113)
