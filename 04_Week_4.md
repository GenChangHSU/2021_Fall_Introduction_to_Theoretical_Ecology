

# Week 4 {-} 
<div style = "font-size: 28pt"> **_Discrete exponential and logistic models_**</div>

## Lecture in a nutshell {-}

<br>
<br>
<br>
<br>
<br>

## Lab demonstration {-}

In this lab, we are going to model the discrete logistic population growth and visualize the system dynamics. 

**Part 1 - Model the discrete logistic population growth using for loops**


```r
library(tidyverse)

### (1) Set the parameters
r <- 1.8
K <- 500
N0 <- 10
time <- 100

### (2) Define the discrete logistic growth equation
log_fun <- function(r, N, K){N + r*N*(1-N/K)}  

### (3) Use for loop to iterate over the time sequence
pop_size <- numeric(time)
pop_size[1] <- N0

for (i in 2:time) {pop_size[i] <- log_fun(r = r, N = pop_size[i - 1], K = K)}

pop_data <- pop_size %>% 
  as.data.frame() %>% 
  rename(., pop_size = `.`) %>%
  mutate(time = 0:(time-1)) %>%
  relocate(time)

head(pop_data)
```

```
##   time  pop_size
## 1    0  10.00000
## 2    1  27.64000
## 3    2  74.64171
## 4    3 188.93980
## 5    4 400.51775
## 6    5 543.95762
```

<br>

**Part 2. Visualize the population dynamics:**


```r
### Population trajectory
ggplot(pop_data, aes(x = time, y = pop_size)) + 
  geom_point() + 
  geom_line() +
  geom_hline(yintercept = K, color = "red", size = 1.2, linetype = "dashed") + 
  geom_text(x = time*1.02, y = K+50, label = "italic(K)", color = "red", size = 6.5, parse = T) +
  labs(y = expression(italic(N)), title = paste0("Discrete logistic growth", "\n", "(r = ", r, ", K = ", K, ", N0 = ", N0, ")")) + 
  scale_x_continuous(limits = c(0, time*1.05), expand = c(0, 0)) + 
  scale_y_continuous(limits = c(0, max(pop_size)*1.1), expand = c(0, 0)) + 
  theme_bw(base_size = 15) +
  theme(plot.title = element_text(hjust = 0.5))
```



\begin{center}\includegraphics[width=0.7\linewidth]{04_Week_4_files/figure-latex/unnamed-chunk-2-1} \end{center}

```r
### Cobweb plot/logistic map
cobweb_data <- data.frame(Nt = rep(pop_size[-time], each = 2)[-1], 
                          Nt1 = rep(pop_size[-1], each = 2)[-length(rep(pop_size[-1], each = 2))])

logistic_map <- data.frame(Nt = seq(0, (r+1)/r*K, by = 0.1)) %>%
  mutate(Nt1 = Nt + r*Nt*(1-Nt/K))

ggplot() + 
  geom_line(data = logistic_map, aes(x = Nt, y = Nt1), color = "green", size = 1.2) + 
  geom_path(data = cobweb_data, aes(x = Nt, y = Nt1), color = "blue", size = 0.5) + 
  geom_abline(slope = 1, intercept = 0, color = "red", size = 1) + 
  labs(x = expression(italic(N[t])),
       y = expression(italic(N[t+1])), 
       title = paste0("Cobweb plot/logistic map", "\n", "(r = ", r, ", K = ", K, ", N0 = ", N0, ")")) + 
  scale_x_continuous(limits = c(0, (r+1)/r*K*1.05), expand = c(0, 0)) + 
  scale_y_continuous(limits = c(0, max(pop_size)*1.1), expand = c(0, 0)) + 
  theme_bw(base_size = 15) +
  theme(plot.title = element_text(hjust = 0.5),
        panel.grid = element_blank())
```



\begin{center}\includegraphics[width=0.7\linewidth]{04_Week_4_files/figure-latex/unnamed-chunk-2-2} \end{center}
\*The name "logistic map" comes from the fact that it maps the population size at one time step *N~t~* to the value at the next time step *N~t+1~*.

<br>

<style>
iframe {border: 0;}
</style>

Here is a shiny app for the discrete logistic growth model. Feel free to play around with different inputs and see how the system dynamics change accordingly.

<iframe src="https://genchanghsu0115.shinyapps.io/Discrete_logistic_mod_shinyapp/?showcase=0" width="800px" height="750px" data-external="1"></iframe>

## Additional readings {-}

[Simple mathematical models with very complicated dynamics](./Additional readings/May_1976_Nature.pdf){target="_blank"}

<br>

## Assignments {-}

<br>
<br>
<br>
<br>
<br>


