

# Week 6 {-} 
<div style = "font-size: 28pt"> **_Metapopulations and patch occupancy models_**</div>

## Lecture in a nutshell {-}

* **Metapopulations:**
    1. A group of local populations linked by dispersal
    2. Timescale separation: "patch" as the basic model unit; ignoring the population dynamics within each patch
    3. Assumptions:
        1. Homogeneous patches
        2. No explicit spatial structure (global dispersal; distance-independent)
        3. No time lag
        4. Colonization/extinction rates are time-independent but can depend on current occupancy
        5. Sufficiently large numbers of patches
    4. Modeling the probability (fraction) of patches being occupied $P_{(t)}$: $\\\begin{aligned}\frac{dP}{dt}&=I-E\\&=C_{(P)}(1-P)-e_{(P)}P \\&= local~colonization - local~extinction \end{aligned}$ 
        
<div style="height:1px ;"><br></div>

* **Mainland-island model:**
    1. Mainland as a permanent external source of propagules
    2. Constant immigration from mainland (i.e., constant colonization rate): $C_{(P)} = C_{0}$ 
    3. Constant extinction rate of occupied islands: $e_{(P)} = e_{0}$
    4. No dispersal among islands
    5. Modeling the patch dynamics:
        * System equation: $\frac{dP}{dt}=C_{0}(1-P)-e_{0}P$
        * Equilibrium point $P^{*} = \frac {C_{0}}{C_{0} + e_{0}}$
        * Local stability analysis: $\frac {d}{dP}(\frac {dP}{dt})|_{P = P*} = - (C_{0} + e_{0}) < 0$
        * Equilibrium is stable: metapopulations always persist even if $C_{0} < e_{0}$ because mainland is the constant stable propagule source 

<div style="height:1px ;"><br></div>

* **Internal colonization model:**
    1. No mainland; occupied patches are progagule sources
    2. No dispersal among patches
    3. Colonization rate depends on current patch occupancy: $C_{(P)} = C_{1}P ~ (C_{1} > 0)$
    4. Constant extinction rate of occupied patches: $e_{(P)} = e_{0}$
    5. Modeling the patch dynamics:
        * System equation: $\frac{dP}{dt}=C_{1}P(1-P)-e_{0}P$
        * Equilibrium point $P^{*} = 0$ and $1- \frac {e_{0}}{C_{1}}$
        * Local stability analysis: $\frac {d}{dP}(\frac {dP}{dt})|_{P = P*} = C_{1}(1-P^{*}) - e_{0} - P^{*}C_{1}$
        * Equilibrium $P^{*} = 1- \frac {e_{0}}{C_{1}}$ is stable when $C_{1} > e_{0}$ ($P^{*} = 0$ is unstable)
        * Equilibrium $P^{*} = 1- \frac {e_{0}}{C_{1}}$ is unstable when $C_{1} < e_{0}$ ($P^{*} = 0$ is stable)
        * Metapopulations may not always persist depending on the relative magnitude of colonization and extinction rate

<div style="height:1px ;"><br></div>

