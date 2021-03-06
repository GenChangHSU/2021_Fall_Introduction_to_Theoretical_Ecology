

# Week 8 {-} 
<div style = "font-size: 28pt"> **_Lotka-Volterra model of competition: linear stability analysis_**</div>

## Lecture in a nutshell {-}

* **The differential equations**
    * $f_{A}(N_{A}, N_{B}) = \frac {dN_{A}}{dt} = N_{A}(r_{A}-\alpha_{AA}N_{A}-\alpha_{AB}N_{B})$
    * $f_{B}(N_{A}, N_{B}) = \frac {dN_{B}}{dt} = N_{B}(r_{B}-\alpha_{BB}N_{B}-\alpha_{BA}N_{A})$

<div style="height:1px ;"><br></div> 

* **Analytical analysis (1): Invasion analysis**
    1. Idea: can a species invade the other's equilibrium?
    2. Invasion growth rate (IGR): the growth rate of focal species when rare 
    $IGR_{i} =  \lim_{N_{i} \to 0} \frac {1}{N_{i}} \frac {dN_{i}}{dt}|_{N_{j}}$
        * $IGR_{A} = \lim_{N_{A} \to 0} \frac {1}{N_{A}} \frac {dN_{A}}{dt}|_{E_{B}} = r_{A}-r_{B}(\frac{\alpha_{AB}}{\alpha_{BB}})\rightarrow$ Species A can invade when $\frac{\alpha_{BB}}{r_{B}} > \frac{\alpha_{AB}}{r_{A}}$     
        * $IGR_{B} = \lim_{N_{B} \to 0} \frac {1}{N_{B}} \frac {dN_{B}}{dt}|_{E_{A}} = r_{B}-r_{A}(\frac{\alpha_{BA}}{\alpha_{AA}}) \rightarrow$ Species B can invade when $\frac{\alpha_{AA}}{r_{A}} > \frac{\alpha_{BA}}{r_{B}}$ 
    3. System dynamics:
        * $IGR_{A} > 0$ and $IGR_{B} < 0$: Species A wins
        * $IGR_{A} < 0$ and $IGR_{B} > 0$: Species B wins
        * $IGR_{A} > 0$ and $IGR_{B} > 0$: Two species coexist (mutual invasibility)
        * $IGR_{A} < 0$ and $IGR_{B} < 0$: Priority effect (founder control)

<div style="height:1px ;"><br></div> 

* **Analytical analysis (2): Local stability analysis**
    1. Behavior of a small displacement $\epsilon$ near the equilibrium: $\frac{d\epsilon}{dt} = \frac{d}{dt} \begin{vmatrix}\epsilon_{A}\\ \epsilon_{B}\end{vmatrix} = \begin{vmatrix}\frac {\partial f_{A}}{\partial N_{A}} & \frac {\partial f_{A}}{\partial N_{B}}\\\frac {\partial f_{B}}{\partial N_{A}} & \frac {\partial f_{B}}{\partial N_{B}}\end{vmatrix}_{(N_{A}^{*}, N_{B}^{*})} \begin{vmatrix}\epsilon_{A}\\ \epsilon_{B}\end{vmatrix} = J\begin{vmatrix}\epsilon_{A}\\ \epsilon_{B}\end{vmatrix}$
    2. General solution for $\begin{vmatrix}\epsilon_{A}\\ \epsilon_{B}\end{vmatrix}$: $w1\begin{vmatrix}C_{1}\\ D_{1}\end{vmatrix}e^{\lambda_{1}t} + w2\begin{vmatrix}C_{2}\\ D_{2}\end{vmatrix}e^{\lambda_{2}t} \\$
    where $\lambda_{1}$ and $\lambda_{2}$ are the two eigenvalues of $J$, $w1$ and $w2$ are constant, and $\begin{vmatrix}C_{1}\\ D_{1}\end{vmatrix}$ and $\begin{vmatrix}C_{2}\\ D_{2}\end{vmatrix}$ are the corresponding eigenvectors
    $\to \lambda's$ govern the dynamics of the displacement
    3. In our example model, $J = \begin{vmatrix}-N_{A}\alpha_{AA}+r_{A}-\alpha_{AA}N_{A}-\alpha_{AB}N_{B} & -N_{A}\alpha_{AB}\\-N_{B}\alpha_{BA} & -N_{B}\alpha_{BB}+r_{B}-\alpha_{BB}N_{B}-\alpha_{BA}N_{A}\end{vmatrix}$
    4. Steps for local stability analysis:
        1. Find the equilibrium points $E^{*}$
        2. Evaluate $J$ at $E^{*}$
        3. Find the eigenvalues of $J|_{E^{*}}$
        4. Determine the stability of $E^{*}$:
            * Stable if all real parts of $\lambda's$ < 0
            * Unstable if at least one real part of $\lambda's$ > 0
            * Spiral trajectory if the imaginary parts of $\lambda's$ is non-zero (this can be proven by the Euler's equation $e^{ix} = cos(x) + isin(x)$)

