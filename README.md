# Flip_ReCom_LocalSearch
Contains code, data, and plans for Flip and ReCom local search heuristics for IL, MO, and TN congressional district plan optimization

## Data
The **IL_tracts_projected32616_MOD_SingleParts_Data_Plan**, **MO_Tracts_projected32615_Data_Plan**, and **TN_Tracts_projected32616_SingleParts_Data_Plan** folders contain the census tract shapefiles (with tract population, Democrat/Republican votes, and population broken down by race/ethnicity) for Illinois, Missouri, and Tennessee, respectively. _Note that the data columns for these shapefiles are hardcoded into the local search algorithms._

The **InitialPlans_IL_Tracts**, **InitialPlans_MO_Tracts**, and **InitialPlans_TN_Tracts** folders contain the initial congressional district plan assignment files for Illinois, Missouri, and Tennessee, respectively.

## Code

The **FlipLocalSearch_2023.ipynb** code implements _Flip_ iterations within simple hill-climbing, simulated annealing, and greedy local search heuristics to improve an objective for a given district plan, subject to constraints. This code reads in parameters from **Flip_PARAMETERS_2023.csv.**

The **ReComLocalSearch_2023.ipynb** code uses the open-source GerryChain package to implement _Recombination (ReCom)_ iterations within within simple hill-climbing, simulated annealing, and greedy local search heuristics to improve an objective for a given district plan, subject to constraints. This code reads in parameters from **ReCom_PARAMETERS_2023.csv.**

There are .yml environment files in the folder **Environment** that detail the versions of all packages that the code uses.

## Parameter Files

**FlipLocalSearch_2023.ipynb** reads in parameters from **Flip_PARAMETERS_2023.csv** and **ReComLocalSearch_2023.ipynb** reads in parameters from **ReCom_PARAMETERS_MO_2022.csv.** The user does not need to alter the code itself, they only need to change the parameters in these files. Both files are currently set up to optimize Illinois's congressional plan for compactness (measured by number of cut edges), subject to population balance and VRA constraints, using simple hill-climbing. With the given parameters, running the code will produce the assignment file of one congressional district plan optimized for compactness (located in a folder named Test) and should take approximately 15 seconds for Flip and 5 minutes for ReCom on a consumer-grade desktop/laptop computer.
