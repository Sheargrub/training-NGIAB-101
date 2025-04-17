---
title: "Visualization"
teaching: 5
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do I visualize my NextGen runs?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain how the Data Visualizer complements NGIAB.
- Use the Data Visualizer to visualize results of a NextGen run.

::::::::::::::::::::::::::::::::::::::::::::::::

## Data Visualizer

The Data Visualizer component developed using the Tethys Platform [(Swain et al., 2015)](https://doi.org/10.1016/j.envsoft.2015.01.014) complements NGIAB and its other extensions by providing a robust environment for **geospatial and time series visualization of catchments and nexus points**. Through a web-based architecture, researchers can seamlessly explore hydrological data in a spatiotemporal context, facilitating a deeper understanding of model outputs and key hydrological processes [(CIROH, 2025)](https://github.com/CIROH-UA/ngiab-client). In addition to standard map-based displays, this component also **supports the visualization of the TEEHR output**, including tabular metrics and interactive time series plots.

#### Using the Data Visualizer with NGIAB

Like TEEHR, the Data Visualizer is automatically executed by default upon execution of the main NGIAB guide script, `guide.sh`. A separate `viewOnTethys.sh` script is also available in the NGIAB-CloudInfra repository.

Once a simulation is complete, users can launch the Data Visualizer through their web browser when prompted by the guide script. Through its interactive tools, users can analyze geospatial patterns, temporal trends, and overall model behavior. Although TEEHR’s outputs can be displayed within the Data Visualizer, this tool is primarily designed to provide a broad overview of model results. Users seeking TEEHR’s more advanced analysis features can still access them outside the Data Visualizer.

Figures 1 and 2 demonstrate several ways the Data Visualizer can be used to visualize model outputs, including geopatial visualization for nexus points, catchment-based visualization, and TEEHR time series representation.

| ![Figure 1](images/fig6-1.png) |
| :--: |
| *Figure 1: A map showing the geospatial visualization using the Data Visualizer within the Tethys framework for an entire study area (Provo River near Woodland, UT).* |

| ![alt text](images/fig1-5.png) |
| :--: |
| *Figure 2: A map showing the geospatial visualization using the Data Visualizer within the Tethys framework for a selected outlet nexus point as well as displaying a time series plot between observed (labeled “USGS”; blue line) and simulated (labeled “ngen”; orange line) with the performance metrics (KGE, NSE, and relative bias). The Visualizer can also show the performance of the NWM 3.0 compared to the observed time series.* |

::::::::::::::::::::::::::::::::::::: callout

To use the Data Visualizer through an SSH connection, you will have to set up port forwarding. See the instructions in the Advanced Topics episode.

::::::::::::::::::::::::::::::::::::::::::::::::

## Your Turn

Go ahead and run the Data Visualizer in the guide script, open it in your browser, and explore the visualization of your NextGen run.

::::::::::::::::::::::::::::::::::::: keypoints 

- The Data Visualizer, built on the Tethys Platform, provides interactive geospatial and time series visualization for NextGen model outputs.
- It complements NGIAB by offering a web-based environment to explore catchments, nexus points, temporal patterns, and TEEHR outputs in your simulation results.
- The Data Visualizer runs automatically with the `guide.sh` script.

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
