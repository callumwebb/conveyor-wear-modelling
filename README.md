# conveyor-wear-modelling
Public repository for the *Developing and evaluating predictive conveyor belt wear models* article.
We are able to share code for our methodology, however the data are proprietary and currently are not published.
Code for the model evaluation framework including our cross-validation design, variable importance, and partial dependence plots is included.

## Getting started
The code is presented in a single R notebook, `modelling.Rmd`. We recommend using [RStudio](https://rstudio.com/) and opening `conveyor-wear-modelling.Rproj` for interacting with the source.
Dependencies are captured using the `renv` package (https://rstudio.github.io/renv/index.html). Follow the installation instructions for `renv` and then run `renv::restore` to install the required packages.

### Data structure
In lieu of modelling data, we can describe the structure of the data so that our methodology can be understood and applied to similar supervised learning problems (conceivably, you could also generate dummy data matching this structure to run and interrogate our code).

The file `data/model-data.rds` (not published) is a data frame with the following structure:

* 660 rows
* 16 columns

| column             | class     | description                                                           |
|--------------------|-----------|-----------------------------------------------------------------------|
| pool               | integer   | uniquely identifies belt                                              |
| wear_type          | character | "mean" or "max" - type of wear rate metric                            |
| metric             | character | "mm/MT" or "mm/week" - throughput or time based wear rate             |
| rate               | numeric   | wear rate value                                                       |
| r2                 | numeric   | r squared value of wear rate estimate                                 |
| std_err            | numeric   | standard error of wear rate estimate                                  |
| belt_width_mm      | integer   | belt width [mm]                                                       |
| belt_strength_kNpm | integer   | belt strength [kN/m]                                                  |
| conveyor_duty      | character | "reclaimer", "shiploader", "stacker", "transfer", or "yard"           |
| belt_speed_ms      | numeric   | belt speed [m/s]                                                      |
| belt_length_m      | integer   | belt length [m]                                                       |
| load_frequency     | numeric   | load frequency [Hz]                                                   |
| conveyor_id        | character | the conveyor the belt was installed on                                |
| drop_height_m      | numeric   | vertical distance between feeding and receiving pulleys               |
| perc_fines         | numeric   | percentage of conveyed product made up of "fines"                     |
| position           | integer   | transverse position of maximum wear rate, NA when wear_type is "mean" |

### Contact

Please feel free to contact the authors using the contact information published in the article, or by raising an issue in this repository.