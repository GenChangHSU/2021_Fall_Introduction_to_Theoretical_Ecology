

# Week 2 {-} 
<div style = "font-size: 28pt"> **_Exponential population growth_**</div>

## Lecture in a nutshell {-}

* **Model derivation:** 
    1. Population growth rate: $Birth - Death + Immigration - Emigration$
    2. Per capita growth rate: $(birth - death + immigration - emigration)\times N$.

<div style="height:1px ;"><br></div>

* **Assumptions:**
    1. Closed population: $Immigration$ = $Emigration = 0$
    2. All individuals are identical: no genetic/age/stage structure
    3. Continuous population growth: no time lag
    4. Per capita birth and death rates are constant: time- and density-independent

<div style="height:1px ;"><br></div>

* **Solving the differential equation $\frac{dN}{dt} = (b-d)N$:**
    1. Use separation of variables and integrate both sides
    2. Plug in the initial condition $N_0$ at $t = 0$
    3. Integration result: $N_{(t)} = N_0e^{(b-d)t} = N_0e^{rt}$

<div style="height:1px ;"><br></div>

* **Related concept:**
    1. Doubling time $t_d = \frac{ln(2)}{r}$

<div style="height:1px ;"><br></div>

* **Average (expected) lifetime for an exponential decay function $N_{(t)} = N_0e^{-\delta t}$:**
    1. Probability density function (PDF): $\frac{N_0e^{-\delta t} - N_0e^{-\delta (t+\Delta t)}}{N_0} \approx \delta e^{-\delta t}$ (linear approximation)
    2. Expected value: $\int_{0}^{\infty}t\delta e^{-\delta t}dt$
    3. Use integration by parts to evaluate the integral
    4. Integration result: $\frac{1}{\delta}$

<div style="height:1px ;"><br></div>

* **Relaxation of assumption 1:**
    1. Net immigration/emigration is not zero: $\frac{dN}{dt} = rN + I_{(t)}$
    2. Solve the equation using the general solution to first-order linear differential equations

<div style="height:1px ;"><br></div>

* **Relaxation of assumption 4:**
    1. Per capita growth rate $r$ is not a constant but rather a function of time: $\frac{dN}{dt} = r_{(t)}N$
    2. An example of $r_{(t)}$: $r_{(t)} = \overline{r} + \frac{\sigma}{2}sin(\omega t + \phi)$
    3. Biological interpretation of $r_{(t)}$: seasonality, environmental fluctuations, etc.

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

<br>

## Assignments {-}

[Exponential Population Growth with Constant Immigration](./Assignments/Week2_Exponential Growth.pdf){target="_blank"}

[Suggested Solutions](./Assignments/Week2_Exponential Growth_with_Solutions.pdf){target="_blank"}






