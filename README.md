# dFC_cogcorr


Data Verifications:
1. Currentseschecker.py - Check the sessions with subject directories. 

  hcp_patient02.py - Reading in Patient files

  parametermaker.py - Read HCPEP183 subjects with resting-state fMRI scans.
2. Voxelwise to Cortical Atlas 

  meantimeseries.txt - For each resting-state subject ID, use the 360 cortical Glasser atlas to average demeaned voxelwise fMRI data.
  
3. Extract, Cluster and LEIDA
  Clustering.m - For the LE(t) for each run and each participant, stack them and conduct k-medians clustering with a specified k for one     random iteration of 500. 

  gatherstatejump.py - LE_group_statesim_gather.py - For the selected k, gather the idiosyncrasies across all subjects across runs and within run.

  gatherstateim.py - For the specified k and cognitive variable, find the correlations with the idiosyncrasy metrics and the corresponding uncorrected p-values.

  statedyn - Adding state labels to 'k' 
4. R-Correlations 
  T-test - T-test between patients and healthy controls, with age adjusment and FDR correction.  

  dwell_corr - Pairwise correlation for dwell time and Fluid, Crystal and Total composite scores.

  idio_corr - Pairwise correlation for idiosyncrasy  time and Fluid, Crystal and Total composite scores. 

  trans_corr - Pairwise correlation for transition distances  time and Fluid, Crystal and Total composite scores. 

  pyschodFCcogg - An attempt at T-test and some correlations. 