* **Mainland-island model with rescue effect:**
    1. Rescue effect: higher overall occupancy will reduce the extinction rate of the islands
    2. Constant immigration from mainland: $C_{(P)} = C_{0}$ 
    3. Extinction rate depends on the fraction of unoccupied islands: $e_{(P)} = e_{1}(1-P)$
    4. Modeling the patch dynamics:
        * System equation: $\frac{dP}{dt}=C_{0}(1-P)-e_{1}(1-P)P$
        * Equilibrium point $P^{*} = 1$ and $\frac {C_{0}}{e_{1}}$
        * Local stability analysis: $\frac {d}{dP}(\frac {dP}{dt})|_{P = P*} = -(C_{0}-(e_{1}P^{*}) - (1-P^{*})e_{1}$
        * Equilibrium $P^{*} = \frac {C_{0}}{e_{1}}$ is unstable when $C_{0} > e_{1}$ ($P^{*} = 1$ is stable)
        * Equilibrium $P^{*} = \frac {C_{0}}{e_{1}}$ is stable when $C_{0} < e_{1}$ ($P^{*} = 1$ is unstable)
        * Metapopulations always persist regardless of the colonization and extinction rate

<br>

## Lab demonstration {-}

Plants can condition nearby soil microbial communities, which will in turn influence the performance of subsequent colonizing plants. The soil beneath plant communities are therefore a mosaic with different cultivation histories. Po-Ju wants to understand how plant demographic rates (i.e., colonization and mortality rate) and microbial dynamics (i.e., the conditioning and decay rate of microbial communities) affect the percentage of different soil types in natural forests. As a starting point, Po-Ju builds a one-species patch occupancy model to track the dynamics of different types of plant-soil combination. 

In this model, he characterizes sites by their plant-soil microbe state, using the notation $P_{ij}$ to indicate sites that are now occupied by plant species $i$ but have soil microbes state $j$. Here, as a single species model, $i$ can be 0 or $A$, representing uncolonized sites or sites colonized by plant $A$, respectively. Similarly, $j$ can be 0 or $A$, indicating sites without recent plant conditioning history or sites conditioned by plant $A$, respectively. In summary:  

1. $P_{00}$ represents uncolonized and unconditioned sites 
2. $P_{A0}$ represents cites colonized by plant $A$ but the soil is yet to be conditioned 
3. $P_{AA}$ represents plant $A$ colonizing a site with plant-$A$-specific microbial community 
4. $P_{0A}$ represents sites that are currently unoccupied but have soil microbes that were associated with plant $A$ 

At the landscape scale, $P_{ij}$ represents the proportion of sites belonging to a particular plant-soil microbe state, and its dynamics, $\frac {dP_{ij}}{dt}$, summarizes the processes of plant colonization and death. The transitions between different plant-soil microbe states can be described by the following figure. 

<img src="./Plant_soil_model.png" width= "100%"/>

Here, $P_{00}$ can be colonized by plant $A$ when propagules arrive, transitioning the state from $P_{00}$ to $P_{A0}$. Plants may die, with rate $m_{A}$, before conditioning the soil (i.e., transition from $P_{A0}$ back to $P_{00}$), or may successfully condition the soil with rate $c_{A}$ (i.e., transition from $P_{A0}$ to $P_{AA}$). After plants within the state $P_{AA}$ die, a site with microbial legacy is left behind, denoted as $P_{0A}$. These empty sites can be recolonized (i.e., transition from $P_{0A}$ back to $P_{AA}$) with rates affected by the microbial legacy effect, $\alpha$. Finally, the microbial community within the soil may decay to unconditioned state with rate $d_{A}$, transitioning the state from $P_{0A}$ to $P_{00}$.

In this lab, we are going to model the dynamics of this plant-soil system. We will start by converting the flow diagram into a set of differential equations and then solve them numerically using the package `deSolve`. 


```r
library(deSolve)
library(tidyverse)

### Model specification
plant_soil_model <- function(times, state, parms) {
  with(as.list(c(state, parms)), {
    dP00_dt = P0A*dA + PA0*mA - P00*(PA0 + PAA)*RA
    dPA0_dt = P00*(PA0 + PAA)*RA - PA0*mA - PA0*CA
    dPAA_dt = PA0*CA - PAA*mA + P0A*(PA0 + PAA)*RA*a
    dP0A_dt = PAA*mA - P0A*(PA0 + PAA)*RA*a - P0A*dA
    
    return(list(c(dP00_dt, dPA0_dt, dPAA_dt, dP0A_dt)))
  })
}

### Model parameters
times <- seq(0, 20, by = 0.1)
state <- c(P00 = 0.25, PA0 = 0.25, PAA = 0.25, P0A = 0.25)
parms <- c(RA = 0.5, mA = 0.1, CA = 0.5, dA = 0.4, a = 0.7)

### ODE solver
patch_prop <- ode(func = plant_soil_model, times = times, y = state, parms = parms)

### Visualization
patch_prop %>%
  as.data.frame() %>%
  pivot_longer(cols = -time, names_to = "patch", values_to = "prop") %>%
  ggplot(aes(x = time, y = prop, color = fct_reorder(patch, prop, last,  .desc = T))) + 
  geom_line(size = 1.5) +
  theme_classic(base_size = 12) +
  labs(x = "Time", y = "Proportion") +
  scale_x_continuous(limits = c(0, 20.5), expand = c(0, 0)) +
  scale_y_continuous(limits = c(0, 0.8), expand = c(0, 0)) +
  scale_color_brewer(name = NULL, palette = "Set1")    
```

<img src="06_Week_6_files/figure-html/unnamed-chunk-1-1.png" width="70%" style="display: block; margin: auto;" />
<br>

## Additional readings {-}

[Otto & Day Chapter 2 - How to Construct a Model](./Additional readings/Otto_&_Day_Chapter2.pdf){target="_blank"}

<br>

## Assignments {-}

No assignments this week.


