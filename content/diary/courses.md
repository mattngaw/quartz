---
title: Courses @ CMU
date: 2024-8-10
description: my thoughts on courses at Carnegie Mellon
tags:
  - "#evergreen"
  - cmu
---

<style> summary { cursor: pointer } </style>

>[!warning]
>\[2024-07-29\] This post will be subject to reformatting changes soon.
## Foreword

The following is inspired by the many other CMU course reviews out there on the
internet. Just search `cmu course reviews` in your favorite search engine, and you can find pages like this. However, pretty much every other site you will find will be from a CMU SCS 
student/alum.[^1] I have yet to see a course review post from a CMU ECE
student/alum. Maybe this will inspire people to make more! 🤞

[^1]: Here are some of my favorites course reviews: [1](https://fanpu.io/courses/) [2](https://www.ericzheng.org/thoughts/index.html) [3](https://wanshenl.me/courses/reviews/) [4](https://thenumb.at/cmu/)

If you're a current CMU student, I recommend you plan your semesters using ScottyLabs' [CMU Courses](https://cmucourses.com/) tool. You want to have an idea of how many hours your planned coursework will take from you. Broadly speaking, and I mean *broadly*, 40 to 50 hours for one semester is a balanced enough schedule that will leave you enough time for extracurriculars, hobbies, exercise, and a healthy social life. For the average person[^2], any more hours will mean sacrificing something else.

[^2]: "But what if I'm not the *average person*? I'm built different!" You might be different. To each their own. I'll say it again, I'm giving *broad* suggestions. Don't oversubscribe, or something else will have to give.

If you're a CMU ECE student, I also recommend looking at Professor James Hoe's [advice for CMU ECE undergrads](https://users.ece.cmu.edu/~jhoe/doku/doku.php?id=advice_columa), and these [CMU ECE & CS Course Guides](https://github.com/CMU-HKN/CMU-ECE-CS-Guide). I wish I stumbled upon Professor Hoe's advice in my freshman year.

----

## Key

These emojis act as qualifiers to describe my experience with each class.

- ⭐️: Transformative. It gave me a perspective-change.

- ❤️: Loved/enjoyed. I had a fun with this class.

- 🔨: Time-consuming. Conceptually hard, and/or just lots of work.

I've included the number of units next to each course, and for additional 
context, I've included the average workload in terms of hours as reported by 
students in Faculty Course Evaluations (at the time of writing). These hours are
an underestimate, since they do not include things like TAing and research. I've
also included a list of any other commitments I had during each semester. The 
commitments are listed in descending order of impact. Lastly, I've left a small
blurb under some semesters describing how I felt about the semester/workload.

Some semesters, especially the earlier ones, are missing these details, mostly 
because I've ~~shut them out~~ forgotten them. The COVID years were 
terrible for me.

Here is what I tentatively have planned for next year (my [IMB](https://www.ece.cmu.edu/academics/integrated.html) year).

## Fall 2024 (Upcoming)

- 18-622 Digital Integrated Circuit Design

- 15-749 Computing After CPUs: Recent Research in Non-Von Neumann Computer Architecture

- 17-715 Advanced Topics in Hardware Security

- 18-640 Hardware Arithmetic for Machine Learning (*tentative*)

- Research?

- (TA) ???

## Spring 2025 (Future)

- 18-725 Advanced Digital Integrated Circuit Design

- 18-742 Computer Architecture and Systems

- ???

- Research?

- (TA) ???

Here are my thoughts on the courses that I have taken.

## Spring 2024

- ⭐️ 🔨 [15-411](https://www.cs.cmu.edu/~janh/courses/411/24/index.html) Compiler Design (15)

   - Not too challenging conceptually, but it was an engineering nightmare to 
   put together so much code from scratch. By the end of the semester, we were
   able to cobble together a compiler and runtime environment that *in 
   principle* performed [mark-and-sweep garbage collection](https://en.wikipedia.org/wiki/Tracing_garbage_collection#Na%C3%AFve_mark-and-sweep)
   on top of implementing the [C0 language](https://c0.cs.cmu.edu/docs/c0-reference.pdf).

- [18-341](https://github.com/CMU-HKN/CMU-ECE-CS-Guide/blob/master/electives/18341.md) Logic Design and Verification (12)

   - Took this for extra SystemVerilog practice. I personally did not find 
   verification interesting, but SV has some nifty constructs. I was chilling
   in the class until USB.

- 🔨 [18-500](https://course.ece.cmu.edu/~ece500/projects/) ECE Design Experience (12)

   - My salty, reductionist take on what happened to my team: set ourselves up for
   Icarian failure by choosing a very difficult project, failed to get early enough feedback
   to bring us back down to earth, grinded ourselves to the bone just to get something 
   barely working at the end, with lots of busy documentation work interspersed.

- 85-241 Social Psychology (9)

- (Research) Application-Based Fault-Tolerance, Radiation Hardening, Floating-Point ($)

**FCE Hours**: 56, definitely was at least 56. 

**Other Commitments**: Gym 5-6x a week (until the last quarter of the semester), SO time,
some social life (in the first two thirds), a spring break trip (do not regret despite the later pain).

**Workload**: The highest I have ever experienced. This semester there were probably 10ish days
where I effectively did not sleep (1-2 hours max, I can't operate with truly zero sleep). Call it
cognitive dissonance and justification of effort, but in this semester I feel I learned the most I ever
have despite the suffering. I do not regret going through the struggle.

## Fall 2023

- ⭐️ [18-740](https://github.com/CMU-HKN/CMU-ECE-CS-Guide/blob/master/electives/18740.md) Modern Computer Architecture and Design (12)

   - Conceptually interesting. It was the first time I was properly exposed to out-of-order execution.
   The labs could be a lot better, since I did not gain much insight from them. Logistically, the class
   could have been run a lot better (more TAs were definitely needed).

- 🔨 [18-643](https://users.ece.cmu.edu/~jhoe/doku/doku.php?id=18-643_reconfigurable_logic) Reconfigurable Hardware (12)

   - On first glance, this class looks like a class on FPGAs and HLS. However, much of the lecture content covers 
   those topics, but the labs make this class a hardware design and optimization class in disguise. It was painful to
   use Vitis HLS, but otherwise I learned a lot about hardware design (a tool-agnostic skill).

- ❤️ [18-220](https://youtu.be/wfXyBDZX-zw) Electronic Devices and Analog Circuits (12)

   - Fundamental, and Professor Budnik made it very enjoyable.

- 82-137 Chinese Calligraphy: Culture and Skills (9)

   - Fun and chill.

- 66-221 Topics of Law: Introduction to Intellectual Property Law (9)

   - Comically chill. Like, too chill. Like, "should this class even be offered" chill.

- 98-154 Stuco: Intro to Open-Source FPGA & ASIC Chip Design (was not registered, I just showed up lol)

- (Research) 18-580 Application-Based Fault-Tolerance, Radiation Hardening, Floating-Point (9)

- (TA) 18-344 Computer Systems and the Hardware-Software Interface

**FCE Hours**: 45, felt like 55

**Other Commitments**: Gym 5-6x a week, running 1x a week, SO time, internship search

**Workload**: High, mainly because of 643 + TAing + research.

## Spring 2023

- ⭐️ ❤️ [18-447](https://users.ece.cmu.edu/~jhoe/doku/doku.php?id=18-447_introduction_to_computer_architecture) Introduction to Computer Architecture (12)

   - Solidified my love for computer architecture after 344. Built a superscalar RISC-V core. My project group came in second in both (performance and performance-per-watt) categories!

- [18-349](https://github.com/CMU-HKN/CMU-ECE-CS-Guide/blob/master/electives/18349.md) Introduction to Embedded Systems (12)

- 79-204 American Environmental History (9)

- ❤️ 79-211 Modern Southeast Asia: Colonialism, Capitalism, and Cultural Exchange (9)

- (Research) [SPIRAL](http://www.spiral.net/): Modular Arithmetic, [Finite Fields](https://en.wikipedia.org/wiki/Finite_field), and Encryption

   - After this semester of research, I requested Prof. Franchetti to change my research project. I tried my best to learn the math, but it did not 
   inspire me, and so I struggled to make progress.

- (TA) 18-213 Introduction to Computer Systems

**FCE Hours**: 43, felt like 48

**Other Commitments**: Gym 5-6x a week, running 1x a week, SO time, stressing about summer

**Workload**: Moderate. 447 became more intense (and fun) at the end. So did 349. The gen-eds balanced out the heavier technicals well.

## Fall 2022

- ⭐️ ❤️ [18-344](https://course.ece.cmu.edu/~ece344/) Computer Systems and the Hardware-Software Interface (12)

   - Pivotal. This class put me on the path of computer architecture/systems and hardware.

- 18-290 Signals and Systems (12)

- ❤️ [10-301](http://www.cs.cmu.edu/~mgormley/courses/10601/) Introduction to Machine Learning (12)

- 76-270 Writing for the Professions (9)

- 98-043 StuCo: Chess Tactics and Strategy (3)

- (Research) [SPIRAL](http://www.spiral.net/): [FFT Integer Multiplication](https://en.wikipedia.org/wiki/Convolution_theorem) w/ [Interval Arithmetic](https://en.wikipedia.org/wiki/Interval_arithmetic)

- (TA) 18-213 Introduction to Computer Systems

**FCE Hours**: 44, felt like 48

**Other Commitments**: Gym 5-6x a week, SO time

**Workload**: Moderate.

## Spring 2022

- 🔨 18-240 Structure and Design of Digital Systems (12)

   - 240 was a struggle for me; I did not understand how cool hardware could be
   until I got to later courses.

- ⭐️ [15-150](http://www.cs.cmu.edu/~15150/) Principles of Functional Programming (12)

   - Opened my mind to a different way to program. This class proved useful to me later on
   in both learning Rust and taking Compilers.

- 36-226 Introduction to Statistical Inference (9)

   - Why the heck did I take this class?

- 15-281 Artificial Intelligence: Representation and Problem Solving (12)

- 98-008 StuCo: Shilling The Rust Programming Language (3)

   - My first introduction to Rust. I did not appreciate it as much as I do now because of how tough the other classes were on me.

**FCE Hours**: 50. At this time in my undergrad, I was not ready for 50.

**Other Commitments**: Gym, club frisbee, intramural basketball, social life

**Workload**: Should have been moderate—or with the right focus, even a light workload—but for a variety of reasons it was a heavy load. 
This semester served as a wakeup call for me to reflect on what my priorities are.

## Fall 2021 (first time @ Pitt)

- ⭐️ [18-213](https://www.cs.cmu.edu/~18213/index.html) Introduction to Computer Systems (12)

- 36-225 Introduction to Probability Theory (9)

- 21-241 Matrices and Linear Transformations (11)

- 73-102 Principles of Microeconomics (9)

**FCE Hours**: 43, felt like 43

**Other Commitments**: Running and gym, club frisbee, social life

**Workload**: Light/moderate

## Spring 2021 (remote @ home)

* 15-122 Principles of Imperative Computation (12)

- 18-100 Introduction to Electrical and Computer Engineering (12)

- 76-101 Interpretation and Argument (9)

- 21-127 Concepts of Mathematics (12)

**Other Commitments**: Track training, gym, and this time, actually zero social life.

**Comments**: My worst semester "at" CMU, and probably the worst experience of my life.

## Fall 2020 (remote @ home)

- 21-259 Calculus in Three Dimensions (10)

- 15-112 Fundamentals of Programming and Computer Science (10)

- 24-101 Fundamentals of Mechanical Engineering (12)

- 39-109 Grand Challenge Freshman Seminar: Climate Change (9)

**Other Commitments**: Track training, gym, and no social life
except for my one hometown friend Evan who was also stuck at home like me.

**Comments**: Although I was bummed to be at home, the novelty of Zoom college had not worn out.

## Acknowledgements

I would like to give special thanks to my good friend [Evan Rovelli](https://erovelli.github.io/) who read over this post and gave me suggestions.
