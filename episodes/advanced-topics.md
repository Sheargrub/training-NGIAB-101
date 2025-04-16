---
title: "Advanced Topics"
teaching: 5
exercises: 60
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I build NGIAB locally?
- How do I use NGIAB on an high-performance computing (HPC) system?
- How can I contribute to NGIAB?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Build a development version of NGIAB locally
- Install and use NGIAB on an HPC
- Explain the NGIAB community contribution process

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

## Community Contributions to NGIAB/NextGen

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

## Your Turn

Based on your own interests and use cases, try out some of these options:
- Build a development version of NGIAB locally
- Install and use NGIAB on your HPC environment
- Contribute to NGIAB/NextGen!

::::::::::::::::::::::::::::::::::::: keypoints 

- NGIAB can be built locally using Docker, allowing for development without pulling from the remote registry.
- NGIAB supports HPC environments through Singularity, not Docker, but the workflow mirrors the local Docker use.
- Community contribution guidelines are available in each repository's GitHub page.

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
