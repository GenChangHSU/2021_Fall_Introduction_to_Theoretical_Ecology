

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
        * $IGR_{A} > 0$ and $IGR_{B} < 0$: Species A wins
        * $IGR_{A} < 0$ and $IGR_{B} > 0$: Species B wins
        * $IGR_{A} > 0$ and $IGR_{B} > 0$: Two species coexist (mutual invasibility)
        * $IGR_{A} < 0$ and $IGR_{B} < 0$: Priority effect
    3. $IGR_{A} = \lim_{N_{A} \to 0} \frac {1}{N_{A}} \frac {dN_{A}}{dt}|_{E_{B}} = r_{A}-r_{B}(\frac{\alpha_{AB}}{\alpha_{BB}})\rightarrow$ Species A can invade when $\frac{\alpha_{BB}}{r_{B}} > \frac{\alpha_{AB}}{r_{A}}$     
    4. $IGR_{B} = \lim_{N_{B} \to 0} \frac {1}{N_{B}} \frac {dN_{B}}{dt}|_{E_{A}} = r_{B}-r_{A}(\frac{\alpha_{BA}}{\alpha_{AA}}) \rightarrow$ Species B can invade when $\frac{\alpha_{AA}}{r_{A}} > \frac{\alpha_{BA}}{r_{B}}$   

<div style="height:1px ;"><br></div> 

* **Analytical analysis (2): Local stability analysis**
    1. A small displacement from the equilibrium: 
    2. Dynamics of displacement: $\frac{d}{dt} \begin{vmatrix}0\\ 0\end{vmatrix}$
    3. Eigenvalues of J
    4. General solution
    5. J = 
    6. Steps:
        1. 
        2. 
        3. 

$J = \begin{vmatrix}\frac {\partial }{\partial N_{A}} \frac {dN_{A}}{dt} & 0\\0 & 0\end{vmatrix}$
$J = \begin{vmatrix}0\\ 0\end{vmatrix}$

<div style="height:1px ;"><br></div> 

* **Local stability analysis of the four equilibrium points**
    1. $E_{0} = (0, 0)$
    2. $E_{A} = (\frac {r_{A}}{\alpha_{AA}}, 0)$ 
        * Jacobian matrix: $J|_{E_{0}} = \begin{vmatrix}0 & 0\\0 & 0\end{vmatrix}$
        * Eigenvalues: $\lambda_{1} = and~\lambda_{2} = $
        * Stability criteria: $\frac {r_{A}}{\alpha_{AA}} > \frac {r_{B}}{\alpha_{BA}}$ and $\frac {r_{A}}{\alpha_{AB}} > \frac {r_{B}}{\alpha_{BB}}$
    3. $E_{B} = (0, \frac {r_{B}}{\alpha_{BB}})$ when $\frac {r_{A}}{\alpha_{AA}} < \frac {r_{B}}{\alpha_{BA}}$ and $\frac {r_{A}}{\alpha_{AB}} < \frac {r_{B}}{\alpha_{BB}}$
    4. $E_{AB} = (\frac {r_{A}r_{B}(\frac {\alpha_{BB}}{r_{B}}-\frac {\alpha_{AB}}{r_{A}})}{\alpha_{AA} \alpha_{BB} - \alpha_{AB}\alpha_{BA}}, \frac {r_{A}r_{B}(\frac {\alpha_{AA}}{r_{A}}-\frac {\alpha_{BA}}{r_{B}})}{\alpha_{AA} \alpha_{BB} - \alpha_{AB}\alpha_{BA}})$ when $\frac {r_{B}}{\alpha_{BA}} > \frac {r_{A}}{\alpha_{AA}}$ and $\frac {r_{A}}{\alpha_{AB}} > \frac {r_{B}}{\alpha_{BB}}$
    
    5. ecies A and B coexist (unstable; there are alternative stable states $E_{A}$ and $E_{B}$ depending on the initial condition): $E_{AB} = (\frac {r_{A}r_{B}(\frac {\alpha_{BB}}{r_{B}}-\frac {\alpha_{AB}}{r_{A}})}{\alpha_{AA} \alpha_{BB} - \alpha_{AB}\alpha_{BA}}, \frac {r_{A}r_{B}(\frac {\alpha_{AA}}{r_{A}}-\frac {\alpha_{BA}}{r_{B}})}{\alpha_{AA} \alpha_{BB} - \alpha_{AB}\alpha_{BA}})$ when $\frac {r_{B}}{\alpha_{BA}} < \frac {r_{A}}{\alpha_{AA}}$ and $\frac {r_{A}}{\alpha_{AB}} < \frac {r_{B}}{\alpha_{BB}}$
    
<div style="height:1px ;"><br></div>

* **Summary of stability criteria**
    1. 
    2. 
    3.
    4. 

<div style="height:1px ;"><br></div>    
<br>


## Lab demonstration {-}

In this lab, we are going to analyze the two-species Lotka-Volterra competition model numerically and visualize the population dynamics under different parameter settings.


<br>

## Additional readings {-}

<br>
<br>
<br>
<br>
<br>

## Assignments {-}

[Linear Stability Analysis of Lotka-Volterra Competition Model](./Assignments/Week8_LV Competition Model.pdf){target="_blank"}

<!-- [Suggested Solutions](./Assignments/Week8_LV Competition Model_with_Solutions.pdf){target="_blank"} -->





