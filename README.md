# Project README

This project involves a comprehensive analysis of brain state transitions in resting-state fMRI data. It utilizes Leading Eigenvector Dynamic Analysis (LEiDA) to examine brain dynamics. The data, stored as a time series in BIDS format, undergoes several processing stages including Phase Dynamic Functional Connectivity (dFC), a Hilbert transformation, and clustering. The following sections provide a detailed description of each file and its role in this extensive analysis workflow.

## About Me

I am an undergraduate student at the University of Toronto studying Biology. Over the summer of 2024, I worked closely with my Principal Investigator, Dr. Colin Hawco, and PhD student Justin Ng on a Leading Eigenvector Dynamic Analysis (LEiDA) of resting-state fMRI data. Our research focused on examining the brain dynamics in relation to specific conditions.

For any inquiries, you can reach me at: [ifrah.ismail@mail.utoronto.ca](mailto:ifrah.ismail@mail.utoronto.ca).

## 1. Data Verifications

- **`currentseschecker.py`**  
  Checks the sessions and verifies the presence of subject directories. Ensures that all expected directories are available and correctly named, facilitating data consistency checks before further processing.

- **`hcp_patient02.py`**  
  Reads and processes patient data files related to the Human Connectome Project (HCP). Handles the extraction and preparation of patient-specific data for subsequent analysis.

- **`parametermaker.py`**  
  Generates parameter files by reading subject information related to resting-state fMRI scans. Focuses on creating input files for HCPEP183 subjects, preparing them for further analysis.

## 2. Voxelwise to Cortical Atlas

- **`meantimeseries.txt`**  
  Contains mean time series data for each subject in the resting-state fMRI dataset. Used to average and demean voxel-wise fMRI data according to the 360 cortical regions defined by the Glasser atlas. Converts voxel-level data into a cortical atlas format for higher-level analysis.

## 3. Extract, Cluster, and LEiDA

- **`clustering.m`**  
  A MATLAB script that performs k-medians clustering on LE(t) data for each run and participant. Stacks LE(t) matrices and conducts clustering with a specified number of clusters (`k`) for one of the 500 random iterations. Crucial for grouping data into meaningful clusters based on dynamic brain states.

- **`gatherstatejump.py`**  
  Aggregates state jump transition distances for all subjects across different runs. For a given clustering parameter (`k`), compiles transition distances into a comprehensive matrix, providing insights into state transitions on a group level.

- **`gatherstatetim.py`**  
  Calculates and collects correlations between state transition metrics and cognitive variables for the specified `k`. Explores the relationship between brain state dynamics and cognitive performance measures.

- **`LE_maker.py`**  
  Generates leading eigenvector (LE) matrices from the input data. Essential for preparing data for subsequent clustering and state analysis by extracting the LE features used in dynamic brain state studies.

- **`stateclass.py`**  
  Classifies brain states based on predefined criteria or results from clustering analysis. Helps in categorizing the identified states into meaningful groups for further interpretation.

- **`statesim.py`**  
  Simulates brain states based on input parameters and analyzes the results. Used to generate hypothetical scenarios or models of brain states, which can be compared against empirical data.

- **`statesort.py`**  
  Sorts and organizes brain states based on simulation outcomes or clustering results. Aids in arranging states in a systematic order for easier interpretation and analysis.

## 4. SLURM Scripts

- **`leida_slurm.sh`**  
  SLURM batch script designed to run LEiDA clustering analysis with specified parameters. Manages the execution of LEiDA tasks on a high-performance computing cluster, allowing for efficient processing of large-scale data.

- **`clusteringslurm.sh`**  
  SLURM batch script for executing general clustering tasks. Schedules and manages clustering jobs on the cluster, facilitating parallel processing and computation.

- **`statedynslurm.sh`**  
  SLURM batch script for conducting state dynamics analysis. Coordinates the execution of state dynamics tasks, ensuring they run efficiently on the computing cluster.

- **`statejumpslurm.sh`**  
  SLURM batch script for running state jump analysis. Handles job scheduling for the analysis of state transitions, optimizing computational resources.

- **`statesimslurm.sh`**  
  SLURM batch script for running simulations of brain states. Manages the execution of state simulation tasks, leveraging cluster resources for intensive computations.

## 5. Configuration and Parameter Files

- **`leidaparameters.txt`**  
  Contains parameters specific to LEiDA analysis, including configuration settings and thresholds for clustering. Provides the necessary inputs for running LEiDA algorithms.

- **`clusteringparameters.txt`**  
  Lists parameters for general clustering tasks, including details such as the number of clusters (`k`) and other relevant settings. Guides the clustering process across different analyses.

- **`reconfigparameter.txt`**  
  Provides parameters for reconfiguring analysis setups. Used to adjust settings or parameters for different iterations or experimental conditions.

- **`meantimeseries.ts`**  
  Time series data file containing mean time series information, used in conjunction with `meantimeseries.txt` for analysis.

- **`hcp_fulldata.txt`**  
  Contains comprehensive data from the Human Connectome Project (HCP) in text format. Includes detailed subject data for analysis.

- **`hcp_fulldata.yaml`**  
  YAML configuration file related to HCP data. Provides structured metadata and settings for processing HCP data.

- **`statejump.py`**  
  Python script for analyzing state jumps, focusing on transitions between different brain states.

- **`statejumpslurm.txt`**  
  Text file related to SLURM job configuration for state jump analysis, potentially including job-specific settings or parameters.

## 6. Interactive Notebooks

- **`Interactive - stateclass.py.ipynb`**  
  Jupyter Notebook for interactive exploration and visualization of state classification results. Allows dynamic analysis and adjustment of classification parameters.

- **`Interactive - statesort.py.ipynb`**  
  Jupyter Notebook for interactive exploration and visualization of state sorting results. Facilitates an in-depth examination of state sorting processes and outcomes.

## 7. Miscellaneous Files

- **`group_stateanalyze.asv`**  
  MATLAB file for group-level analysis of state transitions, potentially a versioned script used for in-depth group analysis.

- **`statedyn.asv`**  
  MATLAB file for state dynamics analysis, likely a versioned script for studying the evolution of brain states over time.

- **`iterations.py`**  
  Python script handling iterative processes or simulations. Used for running multiple iterations or experiments in the analysis.

- **`k_LE_1D.csv`**  
  CSV file containing results from the 1D LE (leading eigenvector) clustering analysis. Includes clustering outcomes for further review.

- **`stateclass.py`**  
  Python script for classifying brain states based on analysis results. Used to categorize states into predefined groups.

- **`statesimslurm.sh`**  
  SLURM script for executing state simulation tasks on the cluster. Manages job scheduling for simulation experiments.

---
## Data Access

You can access the data for this project in my [GitHub repository](https://github.com/ifrahismail/dFC_cogcorr). The data includes the most recent updates as of August 2024.

This README provides comprehensive descriptions for each file, outlining their specific roles and how they contribute to the overall analysis workflow.

