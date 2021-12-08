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

Placeholder



<!--chapter:end:index.Rmd-->


# Week 1 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:01_Week_1.Rmd-->


# Week 2 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:02_Week_2.Rmd-->


# Week 3 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:03_Week_3.Rmd-->


# Week 4 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:04_Week_4.Rmd-->


# Week 5 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:05_Week_5.Rmd-->


# Week 6 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:06_Week_6.Rmd-->


# Week 7 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:07_Week_7.Rmd-->


# Week 8 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:08_Week_8.Rmd-->



# Week 9 {-} 
<div style = "font-size: 28pt"> **_Midterm_**</div>

<div style="height:1px ;"><br></div>

[Midterm](./Assignments/Week9_Midterm.pdf){target="_blank"}

<div style="height:1px ;"><br></div>

[Suggested Solutions](./Assignments/Week9_Midterm_with_Solutions.pdf){target="_blank"}



<!--chapter:end:09_Week_9.Rmd-->


# Week 10 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:10_Week_10.Rmd-->


# Week 11 {-} 

Placeholder


## Lecture in a nutshell {-}
## Lab demonstration {-}
### Special topic: time-scale separation {-}
## Additional readings {-}
## Assignments {-}

<!--chapter:end:11_Week_11.Rmd-->



# Week 12 {-} 
<div style = "font-size: 28pt"> **_Resource competition: R* models_**</div>

## Lecture in a nutshell {-}

* **Topic:**
    1. 
    2. 
    3. 
    
<div style="height:1px ;"><br></div>

* **Topic:**
    1. 
    2. 
    3.

<div style="height:1px ;"><br></div>    
<br>


## Lab demonstration {-}

### Part 1 - R* rule {-}
Similar to what we've done in the previous class, in this lab we are going to analyze the Rosenzweig–MacArthur predator–prey model:

<div style="margin-left: 30%;">$\begin{align}\frac {dN}{dt} = rN(1-\frac{N}{K})-a\frac{N}{1+ahN}P\end{align}\\$</div>
<div style="margin-left: 30%; margin-bottom: 10px;">$\begin{align}\frac {dP}{dt} = ea\frac{N}{1+ahN}P-dP\end{align}$</div>

Please simulate the model using the parameter set (_N_ = 5, _P_ = 2, _r_ = 1.0, _K_ = 5.0, _a_ = 1.3, _h_ = 0.9, _e_ = 0.6, _d_ = 0.5) and plot the population trajectories of predator and prey as well as show their population dynamics in the state-space diagram.

What will happen if you add a perturbation to the system (i.e., change the initial conditions)? Try out different values of _N_ and _P_ and visualize the differences in the state-space diagram. Also compare the results of the Rosenzweig–MacArthur model and the original Lotka-Volterra model. What do you find regarding the final equilibrium cycles?


```r
library(tidyverse)
library(deSolve)

### Model specification
RM_predation_model <- function(times, state, parms) {
  with(as.list(c(state, parms)), {
    dN_dt = r*N*(1-(N/K))-(a*N/(1+a*h*N))*P
    dP_dt = e*(a*N/(1+a*h*N))*P-d*P
    return(list(c(dN_dt, dP_dt)))  
  })
}

### Model parameters
times <- seq(0, 200, by = 0.01)  
state <- c(N = 5, P = 2)  
parms <- c(r = 1.0, K = 5.0, a = 1.3, h = 0.9, e = 0.6, d = 0.5) 

### Model application
pop_size <- ode(func = RM_predation_model, times = times, y = state, parms = parms)

### Visualize the population dynamics
# (1) population trajectories
pop_size %>%
  as.data.frame() %>%
  pivot_longer(cols = -time, names_to = "species", values_to = "N") %>%
  ggplot(aes(x = time, y = N, color = species)) + 
  geom_line(size = 1.5) +
  theme_classic(base_size = 12) +
  labs(x = "Time", y = "Population size") +
  scale_x_continuous(limits = c(0, 200.5), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, max(pop_size[, -1])*1.2), expand = c(0, 0)) +
  scale_color_brewer(name = NULL, palette = "Set1", labels = c("Prey", "Predator"), direction = -1)
```

