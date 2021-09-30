

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

<br>

## Assignments {-}

[Exponential Population Growth with Constant Immigration](./Assignments/Week2_Exponential Growth.pdf){target="_blank"}








