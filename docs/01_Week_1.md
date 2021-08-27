# Week 1{-}

Figure with label and caption

```r
par(mar = c(4, 4, .1, .1))
plot(pressure, type = 'b', pch = 19)
```

<div class="figure" style="text-align: center">
<img src="01_Week_1_files/figure-html/nice-fig-1.png" alt="Here is a nice figure!" width="80%" />
<p class="caption">(\#fig:nice-fig)Here is a nice figure!</p>
</div>

External image with label and caption

```r
knitr::include_graphics("knit-logo.png")
```

<div class="figure" style="text-align: center">
<img src="knit-logo.png" alt="Here is a nice figure!" width="80%" />
<p class="caption">(\#fig:nice-fig2)Here is a nice figure!</p>
</div>

Table with label and caption

```r
knitr::kable(
  head(iris, 20), caption = 'Here is a nice table!',
  booktabs = TRUE
)
```



Table: (\#tab:nice-tab)Here is a nice table!

| Sepal.Length| Sepal.Width| Petal.Length| Petal.Width|Species |
|------------:|-----------:|------------:|-----------:|:-------|
|          5.1|         3.5|          1.4|         0.2|setosa  |
|          4.9|         3.0|          1.4|         0.2|setosa  |
|          4.7|         3.2|          1.3|         0.2|setosa  |
|          4.6|         3.1|          1.5|         0.2|setosa  |
|          5.0|         3.6|          1.4|         0.2|setosa  |
|          5.4|         3.9|          1.7|         0.4|setosa  |
|          4.6|         3.4|          1.4|         0.3|setosa  |
|          5.0|         3.4|          1.5|         0.2|setosa  |
|          4.4|         2.9|          1.4|         0.2|setosa  |
|          4.9|         3.1|          1.5|         0.1|setosa  |
|          5.4|         3.7|          1.5|         0.2|setosa  |
|          4.8|         3.4|          1.6|         0.2|setosa  |
|          4.8|         3.0|          1.4|         0.1|setosa  |
|          4.3|         3.0|          1.1|         0.1|setosa  |
|          5.8|         4.0|          1.2|         0.2|setosa  |
|          5.7|         4.4|          1.5|         0.4|setosa  |
|          5.4|         3.9|          1.3|         0.4|setosa  |
|          5.1|         3.5|          1.4|         0.3|setosa  |
|          5.7|         3.8|          1.7|         0.3|setosa  |
|          5.1|         3.8|          1.5|         0.3|setosa  |

[Internal Link to anchor](#abcd)


## Equations {- #equations}
$f(k) = {n \choose k} p^{k} (1-p)^{n-k}$

$$f(k) = {n \choose k} p^{k} (1-p)^{n-k}$$

$$\begin{vmatrix}a & b\\
c & d
\end{vmatrix}=ad-bc$$

\begin{equation} 
  f\left(k\right) = \binom{n}{k} p^k\left(1-p\right)^{n-k}
  (\#eq:binom)
\end{equation} 

\begin{equation*} 
\frac{d}{dx}\left( \int_{a}^{x} f(u)\,du\right)=f(x)
\end{equation*} 


Text references

(ref:foo) A scatterplot of the data `cars` using **base** R graphics. 


```r
plot(cars)  # a scatterplot
```

<div class="figure">
<img src="01_Week_1_files/figure-html/foo-1.png" alt="(ref:foo)" width="672" />
<p class="caption">(\#fig:foo)(ref:foo)</p>
</div>


<a name="abcd"></a>
see this!!!