<img src="12_Week_12_files/figure-html/unnamed-chunk-1-1.png" width="70%" style="display: block; margin: auto;" />

```r
# (2) state-space diagram
pop_size %>%
  as.data.frame() %>%
  ggplot(aes(x = N, y = P)) + 
  geom_path() + 
  geom_vline(xintercept = with(as.list(parms), d/(e*a-a*d*h)), color = "#E41A1C", size = 1) +
  geom_function(data = data.frame(x = seq(0, 5, 0.01)), aes(x = x), fun = function(n){with(as.list(parms), r*(1+a*h*n)*(1-n/K)/a)}, inherit.aes = F, color = "#377EB8", size = 1) + 
  geom_point(aes(x = tail(N, 1), y = tail(P, 1)), size = 2) +
  theme_classic(base_size = 14) +
  theme(axis.line.x = element_line(color = "#E41A1C", size = 1),
        axis.line.y = element_line(color = "#377EB8", size = 1)) + 
  labs(x = "Prey", y = "Predator") + 
  scale_x_continuous(limits = c(0, max(pop_size[, "N"]*1.05)), expand = c(0, 0)) + 
  scale_y_continuous(limits = c(0, max(pop_size[, "P"]*1.05)), expand = c(0, 0)) 
```

<img src="12_Week_12_files/figure-html/unnamed-chunk-1-2.png" width="70%" style="display: block; margin: auto;" />

<br>

### Part 2 - Tilman’s resource ratio hypothesis {-}


```r
library(tidyverse)
library(deSolve)

### Model specification
RM_predation_model <- function(times, state, parms) {
  with(as.list(c(state, parms)), {
    dN_dt = r*N*(1-(N/K))-(a*N/(1+a*h*N))*P
    dP_dt = e*(a*N/(1+a*h*N))*P-d*P
    return(list(c(dN_dt, dP_dt)))  
  })
}

### Model parameters
times <- seq(0, 200, by = 0.01)  
state <- c(N = 5, P = 2)  
parms <- c(r = 1.0, K = 5.0, a = 1.3, h = 0.9, e = 0.6, d = 0.5) 

### Model application
pop_size <- ode(func = RM_predation_model, times = times, y = state, parms = parms)

### Visualize the population dynamics
# (1) population trajectories
pop_size %>%
  as.data.frame() %>%
  pivot_longer(cols = -time, names_to = "species", values_to = "N") %>%
  ggplot(aes(x = time, y = N, color = species)) + 
  geom_line(size = 1.5) +
  theme_classic(base_size = 12) +
  labs(x = "Time", y = "Population size") +
  scale_x_continuous(limits = c(0, 200.5), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, max(pop_size[, -1])*1.2), expand = c(0, 0)) +
  scale_color_brewer(name = NULL, palette = "Set1", labels = c("Prey", "Predator"), direction = -1)
```

<img src="12_Week_12_files/figure-html/unnamed-chunk-2-1.png" width="70%" style="display: block; margin: auto;" />

```r
# (2) state-space diagram
pop_size %>%
  as.data.frame() %>%
  ggplot(aes(x = N, y = P)) + 
  geom_path() + 
  geom_vline(xintercept = with(as.list(parms), d/(e*a-a*d*h)), color = "#E41A1C", size = 1) +
  geom_function(data = data.frame(x = seq(0, 5, 0.01)), aes(x = x), fun = function(n){with(as.list(parms), r*(1+a*h*n)*(1-n/K)/a)}, inherit.aes = F, color = "#377EB8", size = 1) + 
  geom_point(aes(x = tail(N, 1), y = tail(P, 1)), size = 2) +
  theme_classic(base_size = 14) +
  theme(axis.line.x = element_line(color = "#E41A1C", size = 1),
        axis.line.y = element_line(color = "#377EB8", size = 1)) + 
  labs(x = "Prey", y = "Predator") + 
  scale_x_continuous(limits = c(0, max(pop_size[, "N"]*1.05)), expand = c(0, 0)) + 
  scale_y_continuous(limits = c(0, max(pop_size[, "P"]*1.05)), expand = c(0, 0)) 
```

