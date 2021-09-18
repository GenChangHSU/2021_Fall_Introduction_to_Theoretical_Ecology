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

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px; text-align: center"> **IMPORTANT ANOUNCEMENT!!!** </p>
The first three weeks of this course will be online. We will host the two modules of this course (i.e., 2-hr lecture and 1-hr practice) on different platforms. We will use Google Meet for the lecture section [(link here)](https://meet.google.com/nzd-cdjp-kbt){target="_blank"}. To mimic an environment where we can provide one-on-one coding advice, we will use Gather Town for the hands-on practice section [(link here)](https://gather.town/app/osrqFSf0a7q0I6uo/TheoreticalEcology){target="_blank"}. Please login in advance to make sure it is working; learn how to use Gather Town [here](https://www.youtube.com/watch?v=89at5EvCEvk){target="_blank"}.

For those who wish to enroll manually, please join the first lecture and stay online afterward. Since we have moved to a larger classroom due to COVID-19 regulation, we can accommodate more students. We have asked students to introduce themselves (e.g., research interest and familiarity with R; 1-2 minutes) during the first time we meet online, so please also be prepared if you wish to enroll.

********************************************************************************

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Description** </p> The development of theory plays an important role in advancing ecology as a scientific field. This three-unit course is for students at the graduate or advanced undergraduate level. The course will cover classic theoretical topics in ecology, starting from single-species dynamics and gradually build up to multi-species models. The course will primarily focus on population and community ecology, but we will also briefly discuss models in epidemiology and ecosystem ecology. Emphasis will be on theoretical concepts and corresponding mathematical approaches.

This course is designed as a two-hour lecture followed by a one-hour hands-on practice module. In the lecture, we will analyze dynamical models and derive general theories in ecology. In the hands-on practice section, we will use a combination of analytical problem sets, interactive applications, and numerical simulations to gain a general understanding of the dynamics and behavior of different models. 

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Objectives** </p>
By the end of the course, students are expected to be familiar with the basic building blocks of ecological models and would be able to formulate and analyze simple models of their own. The hands-on practice component should allow students to link their ecological intuition with the underlying mathematical model, helping them to better understand the primary literature of theoretical ecology. 

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Requirements** </p>
Students are expected to have a basic understanding of **Calculus** (e.g., freshman introductory course) and **Ecology**.

<p style = "font-size: 24pt; margin-bottom: 5px; margin-top: 25px"> **Format** </p>
Tuesday 1:20 pm ~ 4:20 pm at Classroom 3C, Life Science Building

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
           <br> 28-Sept-2021 & Introduction: what is theoretical ecology? &  & Grainger et al., 2021\\
\hline
**Week 2** <span style='vertical-align:-30%'> </span>
           <br> 05-Oct-2021 & Exponential population growth & Solving exponential growth equation using "deSolve" & Visualization & Gotelli [Ch.1] <br> Case [Ch.1]\\
\hline
**Week 3** <span style='vertical-align:-30%'> </span>
           <br> 12-Oct-2021 & Density-dependence and logistic population growth & Solving logistic growth equation using "deSolve" & Visualization & Gotelli [Ch.2] <br> Case [Ch.5]\\
\hline
**Week 4** <span style='vertical-align:-30%'> </span>
           <br> 19-Oct-2021 & Stability analysis of single population dynamics &  & Otto & Day [Ch.5]\\
\hline
**Week 5** <span style='vertical-align:-30%'> </span>
           <br> 26-Oct-2021 & Geometric growth and age-structured population models &  & Gotelli [Ch.3] <br> Case[Ch.3]\\
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
\end{tabu}
\endgroup{}



<!--chapter:end:index.Rmd-->

# Week 1 {-} 
<div style = "font-size: 28pt"> **_Introduction: what is theoretical ecology?_**</div>

## Lecture in a nutshell {-}

[Lecture handout](./Lecture handouts/Week1_Lecture_What_Is_Theoretical_Ecology.pdf){target="_blank"}

* Introduction to ecological theories and mathematical models

* Constructing ecological models: 5 steps

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Step 1_**. Formulate the motivating question</span>

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Step 2_**. Determine the basic ingredients</span>

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Step 3_**. Qualitatively describe the biological system</span>

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Step 4_**. Quantitatively describe the biological system</span>

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Step 5_**. Analyze the model</span>

* Apply ecological models in your study: 4 approaches

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Approach 1_**. Adopt the framework</span>

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Approach 2_**. Test the predictions</span>

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Approach 3_**. Use the equations (model fitting/proxy calculation)</span>

<span style="display: block; margin-top: -10px; margin-left: 50px">**_Approach 4_**. Test model assumptions</span>

* Some relevant math techniques: Derivatives and Taylor expansion

## Lab demonstration {-}

No lab demonstration this week.

## Additional readings {-}

[Grainger et al. (2021). An empiricist’s guide to using ecological theory. *American Naturalist*.](./Additional readings/Week1_Reading_Grainger_et_al_2021_AmNat.pdf){target="_blank"} 

## Assignments {-}

Please review the study material and make sure you understand the basic R syntax and programming fundamentals, which we will be using throughout the semester. The example dataset for the tutorial is provided below. 

[Basic Introduction to R](./Assignments/Week1_Basic Introduction to R.pdf){target="_blank"}

[Example dataset](./Assignments/example_dat.txt){target="_blank"}

<br>






<!--chapter:end:01_Week_1.Rmd-->



# Week 2 {-} 
<div style = "font-size: 28pt"> **_Exponential population growth_**</div>

## Lecture in a nutshell {-}

<br>
<br>
<br>
<br>
<br>

## Lab demonstration {-}

In this lab, we will be solving the differential equation for exponential population growth (Part 1) and visualize how the population sizes change over time (Part 2). 

<br>

**Part 1 - Numerical solution using the package "deSolve"**

Two main phases:

<span id = "aaa" style="display: block; margin-top: -10px; margin-left: 50px">Model specification: specify the structure of differential equation model</span>

<span id = "bbb" style="display: block; margin-top: -10px; margin-left: 50px">Model application: set the time steps, initial population size, model parameters (e.g., intrinsic population growth rate *r*) and solve the equation</span>

<style>

p span#aaa:before { 
  content: "(1) "; 
  display: inline-block;
  margin-left: -1.5em;
  margin-right: 0.3em;
}

