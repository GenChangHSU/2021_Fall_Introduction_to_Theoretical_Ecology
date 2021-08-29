--- 
title: "Introduction to Theoretical Ecology"
author: "Instructor: Po-Ju Ke $~~~~~$ Teaching Assistant: Gen-Chang Hsu"
date: "2021 Fall at National Taiwan Univeristy ![](./bifurcation.gif)"

url: "https://genchanghsu.github.io/2021_Fall_Introduction_to_Theoretical_Ecology/"
github-repo: "GenChangHSU/2021_Fall_Introduction_to_Theoretical_Ecology"
cover-image: "bifurcation.gif"

site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
biblio-style: apalike
link-citations: yes

description: "This is the course website for **_Introduction to Theoretical Ecology_** 2021 Fall at National Taiwan University."
---



# Course Information {-}

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Description** </p> The development of theory plays an important role in advancing ecology as a scientific field. This three-unit course is for students at the graduate or advanced undergraduate level. The course will cover classic theoretical topics in ecology, starting from single-species dynamics and gradually build up to multi-species models. The course will primarily focus on population and community ecology, but we will also briefly discuss models in epidemiology and ecosystem ecology. Emphasis will be on theoretical concepts and corresponding mathematical approaches.

This course is designed as a two-hour lecture followed by a one-hour hands-on practice module. In the lecture, we will analyze dynamical models and derive general theories in ecology. In the hands-on practice section, we will use a combination of analytical problem sets, interactive applications, and numerical simulations to gain a general understanding of the dynamics and behavior of different models. 

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Objectives** </p>
By the end of the course, students are expected to be familiar with the basic building blocks of ecological models and would be able to formulate and analyze simple models of their own. The hands-on practice component should allow students to link their ecological intuition with the underlying mathematical model, helping them to better understand the primary literature of theoretical ecology. 

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Requirements** </p>
Students are expected to have a basic understanding of **Calculus** (e.g., freshman introductory course) and **Ecology**.

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Format** </p>
Tuesday 1:20 pm ~ 4:20 pm at Room 204, Gongtong Lecture Building

- Lecture (two hours): selected topics of ecological theories and models (blackboard writing) 
- Lab (one hour): hands-on practice in programming and simulation (using R) + discussion

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Grading** </p>
The final grade consists of:

(1) Assignment problem sets (60%)
(2) Midterm exam (15%)
(3) Final exam (15%)
(4) Course participation (10%)

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Course materials** </p>
We will be using a combination of textbooks and literature articles on theoretical ecology in this course. Textbook chapters and additional reading materials will be provided (see **Syllabus** for more details).

Below are the textbook references:

- Case, Ted J. *An illustrated guide to theoretical ecology*. Oxford University Press, 2000.
- Gotelli, Nicholas J. *A primer of ecology 4^th^ edition*. Sinauer Associates, 2008.
- Pastor, John. *Mathematical ecology of populations and ecosystems*. John Wiley & Sons, 2011.
- Otto, Sarah P. and Troy Day. *A biologist's guide to mathematical modeling in ecology and evolution*. Princeton University Press, 2011.

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Contacts** </p>
**Instructor**: Po-Ju Ke

- Office: Life Science Building R635
- Email: pojuke@ntu.edu.tw
- Office hours: by appointment

**Teaching assistant**: Gen-Chang Hsu

- Email: b04b01065@ntu.edu.tw
- Office hours: by appointment


# Syllabus {-}

\begingroup\fontsize{17}{19}\selectfont

\begin{tabu} to \linewidth {>{\centering}X>{\centering}X>{\centering}X>{\raggedright}X}
\hline
\begingroup\fontsize{20}{22}\selectfont \textcolor{black}{\textbf{Date}}\endgroup & \begingroup\fontsize{20}{22}\selectfont \textcolor{black}{\textbf{Lecture topic}}\endgroup & \begingroup\fontsize{20}{22}\selectfont \textcolor{black}{\textbf{Lab}}\endgroup & \begingroup\fontsize{20}{22}\selectfont \textcolor{black}{\textbf{Reading}}\endgroup\\
\hline
**Week 1** <span style='vertical-align:-30%'> </span>
           <br> 28-Sept-2021 & Introduction: what is theoretical ecology? &  & \\
