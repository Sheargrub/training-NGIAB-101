---
title: "Installation and Setup"
teaching: 10
exercises: 2
---

This episode can be a standalone tutorial for those who want a quick introduction to NGIAB. This tutorial follows the case study from our [CloudInfra repository](https://github.com/CIROH-UA/NGIAB-CloudInfra). Users who wish to learn more about NGIAB can explore our other episodes in this module. 

## Questions

- How do I install and set up NGIAB?
- What are the prerequisites for running NGIAB?
- How do I verify my installation?

## Objectives

- Install and verify Docker
- Set up NGIAB project directories
- Run a sample NGIAB simulation

## Introduction

This lesson guides you through installing and setting up NGIAB, a containerized solution designed to simplify running the NextGen modeling framework locally. NGIAB leverages Docker containers to ensure consistent and reproducible simulations.

## System Requirements

Before installing NGIAB, ensure you have:

- **Operating System:** Windows (with WSL), macOS, or Linux  
- **Software:** Docker, Git  
- **Recommended Minimum RAM:** 8 GB

## Docker Installation

### Windows (WSL)

1. Install Windows Subsystem for Linux (WSL):
   ``` bash
   wsl --install
	```

2.  Install Docker Desktop from Docker's official website.
    
3.  Launch Docker Desktop and open WSL terminal as administrator.
    
4.  Verify Docker installation:
    
    ```bash
    docker run hello-world
    
    ```
    

### macOS

1.  Install Docker Desktop from Docker's official Mac installer.
    
2.  Launch Docker Desktop.
    
3.  Verify Docker installation:
    
    ```bash
    docker run hello-world
    
    ```
    

### Linux

1.  Install Docker by following the official Docker guide.
    
2.  Start Docker service and verify:
    
    ```bash
    sudo systemctl start docker
    docker run hello-world
    
    ```
    

## ✅ Challenge 1: Verify Docker

Run the command below:

```bash
docker ps -a

```

Confirm it executes without errors. If errors occur, revisit Docker installation steps.

### Solution

If `docker ps -a` fails, ensure Docker Desktop is running, or Docker service is active on Linux:

```bash
sudo systemctl start docker

```

## NGIAB Setup

These steps will lead you through the process of running NGIAB with a set of pre-configured input data and realization files.

### Step 1: Create Project Directory

```bash
mkdir -p NextGen/ngen-data
cd NextGen/ngen-data

```

### Step 2: Download Sample Data

Choose one of the following datasets:

**Option 1: Provo River (AWI-009)**

```bash
wget https://ciroh-ua-ngen-data.s3.us-east-2.amazonaws.com/AWI-009/AWI_16_10154200_009.tar.gz
tar -xf AWI_16_10154200_009.tar.gz

```

**Option 2: AWI-007**

```bash
wget https://ciroh-ua-ngen-data.s3.us-east-2.amazonaws.com/AWI-007/AWI_16_2863657_007.tar.gz
tar -xf AWI_16_2863657_007.tar.gz

```

**Option 3: AWI-008 (with LSTM)**

```bash
wget https://ciroh-ua-ngen-data.s3.us-east-2.amazonaws.com/AWI-008/AWI_16_2863806_008.tar.gz
tar -xf AWI_16_2863806_008.tar.gz

```

### Step 3: Clone and Run NGIAB

```bash
cd ../  # back to NextGen folder
git clone https://github.com/CIROH-UA/NGIAB-CloudInfra.git
cd NGIAB-CloudInfra
./guide.sh

```

The interactive `guide.sh` script will prompt you to select input data, processing modes, and will initiate your simulation.

### Directory Structure (`ngen-run/`)

```
ngen-run/
├── config/
├── forcings/
├── lakeout/ (optional)
├── metadata/ (auto-generated, do not edit)
├── outputs/
└── restart/ (optional)

```

>**Tip:** Always run a quick simulation with provided sample datasets to verify the successful setup of NGIAB.

## Troubleshooting

-   Ensure Docker is running before executing `guide.sh`.
    
-   For permission errors on Linux, run Docker commands with `sudo` or add your user to the Docker group:
    

```bash
sudo usermod -aG docker ${USER}
newgrp docker

```
### Check: Did You Download the Dataset?
Run this command:
```bash
ls  ~/NextGen/ngen-data
```
You should see a folder like:
```
AWI_16_10154200_009
```
 If you see it, your dataset was downloaded and extracted correctly.

If you see nothing or just the `.tar.gz` file, run the following again:
```bash
tar  -xf  AWI_16_10154200_009.tar.gz
```
### Are You in the Right Directory?
Before running any script, always check your current folder:
```
pwd
```
You **should see something like**:
```
/home/yourname/NextGen/NGIAB-CloudInfra
```
If not, move into the folder:
```
cd ~/NextGen/NGIAB-CloudInfra
```
## Additional Resources

Are you interested in customizing your run with your own catchments and run configurations? Do you want to explore more functionalities of NGIAB? Check out the following episodes:

-   Data Preparation - NGIAB Data Preprocessor
    
-   Evaluation - NGIAB TEEHR Integration
    
-   Visualization - Data Visualizer
    

## Key Points

-   NGIAB simplifies NextGen framework deployment through Docker.
    
-   Use `guide.sh` for interactive configuration and simulation execution.
    
-   Always confirm successful setup by running provided sample simulations.

----------
## ✅ You're All Set!

If you've completed the steps above and verified your dataset and working directory, you're ready to run the interactive guide script:

```bash
./guide.sh
```
This will walk you through the NGIAB setup and launch your first simulation.

::::::::::::::::::::::::::::::::::::: callout

- A series of prompts will appear that ask you if you want to use the existing Docker image or update to the latest image. Updating to the latest image will take longer, so for the purposes of this tutorial, using the existing Docker image is fine.
- When prompted to run NextGen in serial or parallel mode, either is fine.
- The option to open a Bash shell (interactive shell) will allow you to explore the data directory without quitting NGIAB.
- Redirecting command output to `/dev/null` significantly reduces the amount of output. Either is fine, but if you are curious about what is happening inside NextGen, we suggest that you don't redirect the output.

::::::::::::::::::::::::::::::::::::::::::::::::