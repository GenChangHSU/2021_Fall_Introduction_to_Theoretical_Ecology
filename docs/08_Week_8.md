

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

<table class=" lightable-paper table table-bordered" style="font-size: 17px; font-family: Arial; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;">
 <thead>
<tr>
<th style="empty-cells: hide;" colspan="2"></th>
<th style="padding-bottom:0; padding-left:3px;padding-right:3px;text-align: center; " colspan="2"><div style="border-bottom: 1px solid #00000020; padding-bottom: 5px; ">a2-b2</div></th>
</tr>
  <tr>
   <th style="text-align:center;font-weight: bold;color: black !important;font-size: 20px;"> 1 </th>
   <th style="text-align:center;font-weight: bold;color: black !important;font-size: 20px;"> 2 </th>
   <th style="text-align:center;font-weight: bold;color: black !important;font-size: 20px;"> + </th>
   <th style="text-align:center;font-weight: bold;color: black !important;font-size: 20px;"> - </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:center;width: 5em; "> a1-b1 </td>
   <td style="text-align:center;width: 5em; "> + </td>
   <td style="text-align:center;width: 15em; border-right:1px solid;"> EA and EB unstable <br> EAB feasible and stable <br> IGRA &gt; 0 and IGRB &gt; 0 <br> Stable coexistence </td>
   <td style="text-align:center;width: 15em; "> EA unstable and EB stable <br> EAB unfeasible <br> IGRA &lt; 0 and IGRB &gt; 0 <br> Species B wins </td>
  </tr>
  <tr>
   <td style="text-align:center;width: 5em; ">  </td>
   <td style="text-align:center;width: 5em; "> - </td>
   <td style="text-align:center;width: 15em; border-right:1px solid;"> EA stable and EB unstable <br> EAB unfeasible <br> IGRA &gt; 0 and IGRB &lt; 0 <br> Species A wins </td>
   <td style="text-align:center;width: 15em; "> EA and EB unstable <br> EAB feasible but unstable <br> IGRA &lt; 0 and IGRB &lt; 0 <br> Priority effect </td>
  </tr>
</tbody>
</table>

<div style="height:1px ;"><br></div>    
<br>


## Lab demonstration {-}

In this lab, we are going to analyze the two-species Lotka-Volterra competition model numerically and visualize the population dynamics under different parameter settings.


<br>

## Additional readings {-}

No additional readings this week.
<br>

## Assignments {-}

[Linear Stability Analysis of Lotka-Volterra Competition Model](./Assignments/Week8_LV Competition Model.pdf){target="_blank"}

<!-- [Suggested Solutions](./Assignments/Week8_LV Competition Model_with_Solutions.pdf){target="_blank"} -->