\hline
**Week 2** <span style='vertical-align:-30%'> </span>
           <br> 05-Oct-2021 & Exponential and geometric population growth &  & Gotelli [Ch.1] <br> Case [Ch.1]\\
\hline
**Week 3** <span style='vertical-align:-30%'> </span>
           <br> 12-Oct-2021 & Age-structured population models &  & Gotelli [Ch.3] <br> Case [Ch.3]\\
\hline
**Week 4** <span style='vertical-align:-30%'> </span>
           <br> 19-Oct-2021 & Density-dependence and logistic population growth &  & Gotelli [Ch.2] <br> Case [Ch.5]\\
\hline
**Week 5** <span style='vertical-align:-30%'> </span>
           <br> 26-Oct-2021 & Stability analysis of single population dynamics &  & Otto & Day [Ch.5]\\
\hline
**Week 6** <span style='vertical-align:-30%'> </span>
           <br> 02-Nov-2021 & Metapopulations and patch occupancy models &  & Gotelli [Ch.4] <br> Case [Ch.16]\\
\hline
**Week 7** <span style='vertical-align:-30%'> </span>
           <br> 09-Nov-2021 & Lotka-Volterra model of competition: graphical analysis &  & Gotelli [Ch.5] <br> Case [Ch.14]\\
\hline
**Week 8** <span style='vertical-align:-30%'> </span>
           <br> 16-Nov-2021 & Lotka-Volterra model of competition: linear stability analysis &  & Otto & Day [Ch.8]\\
\hline
**Week 9** <span style='vertical-align:-30%'> </span>
           <br> 23-Nov-2021 & Midterm exam &  & \\
\hline
**Week 10** <span style='vertical-align:-30%'> </span>
           <br> 30-Nov-2021 & Predator-prey interactions &  & Gotelli [Ch.6] <br> Case [Ch.12 & 13]\\
\hline
**Week 11** <span style='vertical-align:-30%'> </span>
           <br> 07-Dec-2021 & Mutualisms &  & Vandermeer & Boucher, 1978.\\
\hline
**Week 12** <span style='vertical-align:-30%'> </span>
           <br> 14-Dec-2021 & Multispecies models of competition: apparent and exploitative competition &  & Holt, 1977.\\
\hline
**Week 13** <span style='vertical-align:-30%'> </span>
           <br> 21-Dec-2021 & Multispecies models of predation: food chains and intraguild predation &  & Holt & Polis, 1997.\\
\hline
**Week 14** <span style='vertical-align:-30%'> </span>
           <br> 28-Dec-2021 & Disease dynamics and SIR models &  & Anderson & May, 1979.\\
\hline
**Week 15** <span style='vertical-align:-30%'> </span>
           <br> 04-Jan-2022 & Ecosystem models and feedbacks &  & Pastor [Ch.11 & 12]\\
\hline
**Week 16** <span style='vertical-align:-30%'> </span>
           <br> 11-Jan-2022 & Final exam &  & \\
\hline
**Week 17** <span style='vertical-align:-30%'> </span>
           <br> 18-Jan-2022 & General discussion: how to develop new theoretical models and the role of theory in modern ecology? &  & Otto & Day [Ch.2] <br> Otto & Rosales, 2020.\\
\hline
\end{tabu}
\endgroup{}



<!--chapter:end:index.Rmd-->

# Week 1 {-} 
<div style = "font-size: 28pt"> **Introduction: what is theoretical ecology?**</div>

<!--chapter:end:01_Week_1.Rmd-->

# Week 2 {-} 
<div style = "font-size: 28pt"> **Exponential and geometric population growth**</div>



<!--chapter:end:02_Week_2.Rmd-->

