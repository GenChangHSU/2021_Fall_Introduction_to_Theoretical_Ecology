

# Week 5 {-} 
<div style = "font-size: 28pt"> **_Age-structured models_**</div>

## Lecture in a nutshell {-}

<br>
<br>
<br>
<br>
<br>

## Lab demonstration {-}

In this lab, we will be analyzing a simple Leslie matrix using for loops and matrix algebra and visualizing the population dynamics (total population size and age distribution). We will also compare the for loops results with the results obtained via eigenanalysis.

**Part 1 - Analyzing Leslie matrix**


```r
library(tidyverse)

### Leslie matrix and initial age classes
leslie_mtrx <- matrix(data = c(0, 0, 10,
                               0.6, 0, 0,
                               0, 0.3, 0.1),
                      nrow = 3, 
                      ncol = 3,
                      byrow = T)

initial_age <- c(20, 0, 0)

### for loop and matrix algebra
time <- 150
pop_size <- data.frame(Age1 = numeric(time+1),
                       Age2 = numeric(time+1),
                       Age3 = numeric(time+1))
pop_size[1, ] <- initial_age

for (i in 1:time) {
  pop_size[i+1, ] <- leslie_mtrx %*% as.matrix(t(pop_size[i, ]))
}

pop_size <- pop_size %>% 
  round() %>%
  mutate(Total_N = rowSums(.), 
         Time = 0:time) %>%
  relocate(Time)

head(round(pop_size)) 
```

```
##   Time Age1 Age2 Age3 Total_N
## 1    0   20    0    0      20
## 2    1    0   12    0      12
## 3    2    0    0    4       4
## 4    3   36    0    0      36
## 5    4    4   22    0      26
## 6    5    0    2    6       8
```

```r
### Age distribution and asymptotic growth rate
asymptotic_growth <- round(pop_size[time+1, 4]/pop_size[time, 4], 3)
asymptotic_growth
```

```
## [1] 1.256
```

```r
age_distribution <- round(pop_size[time+1, 2:4]/sum(pop_size[time+1, 1:3]), 3)
age_distribution
```

```
##      Age1  Age2  Age3
## 151 0.674 0.326 0.085
```

```r
### Eigenanalysis of the Leslie matrix
eigen_out <- eigen(leslie_mtrx)
as.numeric(eigen_out$values[1]) %>% round(., 3)  # dominant eigenvalue
```

```
## [1] 1.251
```

```r
as.numeric(eigen_out$vectors[, 1]/sum(eigen_out$vectors[, 1])) %>% 
  round(., 3)  # stable age distribution
```

```
## [1] 0.623 0.299 0.078
```

The results are pretty much the same for both for loops and eigenanalysis.

<br>

**Part 2 - Visualizing population dynamics**


```r
### Total population size
ggplot(data = pop_size, aes(x = Time, y = Total_N)) + 
  geom_point() + 
  geom_line() + 
  labs(x = "time", y = expression(italic(N))) +
  theme_classic(base_size = 12) +
  scale_x_continuous(limits = c(0, time*1.05), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, max(pop_size$Total_N)*1.05), expand = c(0, 0))
```

<img src="05_Week_5_files/figure-html/unnamed-chunk-2-1.png" width="70%" style="display: block; margin: auto;" />

```r
### Age distribution
```
<br>

**Part 3 - Advanced topic: Incorporating density-dependence into Leslie matrix **


```r
library(tidyverse)

# Incorporate density-dependence transitions


# For loop and matrix algebra


# Visualize the results (animation of age distribution dynamics + total pop size)
```


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