<img src="12_Week_12_files/figure-html/unnamed-chunk-2-2.png" width="70%" style="display: block; margin: auto;" />

<br>

### Part 3 - Relative nonlinearity {-}


```r
library(tidyverse)
library(deSolve)

### Model specification
RM_predation_model <- function(times, state, parms) {
  with(as.list(c(state, parms)), {
    dN_dt = r*N*(1-(N/K))-(a*N/(1+a*h*N))*P
    dP_dt = e*(a*N/(1+a*h*N))*P-d*P
    return(list(c(dN_dt, dP_dt)))  
  })
}

### Model parameters
times <- seq(0, 200, by = 0.01)  
state <- c(N = 5, P = 2)  
parms <- c(r = 1.0, K = 5.0, a = 1.3, h = 0.9, e = 0.6, d = 0.5) 

### Model application
pop_size <- ode(func = RM_predation_model, times = times, y = state, parms = parms)

### Visualize the population dynamics
# (1) population trajectories
pop_size %>%
  as.data.frame() %>%
  pivot_longer(cols = -time, names_to = "species", values_to = "N") %>%
  ggplot(aes(x = time, y = N, color = species)) + 
  geom_line(size = 1.5) +
  theme_classic(base_size = 12) +
  labs(x = "Time", y = "Population size") +
  scale_x_continuous(limits = c(0, 200.5), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, max(pop_size[, -1])*1.2), expand = c(0, 0)) +
  scale_color_brewer(name = NULL, palette = "Set1", labels = c("Prey", "Predator"), direction = -1)
```

<img src="12_Week_12_files/figure-html/unnamed-chunk-3-1.png" width="70%" style="display: block; margin: auto;" />

```r
# (2) state-space diagram
pop_size %>%
  as.data.frame() %>%
  ggplot(aes(x = N, y = P)) + 
  geom_path() + 
  geom_vline(xintercept = with(as.list(parms), d/(e*a-a*d*h)), color = "#E41A1C", size = 1) +
  geom_function(data = data.frame(x = seq(0, 5, 0.01)), aes(x = x), fun = function(n){with(as.list(parms), r*(1+a*h*n)*(1-n/K)/a)}, inherit.aes = F, color = "#377EB8", size = 1) + 
  geom_point(aes(x = tail(N, 1), y = tail(P, 1)), size = 2) +
  theme_classic(base_size = 14) +
  theme(axis.line.x = element_line(color = "#E41A1C", size = 1),
        axis.line.y = element_line(color = "#377EB8", size = 1)) + 
  labs(x = "Prey", y = "Predator") + 
  scale_x_continuous(limits = c(0, max(pop_size[, "N"]*1.05)), expand = c(0, 0)) + 
  scale_y_continuous(limits = c(0, max(pop_size[, "P"]*1.05)), expand = c(0, 0)) 
```

<img src="12_Week_12_files/figure-html/unnamed-chunk-3-2.png" width="70%" style="display: block; margin: auto;" />







## Additional readings {-}

[Competitive Exclusion](./Additional readings/Armstrong_&_McGehee_1980_AmNat.pdf){target="_blank"}

[A Graphical-Mechanistic Approach to Competition and Predation](./Additional readings/Tilman_1980_AmNat.pdf){target="_blank"}

<br>

## Assignments {-}

[Apparent Competition and P* Rule](./Assignments/Week12_Apparent Competition.pdf){target="_blank"}



<!--chapter:end:12_Week_12.Rmd-->

