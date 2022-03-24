# QAMP Spring 2022 Transpiler Hackathon

Our Qiskit Advocate Mentorship Project for Spring, 2022 is a [Transpiler Hackathon](https://github.com/qiskit-advocate/qamp-spring-22/issues/1).

Our Github organization is [here](https://github.com/QAMP-Spring-2022-Transpiler-Hackathon).

[View this document formatted on GitHub Pages](https://qamp-spring-2022-transpiler-hackathon.github.io/)

Table of Contents
=================

* [QAMP Spring 2022 Transpiler Hackathon](#qamp-spring-2022-transpiler-hackathon)
* [Table of Contents](#table-of-contents)
   * [Our team (listed in alphabetical order by last name):](#our-team-listed-in-alphabetical-order-by-last-name)
      * [Vishu Ajith](#vishu-ajith)
      * [Harshit Gupta](#harshit-gupta)
      * [Pulkit Sinha](#pulkit-sinha)
      * [Oskar Słowik](#oskar-słowik)
      * [Jack Woehr (mentor)](#jack-woehr-mentor)
   * [Blog](#blog)
      * [2022-03-24](#2022-03-24)
         * [Agenda for this week](#agenda-for-this-week)
         * [PR development layout](#pr-development-layout)
         * [Tasks](#tasks)
      * [2022-03-14](#2022-03-14)
      * [2022-03-04:](#2022-03-04)
      * [A blue-sky thought about Optimization](#a-blue-sky-thought-about-optimization)
      * [Project plan](#project-plan)
         * [First step](#first-step)

_TOC created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)_

## Our team (listed in alphabetical order by last name):

### Vishu Ajith

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