p span#bbb:before { 
  content: "(2) "; 
  display: inline-block;
  margin-left: -1.5em;
  margin-right: 0.3em;
}

d-article table.lightable-paper {
  margin-bottom: 0px; 
}

</style>


```r
# install.packages("deSolve")
library(deSolve)

### (1) Model specification
exponential_model <- function(times, state, parms) {
  with(as.list(c(state, parms)), {
    dN_dt = r*N  # exponential growth equation
    return(list(c(dN_dt)))  # return the results  
  })
}

### (2) Model application
times <- seq(0, 10, by = 0.1)  # time steps to integrate over
state <- c(N = 10)  # initial population size
parms <- c(r = 1.5)  # intrinsic growth rate

# run the ode solver
pop_size <- ode(func = exponential_model, times = times, y = state, parms = parms)

# take a look at the results
head(pop_size)
```

```
##      time        N
## [1,]  0.0 10.00000
## [2,]  0.1 11.61834
## [3,]  0.2 13.49860
## [4,]  0.3 15.68313
## [5,]  0.4 18.22120
## [6,]  0.5 21.17002
```

<br>

**Part 2. Visualize the integration results:**

Linear scale

```r
# install.packages("tidyverse")
library(tidyverse)

ggplot(data = as.data.frame(pop_size), aes(x = time, y = N)) + 
  geom_point() + 
  labs(title = paste0("Exponential Growth \n (r = ", parms["r"], ")")) +
  theme_classic(base_size = 12) + 
  theme(plot.title = element_text(hjust = 0.5)) +
  scale_x_continuous(limits = c(0, 10.5), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, max(as.data.frame(pop_size)$N)*1.1), expand = c(0, 0))
```



\begin{center}\includegraphics[width=0.7\linewidth]{02_Week_2_files/figure-latex/unnamed-chunk-2-1} \end{center}
<br>

Log scale

```r
ggplot(data = as.data.frame(pop_size), aes(x = time, y = N)) + 
  geom_point() + 
  labs(title = paste0("Exponential Growth \n (r = ", parms["r"], ")")) +
  theme_classic(base_size = 12) + 
  theme(plot.title = element_text(hjust = 0.5)) + 
  scale_x_continuous(limits = c(0, 10.5), expand = c(0, 0)) +
  scale_y_log10(breaks = scales::trans_breaks("log10", function(x) 10^x)(c(10, 10^7)),
                labels = scales::trans_format("log10", scales::math_format(10^.x)),
                expand = c(0, 0))
```



\begin{center}\includegraphics[width=0.7\linewidth]{02_Week_2_files/figure-latex/unnamed-chunk-3-1} \end{center}
<br>

## Additional readings {-}

[Package deSolve: Solving Initial Value Differential Equations in R](./Additional readings/Package deSolve - Solving Initial Value Differential Equations in R.pdf){target="_blank"}

## Assignments {-}



<!--chapter:end:02_Week_2.Rmd-->



# Week 3 {-} 
<div style = "font-size: 28pt"> **_Density-dependence and logistic population growth_**</div>

## Lecture in a nutshell {-}

<br>
<br>
<br>
<br>
<br>

## Lab demonstration {-}