<div style="height:1px ;"><br></div> 

* **Local stability analysis of the four equilibrium points**
    1. $E_{0} = (0, 0)$:
        * $J_{E_{0}} = \begin{vmatrix}r_{A} & 0 \\ 0 & r_{B}\end{vmatrix}$
        * $\lambda's = r_{A}$ and $r_{B}$ (both > 0)
        * Unstable
    2. $E_{A} = (\frac {r_{A}}{\alpha_{AA}}, 0)$: 
        * $J_{E_{A}} = \begin{vmatrix}-r_{A} & -\alpha_{AB}(\frac {r_{A}}{\alpha_{AA}}) \\ 0 & r_{B}-\alpha_{BA}(\frac {r_{A}}{\alpha_{AA}})\end{vmatrix}$
        * $\lambda's = -r_{A}$ and $r_{B}-\alpha_{BA}(\frac {r_{A}}{\alpha_{AA}})$
        * Stability criteria: $\frac {\alpha_{BA}}{r_{B}} > \frac {\alpha_{AA}}{r_{A}}$
    3. $E_{B} = (0, \frac {r_{B}}{\alpha_{BB}})$:
        * $J_{E_{B}} = \begin{vmatrix}r_{A}-\alpha_{AB}(\frac {r_{B}}{\alpha_{BB}}) & 0 \\ -\alpha_{BA}(\frac {r_{B}}{\alpha_{BB}}) & -r_{B} \end{vmatrix}$
        * $\lambda's = -r_{B}$ and $r_{A}-\alpha_{AB}(\frac {r_{B}}{\alpha_{BB}})$
        * Stability criteria: $\frac {\alpha_{AB}}{r_{A}} > \frac {\alpha_{BB}}{r_{B}}$
    4. $E_{AB} = (\frac {r_{A}r_{B}(\frac {\alpha_{BB}}{r_{B}}-\frac {\alpha_{AB}}{r_{A}})}{\alpha_{AA} \alpha_{BB} - \alpha_{AB}\alpha_{BA}}, \frac {r_{A}r_{B}(\frac {\alpha_{AA}}{r_{A}}-\frac {\alpha_{BA}}{r_{B}})}{\alpha_{AA} \alpha_{BB} - \alpha_{AB}\alpha_{BA}}) = (N_{A}^*, N_{B}^*)$:
        * $J_{E_{AB}} = \begin{vmatrix}-\alpha_{AA}N_{A}^* & -\alpha_{AB}N_{B}^* \\ -\alpha_{BA}N_{B}^* & -\alpha_{BB}N_{B}^* \end{vmatrix}$
        * Characteristic equation: $\lambda^2+(\alpha_{AA}N_{A}^*+\alpha_{BB}N_{B}^*)\lambda+N_{A}^*N_{B}^*(\alpha_{AA}\alpha_{BB}-\alpha_{AB}\alpha_{BA}) = 0$
        * $\lambda_{1} + \lambda_{2}=\frac {-b}{a} = -(\alpha_{AA}N_{A}^*+\alpha_{BB}N_{B}^*)$; $\lambda_{1}\lambda_{2}=\frac {c}{a} = N_{A}^*N_{B}^*(\alpha_{AA}\alpha_{BB}-\alpha_{AB}\alpha_{BA})$
        * For both $\lambda's < 0$, we need $\lambda_{1} + \lambda_{2} < 0$ and $\lambda_{1}\lambda_{2} > 0$:
            1. $\lambda_{1} + \lambda_{2} < 0$ $\to$ $N_{A}^*$ and $N_{B}^* > 0$ $\to$ $\frac {\alpha_{BB}}{r_{B}} > \frac {\alpha_{AB}}{r_{A}}$ and $\frac {\alpha_{AA}}{r_{A}} > \frac {\alpha_{BA}}{r_{B}}$ [feasibility]
            2. $\lambda_{1}\lambda_{2} > 0$ $\to$ $\alpha_{AA}\alpha_{BB}-\alpha_{AB}\alpha_{BA} > 0$ [stabilization]

