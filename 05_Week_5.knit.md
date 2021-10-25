

# Week 5 {-} 
<div style = "font-size: 28pt"> **_Age-structured models_**</div>

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

In this lab, we will be analyzing a simple Leslie matrix using for loops + matrix algebra, comparing the results with those obtained via eigenanalysis, and visualizing the population dynamics and age distribution.

**Part 1 - Analyzing Leslie matrix**


```r
library(tidyverse)

### Leslie matrix and initial age classes
leslie_mtrx <- matrix(data = c(0, 1, 5,
                               0.5, 0, 0,
                               0, 0.3, 0),
                      nrow = 3, 
                      ncol = 3,
                      byrow = T)

initial_age <- c(10, 0, 0)

### for loop and matrix algebra
time <- 50
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
## 1    0   10    0    0      10
## 2    1    0    5    0       5
## 3    2    5    0    2       7
## 4    3    8    2    0      10
## 5    4    2    4    1       7
## 6    5    8    1    1      10
```

```r
### Asymptotic growth rate and stable age distribution 
asymptotic_growth <- round(pop_size[time+1, 5]/pop_size[time, 5], 3)
asymptotic_growth
```

```
## [1] 1.091
```

```r
age_distribution <- round(pop_size[time+1, 2:4]/sum(pop_size[time+1, 2:4]), 3)
age_distribution
```

```
##     Age1  Age2  Age3
## 51 0.632 0.289 0.079
```

```r
### Eigenanalysis of the Leslie matrix
eigen_out <- eigen(leslie_mtrx)
as.numeric(eigen_out$values[1]) %>% round(., 3)  # dominant eigenvalue
```

```
## [1] 1.09
```

```r
as.numeric(eigen_out$vectors[, 1]/sum(eigen_out$vectors[, 1])) %>% 
  round(., 3)  # stable age distribution
```

```
## [1] 0.631 0.289 0.080
```

The asymptotic growth rate and stable age distribution obtained from for loops and eigenanalysis are pretty much the same.

<br>

**Part 2 - Visualizing population dynamics and age distribution**





