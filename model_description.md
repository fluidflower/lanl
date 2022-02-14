_Please stick to the headings and their order. Don't modify the words in bold. Your input is required at each occurrence of "e.g." and "..."._<br>
_You may use https://tex-image-link-generator.herokuapp.com/ to render math formulas in Markdown, see the examples below._

## Physics

### PDEs

_E.g._ One mass balance per component water and CO2.

Mass balance of the component ![i](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+i) is in the form: 
![\frac{\partial}{\partial t}  \left(\varphi \sum_{\alpha} s_\alpha \eta_\alpha x^{\alpha}_{i} \right) + \nabla \cdot \sum_\alpha \boldsymbol{F}^{\alpha}_{i} = Q_i,](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial+t%7D++%5Cleft%28%5Cvarphi+%5Csum_%7B%5Calpha%7D+s_%5Calpha+%5Ceta_%5Calpha+x%5E%7B%5Calpha%7D_%7Bi%7D+%5Cright%29+%2B+%5Cnabla+%5Ccdot+%5Csum_%5Calpha+%5Cboldsymbol%7BF%7D%5E%7B%5Calpha%7D_%7Bi%7D+%3D+Q_i%2C)

Here, ![\alpha](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Calpha) is a fluid phase, the flux ![{\boldsymbol{F}}_i^{\alpha}
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%7B%5Cboldsymbol%7BF%7D%7D_i%5E%7B%5Calpha%7D%0A) is given by:
![{\boldsymbol{F}}_i^{{\alpha}}= {\boldsymbol{q}}_{{\alpha}}^{}\eta_{{\alpha}}^{} x_i^{{\alpha}} - \varphi s_{{\alpha}}^{} D_{{\alpha}}^{} \eta_{{\alpha}}^{} {\boldsymbol{\nabla}}x_i^{{\alpha}},
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%7B%5Cboldsymbol%7BF%7D%7D_i%5E%7B%7B%5Calpha%7D%7D%3D+%7B%5Cboldsymbol%7Bq%7D%7D_%7B%7B%5Calpha%7D%7D%5E%7B%7D%5Ceta_%7B%7B%5Calpha%7D%7D%5E%7B%7D+x_i%5E%7B%7B%5Calpha%7D%7D+-+%5Cvarphi+s_%7B%7B%5Calpha%7D%7D%5E%7B%7D+D_%7B%7B%5Calpha%7D%7D%5E%7B%7D+%5Ceta_%7B%7B%5Calpha%7D%7D%5E%7B%7D+%7B%5Cboldsymbol%7B%5Cnabla%7D%7Dx_i%5E%7B%7B%5Calpha%7D%7D%2C%0A)
![x_i^{\alpha}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+x_i%5E%7B%5Calpha%7D) denotes the mole fraction of species ![i](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+i) satisfying 
![\sum_i x_i^\alpha=1,](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Csum_i+x_i%5E%5Calpha%3D1%2C)

### Constitutive relations

#### Fluid-matrix interaction

* **Capillary pressure:** _E.g._ Brooks-Corey
  ![p_c(S_{l}) = p_\text{entry}S_{le}^{-1/\lambda}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+p_c%28S_%7Bl%7D%29+%3D+p_%5Ctext%7Bentry%7DS_%7Ble%7D%5E%7B-1%2F%5Clambda%7D%0A)

* **Relative permeability:** ...

#### Phase composition: Applied equations of state

* **CO2 in liquid phase:** ...

* **Water in gas phase:** ...

#### Density

* **Liquid phase:** ...

* **Gas phase:** ...

### Spatial parameters

_Please provide the relevant facies parameters as a csv file._<br>
_E.g._ The parameters ![p_\text{entry}, \lambda, S_{lr}, S_{gr}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+p_%5Ctext%7Bentry%7D%2C+%5Clambda%2C+S_%7Blr%7D%2C+S_%7Bgr%7D%0A) for the different facies are given in [spatial_parameters.csv](spatial_parameters.csv).<br>
_Obviously, the number and type of parameters for your model might differ from the ones in the provided template._

## Numerics

### Coupling of flow and transport, temporal and spatial discretization

_E.g._ Fully coupled, fully implicit, cell-centered FV with TPFA.

### Linearization and Solvers

_E.g._ Newton with line search, AMG-preconditioned BiCGSTAB for the linear systems.

### Primary Variables

_E.g._ Dependent on local phase composition:
* Both phases present:
  ![p_l, S_g](https://render.githubusercontent.com/render/math?math=%5Ctextstyle+p_l%2C+S_g%0A)...
