_Please stick to the headings and their order. Don't modify the words in bold. Your input is required at each occurrence of "e.g." and "..."._<br>
_You may use https://tex-image-link-generator.herokuapp.com/ to render math formulas in Markdown, see the examples below._

## Physics

We used the HPC porous media code PFLOTRAN https://www.pflotran.org/documentation/index.html for our modeling. We also used FEHM initially (https://fehm.lanl.gov/) and got similar results. We have since then continued to use PFLOTRAN.


### PDEs

_E.g._ One mass balance per component water and CO2.

Mass balance of the component ![i](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+i) is in the form: 
![\frac{\partial}{\partial t}  \left(\varphi \sum_{\alpha} s_\alpha \eta_\alpha x^{\alpha}_{i} \right) + \nabla \cdot \sum_\alpha \boldsymbol{F}^{\alpha}_{i} = Q_i,](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial+t%7D++%5Cleft%28%5Cvarphi+%5Csum_%7B%5Calpha%7D+s_%5Calpha+%5Ceta_%5Calpha+x%5E%7B%5Calpha%7D_%7Bi%7D+%5Cright%29+%2B+%5Cnabla+%5Ccdot+%5Csum_%5Calpha+%5Cboldsymbol%7BF%7D%5E%7B%5Calpha%7D_%7Bi%7D+%3D+Q_i%2C)

Here, ![\alpha](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Calpha) is a fluid phase, the flux ![{\boldsymbol{F}}_i^{\alpha}
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%7B%5Cboldsymbol%7BF%7D%7D_i%5E%7B%5Calpha%7D%0A) is given by:
![{\boldsymbol{F}}_i^{{\alpha}}= {\boldsymbol{q}}_{{\alpha}}^{}\eta_{{\alpha}}^{} x_i^{{\alpha}} - \varphi s_{{\alpha}}^{} D_{{\alpha}}^{} \eta_{{\alpha}}^{} {\boldsymbol{\nabla}}x_i^{{\alpha}},
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%7B%5Cboldsymbol%7BF%7D%7D_i%5E%7B%7B%5Calpha%7D%7D%3D+%7B%5Cboldsymbol%7Bq%7D%7D_%7B%7B%5Calpha%7D%7D%5E%7B%7D%5Ceta_%7B%7B%5Calpha%7D%7D%5E%7B%7D+x_i%5E%7B%7B%5Calpha%7D%7D+-+%5Cvarphi+s_%7B%7B%5Calpha%7D%7D%5E%7B%7D+D_%7B%7B%5Calpha%7D%7D%5E%7B%7D+%5Ceta_%7B%7B%5Calpha%7D%7D%5E%7B%7D+%7B%5Cboldsymbol%7B%5Cnabla%7D%7Dx_i%5E%7B%7B%5Calpha%7D%7D%2C%0A)
![x_i^{\alpha}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+x_i%5E%7B%5Calpha%7D) denotes the mole fraction of species ![i](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+i) satisfying 
![\sum_i x_i^\alpha=1,](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Csum_i+x_i%5E%5Calpha%3D1%2C).

See https://www.pflotran.org/documentation/theory_guide/mode_mphase.html#governing-equations for more details.
### Constitutive relations

#### Fluid-matrix interaction

* **Capillary pressure:**   Linear curves were used

* **Relative permeability:** 
Linear curves were used

#### Phase composition: Applied equations of state

* **CO2 in liquid phase:** Duan, Zhenhao, and Rui Sun. "An improved model calculating CO2 solubility in pure water and aqueous NaCl solutions from 273 to 533 K and from 0 to 2000 bar." Chemical geology 193.3-4 (2003): 257-271.

* **Water in gas phase:** 

#### Density

* **Liquid phase:** International Formulation Committee of the Sixth International Conference on Properties of Steam (1967)

* **Gas phase:** Span, Roland, and Wolfgang Wagner. "A new equation of state for carbon dioxide covering the fluid region from the triple‐point temperature to 1100 K at pressures up to 800 MPa." Journal of physical and chemical reference data 25.6 (1996): 1509-1596.

#### Solubility limit

1.67 kg/m3

### Temperature

20 C throughout

### Domain volume

Total domain volume: 0.08184 m3
Total pore volume: 0.03578m3

### Spatial parameters
Parameters can be found in [spatial_parameters.csv](spatial_parameters.csv).<br>

## Numerics

### Coupling of flow and transport, temporal and spatial discretization

1. Flow and transport are spatially discretized using two-point flux finite volume. Backward Euler was used for temporal discretization with adaptive time-stepping. 
2. In case of tracer tests flow and transport are coupled sequentially.
3. For CO2 flow/transport, full two-phase two-component mass balance equations are solved in a fully coupled fashion.


### Linearization and Solvers

Newton outer loop with FGMRES linear solver along with CPR pre-conditioning was used.

### Primary Variables

* Variable switching: see details in https://www.pflotran.org/documentation/theory_guide/mode_mphase.html#governing-equations

### Computational Grid

Tri Delauney elements are converted to Voronoi
Number of voronoi cells: 24748

### Performance

| Indicator                            |  Average |      Min |      Max |
|:-------------------------------------|---------:|---------:|---------:|
| time step size [s]                   | 6 | 6.e-6 | 6 |
| # nonlinear iterations per time step |      1 |      1 |      1 |
| # linear iterations per solve        |      2 |      2 |      5 |