<div style="height:1px ;"><br></div>

* **Summary of stability criteria**

<style>
.book-body .page-wrapper .page-inner section.normal table th {
    border: 1px solid white !important;
}

.book-body .page-wrapper .page-inner section.normal table th div {
    border: 1px solid white !important;
}

</style>

<table class="table" style="font-size: 17px; font-family: Arial; margin-left: auto; margin-right: auto;">
 <thead>
<tr>
<th style="empty-cells: hide;border-bottom:hidden;" colspan="2"></th>
<th style="border-bottom:hidden;padding-bottom:0; padding-left:3px;padding-right:3px;text-align: center; font-size: 25px;background-color: white; border-top: 2px solid white; border-bottom: 2px solid white;" colspan="2"><div style="border-bottom: 1px solid #ddd; padding-bottom: 5px; ">$\frac {\alpha_{BB}}{r_{B}} - \frac {\alpha_{AB}}{r_{A}}$</div></th>
</tr>
  <tr>
   <th style="text-align:center;font-weight: bold;color: black !important;text-align: center;font-size: 30px;border-color: white; background-color: white;">   </th>
   <th style="text-align:center;font-weight: bold;color: black !important;text-align: center;font-size: 30px;border-color: white; background-color: white;">    </th>
   <th style="text-align:left;font-weight: bold;color: black !important;text-align: center;font-size: 30px;border-color: white; background-color: white;"> $+$ </th>
   <th style="text-align:left;font-weight: bold;color: black !important;text-align: center;font-size: 30px;border-color: white; background-color: white;"> $-$ </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:center;width: 3em; font-size: 25px; border-color: white; vertical-align: bottom;"> $\frac {\alpha_{AA}}{r_{A}} - \frac {\alpha_{BA}}{r_{B}}$ </td>
   <td style="text-align:center;width: 3em; font-size: 30px; border-color: white; border-top: 5px; font-weight: bold; vertical-align: middle;"> $+$ </td>
   <td style="text-align:left;width: 17em; border-right:2px solid;"> $\bullet$ $E_{A}$ and $E_{B}$ unstable <br> $\bullet$ $E_{AB}$ feasible and stable <br> $\bullet$ $IGR_{A}$ &gt; 0 and $IGR_{B}$ &gt; 0 <br> $\bullet$ Stable coexistence </td>
   <td style="text-align:left;width: 17em; "> $\bullet$ $E_{A}$ unstable and $E_{B}$ stable <br> $\bullet$ $E_{AB}$ unfeasible <br> $\bullet$ $IGR_{A}$ &lt; 0 and $IGR_{B}$ &gt; 0 <br> $\bullet$ Species B wins </td>
  </tr>
  <tr>
   <td style="text-align:center;border-top: 2px solid black; border-bottom: 2px solid white; background-color: white;width: 3em; font-size: 25px; border-color: white; vertical-align: bottom;">  </td>
   <td style="text-align:center;border-top: 2px solid black; border-bottom: 2px solid white; background-color: white;width: 3em; font-size: 30px; border-color: white; border-top: 5px; font-weight: bold; vertical-align: middle;"> $-$ </td>
   <td style="text-align:left;border-top: 2px solid black; border-bottom: 2px solid white; background-color: white;width: 17em; border-right:2px solid;"> $\bullet$ $E_{A}$ stable and $E_{B}$ unstable <br> $\bullet$ $E_{AB}$ unfeasible <br> $\bullet$ $IGR_{A}$ &gt; 0 and $IGR_{B}$ &lt; 0 <br> $\bullet$ Species A wins </td>
   <td style="text-align:left;border-top: 2px solid black; border-bottom: 2px solid white; background-color: white;width: 17em; "> $\bullet$ $E_{A}$ and $E_{B}$ stable <br> $\bullet$ $E_{AB}$ feasible but unstable <br> $\bullet$ $IGR_{A}$ &lt; 0 and $IGR_{B}$ &lt; 0 <br> $\bullet$ Priority effect </td>
  </tr>
