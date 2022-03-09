# QAMP Spring 2022 Transpiler Hackathon

Our Qiskit Advocate Mentorship Project for Spring, 2022 is a [Transpiler Hackathon](https://github.com/qiskit-advocate/qamp-spring-22/issues/1).

Our Github organization is [here](https://github.com/QAMP-Spring-2022-Transpiler-Hackathon).

A web journal of our effort will be posted [here](https://QAMP-Spring-2022-Transpiler-Hackathon.github.io).

## 2022-03-09:

Our team is now as follows (listed in alphabetical order by last name):

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

## 2022-03-04:

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
