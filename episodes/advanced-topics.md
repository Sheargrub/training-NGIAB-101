---
title: "Advanced Topics"
teaching: 5
exercises: 60
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I build NGIAB locally?
- How do I use NGIAB on an high-performance computing (HPC) system?
- How can I contribute to NGIAB?
- What is the Research DataStream?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Build a development version of NGIAB locally
- Install and use NGIAB on an HPC
- Explain the NGIAB community contribution process
- Describe the Research DataStream

::::::::::::::::::::::::::::::::::::::::::::::::

## Building NGIAB locally

If you would like to build the NGIAB image locally instead of pulling the latest image from the Docker remote registry, use the following commands:
```
cd docker
docker build -f Dockerfile -t awiciroh/ciroh-ngen-image:latest . --no-cache
```

## Using NGIAB on High-Performance Computing (HPC) Environments

The most up-to-date information on installing NGIAB on an HPC can be found [here](https://github.com/CIROH-UA/NGIAB-HPCInfra). Other than a different installation process and the use of Singularity instead of Docker, the workflow is the same to execute a NextGen run. Tools like the Data Preprocessor, TEEHR, and the Data Visualizer are still available. The NGIAB-HPCInfra contains its own interactive `guide.sh` script, which allows users to specify input data pathways and run configurations (serial or parallel), as well as trigger the execution of TEEHR and the Data Visualizer.

#### Singularity

NGIAB uses Singularity as its containerization platform for HPC environments. Singularity enables secure execution of containerized applications on multi-user HPC clusters. Key features of Singularity include native HPC integration, which allows the execution of containerized applications within existing batch job schedulers such as SLURM (Simple Linux Utility for Resource Management) workload manager, PBS (Portable Batch System) and LSF (Load Sharing Facility); enforced security – it runs containers as non-root users, reducing security risks; and seamless access to host file systems – it enables users to interact with datasets and computational resources without additional configuration directly. Singularity images, known as Singularity Image Format (SIF) files, encapsulate the entire runtime environment, ensuring full reproducibility of simulations. These images can be transferred between systems without requiring reinstallation of software dependencies, making Singularity a reliable choice for running hydrologic models on large-scale computational infrastructures (Jajula and Bangalore, 2024).

## Research DataStream

The NextGen Research DataStream [(Laser et al., 2024)](https://doi.org/10.22541/essoar.173445058.85883665/v1) refers to **daily, CONUS-wide, spatially distributed hydrologic numerical simulations** in the AWS cloud. The physical and machine learning-based models that perform the calculations are orchestrated using the NextGen framework and executed within the NGIAB Docker environment. The NextGen realization file, which configures the models and the variables exchanged between them, is publicly available on GitHub [(CIROH-UA, 2025)](https://github.com/CIROH-UA/ngen-datastream) under the configuration folder. The open-source and community-maintained NextGen realization file allows for continuous accuracy improvement through community contributions. Development is ongoing to refine a process by which community members may propose edits to the NextGen realization. In addition, all input and output files will be publicly available when this development is complete. *Currently, the NextGen DataStream forcing files and associated metadata are available through our [AWS S3 Explorer](https://datastream.ciroh.org/index.html). Daily NextGen simulation outputs via DataStream will soon be available.*

DataStreamCLI is the backend software for the NextGen Research DataStream and can function as a stand-alone command-line interface tool (Figure 1). DataStreamCLI automates the collection and formatting of input data, manages the NextGen framework-based executions through NGIAB, and handles outputs. DataStreamCLI is optimized for repetitive large domain (>10,000 catchments) simulations with short to medium temporal range (<1000 timesteps) yet is versatile and offers many options to facilitate explorative, efficient hydrologic simulations using the NextGen framework.

| ![Figure 1](images/fig1-3.png) |
| :--: |
| *Figure 1: DataStreamCLI Workflow* |

## Community Contributions to NGIAB

The most up-to-date guidelines on community contributions for each repository can be found on its respective GitHub page. 

#### General contribution guidance

- You can use the issue tracker on GitHub to suggest feature requests, report bugs, or ask questions.
- You can change the codebase through Git:
  - Create a fork
  - Clone the repository locally
  - Keep the fork and clone up-to-date
  - Create branches when you want to contribute
  - Make changes to the code
  - Commit to your local branch
  - Push commits to your GitHub fork
  - Create a pull request when the changes are ready to be incorporated

::::::::::::::::::::::::::::::::::::: keypoints 

- NGIAB can be built locally using Docker, allowing for development without pulling from the remote registry.
- NGIAB supports HPC environments through Singularity, not Docker, but the workflow mirrors the local Docker use.
- The Research DataStream delivers daily, CONUS-wide hydrologic simulations via AWS using the NextGen Framework, executed in the NGIAB Docker environment.
- Community contribution guidelines are available in each repository's GitHub page.

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