In this lab, we will solve the differential equation for logistic population growth and visualize how the population sizes change over time. Have a quick review of the [lab section](https://genchanghsu.github.io/2021_Fall_Introduction_to_Theoretical_Ecology/week-2.html#lab-demonstration-1){target="_blank"} in Week 2.

We will also take a look at how population growth rate ($\frac{dN}{dt}$) and per capita growth rate ($\frac{dN}{dtN}$) change with population size ($N$). 
<br>
<br>

**Part 1 - Solving the logistic growth equation and visualize the results**


```r
library(tidyverse)
library(deSolve)

### Model specification
logistic_model <- function(times, state, parms) {
  with(as.list(c(state, parms)), {
    dN_dt = r*N*(K-N)/K  # logistic growth equation
    return(list(c(dN_dt)))  # return the results  
  })
}

### Model application
times <- seq(0, 10, by = 0.1)  # time steps to integrate over
state <- c(N = 10)  # initial population size
parms <- c(r = 1.5, K = 500)  # intrinsic growth rate and carrying capacity

# run the ode solver
pop_size <- ode(func = logistic_model, times = times, y = state, parms = parms)

### Visualize the results
ggplot(data = as.data.frame(pop_size), aes(x = time, y = N)) + 
  geom_point() + 
  labs(title = paste0("Logistic Growth \n (r = ", parms["r"], ", K = ", parms["K"], ")")) +
  theme_classic(base_size = 12) + 
  theme(plot.title = element_text(hjust = 0.5)) +
  scale_x_continuous(limits = c(0, 10.5), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, max(as.data.frame(pop_size)$N)*1.1), expand = c(0, 0))
```



\begin{center}\includegraphics[width=0.7\linewidth]{03_Week_3_files/figure-latex/unnamed-chunk-1-1} \end{center}
<br>

Here is an interactive web app for the logistic growth model. Feel free to play around with the parameters/values and see how the population trajectories change.


\href{https://genchanghsu0115.shinyapps.io/Logistic_mod_shinyapp/}{\includegraphics[width=800px]{03_Week_3_files/figure-latex/unnamed-chunk-2-1} }

<br>

**Part 2 - The relationship between population growth rate ($\frac{dN}{dt}$)/per capita growth rate ($\frac{dN}{dtN}$) and population size ($N$)**


```r
# parameters
r <- 1.5
K <- 500

# a vector of population sizes
N <- 0:600

# calculate the population growth rates and per capita growth rates
dN_dt <- r*N*(K-N)/K 
dN_dtN <- r*(K-N)/K

# organize into a dataframe
logistic_data <- data.frame(N, dN_dt, dN_dtN) %>%
  pivot_longer(cols = c(dN_dt, dN_dtN), 
               names_to = "vars", 
               values_to = "values")

# plot 
K_df <- data.frame(xend = c(500, 500),
                   yend = c(20, 0.1),
                   xstart = c(500, 500),
                   ystart = c(100, 0.5),
                   labels = c("italic(K)", "italic(K)"),
                   vars = c("dN_dt", "dN_dtN"))

ggplot(data = logistic_data, aes(x = N, y = values)) + 
  geom_line(size = 1.2) + 
  geom_point(x = 500, y = 0, size = 4, color = "blue") +
  geom_hline(yintercept = 0, linetype = "dashed", color = "red", size = 1.2) +
  labs(x = "N", y = "") +
  facet_wrap(~vars, 
             ncol = 2, 
             scales = "free_y",
             strip.position = "left", 
             labeller = as_labeller(c(dN_dt = "dN/dt", 
                                      dN_dtN = "dN/dtN"))) + 
  theme_bw(base_size = 12) +
  theme(strip.background = element_blank(),
        strip.placement = "outside",
        legend.position = "top",
        legend.title = element_blank()) + 
  scale_x_continuous(limits = c(0, 610), expand = c(0, 0)) + 
  geom_segment(data = K_df, 
               aes(x = xstart, y = ystart, xend = xend, yend = yend), 
               arrow = arrow(length = unit(0.03, "npc")), 
               size = 1.2,
               color = "blue") + 
  geom_text(data = K_df, 
            aes(x = xstart, y = ystart*1.2, label = labels),
            size = 5, 
            color = "blue",
            parse = T)
```



\begin{center}\includegraphics[width=0.95\linewidth]{03_Week_3_files/figure-latex/unnamed-chunk-3-1} \end{center}

<br>

## Additional readings {-}

[Logistic Growth](http://equation-of-the-month.blogspot.com/2012/01/logistic-growth.html){target="_blank"}

<br>

## Assignments {-}



<!--chapter:end:03_Week_3.Rmd-->

# Week 4 {-} 
<div style = "font-size: 28pt"> **_Stability analysis of single population dynamics_**</div>

## Lecture in a nutshell {-}

<br>
<br>
<br>
<br>
<br>

## Lab demonstration {-}

<br>
<br>
<br>
<br>
<br>

## Additional readings {-}

<br>
<br>
<br>
<br>
<br>

## Assignments {-}

<br>
<br>
<br>
<br>
<br>



<!--chapter:end:04_Week_4.Rmd-->

