DoEgen Synrift Example
--------

This is a working example implementation of DoEgen and a set of post-processing utilities to demonstrating how DoEgen can be used to calibrate badlands models to observations.


## Workflow summary

+ populate an excel spreadsheet with parameter variables and their ranges as input for a set of Badlands experiments
+ use DoEgen to evaluate the optimal parameters and optimal number of experiments to run
+ automatically generate and validate multiple model configuration/xml files using those parameters for Badlands to run
+ run the Badlands models in parallel using the python multiprocessing module

Once all of the experiment / model runs have completed use a set of post-processing scripts to:

+ generate a set of post-processed data, including environmental and geometric realtionships and interpolate that data into the final depth domain 
+ extract stratigraphic data from well locations for evaluation 
+ compare experimental stratigraphic information with observed stratigrpahic information and identify the experiments that have the most similarity to observed data.
+ evaluate the top 10 most similar results using the DoEgen, doeval,  evaluation utility.


![image](./images/doegen_exp_design.png "doeval and simlarity plot examples")

## Requirements

* Python >=3.8
* [Badlands>=2.2.3](https://badlands.readthedocs.io/en/latest/) 
* [doegen](https://github.com/sebhaan/DoEgen)
* [badlands-doe-toolset](https://github.com/GeoMattB/badlands_doe_toolset)
* [similaritymeasures](https://github.com/cjekel/similarity_measures)


This example assumes the docker container **badlandsmodel/badlands:doegen** with jupyter notebooks is being used. However, these packages are available to install from pip.


Once you have Docker installed, the badlands:doegen container may be installed with the following parameters.

OS command line example:

docker run -d --name="badlands-doegen" -p 8888:8888 -v "path_to_local_directory":/live/badlands_data badlandsmodel/badlands:doegen

### Jupyter notebook with python modules

The contents of this repository are needed, the zip file below should be accessible to the docker container.


**https://github.com/GeoMattB/Badlands_DoEgen_SynRift/archive/refs/heads/main.zip**


## Attribution and Acknowledgments
	
This jupyter notebook and code has been extended from a pipeline initially developed by the [Sydney Informatics Hub](https://www.sydney.edu.au/research/facilities/sydney-informatics-hub.html), a core research facility of the University of Sydney, for the [EarthByte](https://www.earthbyte.org/) group.

“This research was supported by the Sydney Informatics Hub, a Core
Research Facility of the University of Sydney.”

