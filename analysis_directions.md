### Overview

* Run each of the problems with CADIS
* Postprocess the problems with postprocessing scripts
* If the results look interesting, make some flux maps with VisIT


### Mesh Refinement


### Parametric Study

* In the analysis scripts repository, I have created a script that can generate
  a parametric study.
  * Files: `/thesiscode/scripts/studymaker.py`
  * Inputs: .py file input for CADIS, arrays of deterministic parameter options
  * Functionality: the script modifies the .py file to in 
  * Example notebook:
    https://github.com/munkm/thesiscode/blob/master/notebooks/parametric_study_example.ipynb
* Use this script to regenerate the angle parameter studies (Pn order,
  quadrature order, quadrature type)
* This script does not support changes in the mesh size, so that will still
  have to be done manually. 

### Postprocessing tools

* In the analysis scripts repository, I have created a series of postprocessing
  scripts to aid in postprocessing the data for this hybrid methods work. 
  * Files:
    * `/thesiscode/scripts/single_run.py` -- convenience script to read in the
      data from a single run, based on different requested outputs. Has the
      ability to read MCNP data from a specified dir, the hdf5 output data from
      Denovo/Exnihilo, and the timing/silo data from denovo/exnihilo. 
    * `/thesiscode/scripts/plotting_utils.py` -- file that has plotting
      functions to more easily plot each of the figures in my dissertation. 
    * `/thesiscode/scripts/compare_runs.py` -- script that requires multiple
      directory specifications. It will attempt to automatically detect which
      method was run in each directory, and can be used to generate comparison
      plots for the different methods. 
    * `/thesiscode/scripts/analysis.py` and
      `/thesiscode/scripts/analysis_utils.py` -- actual functions performing
      analysis on the data read in by mcnpoutput and other functions. 
    * `/thesiscode/scripts/mcnpoutput.py` -- file that reads in the f4 tally
      data from MCNP and puts them into numpy arrays for later data processing.
      Also reads in timing and FOM information from MCNP output. 
  * Example Notebook:
    https://github.com/munkm/thesiscode/blob/master/notebooks/postprocessing-tools.ipynb
* Use this script to:
  * generate tables like this
  * to make histograms of the tallies in each of the problems
  * to make violin, box, or swarm plots of the flux distributions in the
    problems (not necessary for now)
  * to 
