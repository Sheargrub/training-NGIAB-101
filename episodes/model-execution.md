---
title: "Model Execution"
teaching: 5
exercises: 5
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do I execute a NextGen run?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Recognize methods to execute NextGen models
- Run a NextGen simulation using NGIAB

::::::::::::::::::::::::::::::::::::::::::::::::

## Model Execution using NGIAB container

To run a NextGen simulation, simply execute the following commands:
```
cd NextGen
git clone https://github.com/CIROH-UA/NGIAB-CloudInfra.git
cd NGIAB-CloudInfra
./guide.sh
```

The interactive guide script `guide.sh` will prompt you to enter input data pathways and allow you to select a computational mode (serial or parallel processing). After the simulation is complete, the guide script will give you the option to evaluate model predictions and visualize results (discussed in the next two episodes).

## Model Execution using Data Preprocess tool
A secondary method for executing a NextGen simulation is by using the Data Preprocess tool's CLI. The `-a` argument in the command will schedule an automatic execution of NGIAB after preprocessing selected data. As this module is being updated constantly, check back on its [GitHub page](https://github.com/CIROH-UA/NGIAB_data_preprocess) for the latest updates on its functionality.


## Your Turn

Use the guide script `guide.sh` to run a NextGen simulation using your preprocessed data.

Extra Credit: Use the Data Preprocess tool to automatically execute a NextGen run.

::::::::::::::::::::::::::::::::::::: keypoints 

- To execute a NextGen simulation with full functionality, use the interactive guide script `guide.sh` in the NGIAB container.
- A NextGen simulation can also be automatically executed post-preprocessing using the Data Preprocess tool.

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