</tbody>
</table>


<div style="height:1px ;"><br></div>    
<br>


## Lab demonstration {-}

In this lab, we are going to analyze the two-species Lotka-Volterra competition model numerically and visualize the population dynamics under different parameter settings.


```r
library(tidyverse)
library(deSolve)

LV_pop_dynamics <- function(r1 = 1.4, r2 = 1.2, a11 = 1/200, a21 = 1/400, a22 = 1/200, a12 = 1/300, N1_0 = 10, N2_0 = 10) {
    
### Model specification
LV_competition_model <- function(times, state, parms) {
  with(as.list(c(state, parms)), {
    dN1_dt = N1*(r1-a11*N1-a12*N2)  
    dN2_dt = N2*(r2-a22*N2-a21*N1)
    return(list(c(dN1_dt, dN2_dt)))
  })
}

### Model parameters
times <- seq(0, 100, by = 0.1)
state <- c(N1 = N1_0, N2 = N2_0)
parms <- c(r1 = r1, r2 = r2, a11 = a11, a21 = a21, a22 = a22, a12 = a12)

### Model application
pop_size <- ode(func = LV_competition_model, times = times, y = state, parms = parms)

### Visualize the population dynamics
pop_size %>%
  as.data.frame() %>%
  pivot_longer(cols = -time, names_to = "species", values_to = "N") %>%
  ggplot(aes(x = time, y = N, color = species)) + 
  geom_line(size = 1.5) +
  theme_classic(base_size = 12) +
  labs(x = "Time", y = "Population size") +
  scale_x_continuous(limits = c(0, 100.5), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, max(pop_size)*1.2), expand = c(0, 0)) +
  scale_color_brewer(name = NULL, palette = "Set1")
}

### Different parameter settings
LV_pop_dynamics(r1 = 1.4, r2 = 1.2, a11 = 1/200, a21 = 1/400, a22 = 1/200, a12 = 1/300, N1_0 = 10, N2_0 = 10)  # stable coexistence
```

<img src="08_Week_8_files/figure-html/unnamed-chunk-2-1.png" width="70%" style="display: block; margin: auto;" />

```r
LV_pop_dynamics(r1 = 1.2, r2 = 1.2, a11 = 1/200, a21 = 1/100, a22 = 1/100, a12 = 1/300, N1_0 = 10, N2_0 = 10)  # N1 wins
```

<img src="08_Week_8_files/figure-html/unnamed-chunk-2-2.png" width="70%" style="display: block; margin: auto;" />

```r
LV_pop_dynamics(r1 = 1.2, r2 = 1.2, a11 = 1/200, a21 = 1/500, a22 = 1/500, a12 = 1/300, N1_0 = 10, N2_0 = 10)  # N2 wins
```

<img src="08_Week_8_files/figure-html/unnamed-chunk-2-3.png" width="70%" style="display: block; margin: auto;" />
<br>

## Additional readings {-}

No additional readings this week.
<br>

## Assignments {-}

[Linear Stability Analysis of Lotka-Volterra Competition Model](./Assignments/Week8_LV Competition Model.pdf){target="_blank"}

[Suggested Solutions](./Assignments/Week8_LV Competition Model_with_Solutions.pdf){target="_blank"}





