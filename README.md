# HJGalaxy
Jupyter Notebook and ancillary files to reproduce the results of Mustill, Lambrechts and Davies (2021)

This repository contains files to reproduce the results of Mustill, Lambrechts & Davies, 2021, A&A, submitted.
If you make use of this repository, please cite Mustill, Lambrechts & Davies, 2021; a citation to Winter et al, 2020, Nature, 586, 528
would also be apposite if you make us of the Mahalanobis density technique

The repository contains the following files:

 - densities.ipynb
 Jupyter notebook to retrieve stellar kinematic data from the Gaia archive, evaluate the phase space densities of exoplanet host stars, and 
 generate the figures in Mustill, Lambrechts & Davies
 
 - PS_2021.03.11_04.56.35.csv
 Table of exoplanet and host star properties retrieved from https://exoplanetarchive.ipac.caltech.edu/ on 2021-03-11
 
 - log/xmatch_ids_1616414978.3437288.txt
 List of cross-matched ids; this will be used if Simbad cannot be accessed
 
 - log/flags1616429974.3911638.txt
 List of system attributes from a previous analysis run: messages will be printed if discrepancies arise
 
 - results
 Directory containing one subdirectory per target. Target subdirectory contains one subdirectory for the Gaia EDR3 analysis. This 
 contains the files:
  
  - TARGETNAME_GAIADR_seed
  saved RNG seed to ensure reproducibility of the Monte-Carlo analysis
  
  - TARGETNAME_GAIADR_densities.txt
  Table of Gaia ids, densities, and 6D positions of the target and up to 600 neighbouring stars. If this file exists, it will be read
  instead of generating a MC sample and calculating the densities (this takes up to a few minutes per target). This file will be 
  created or overwritten when anaylsis of the target is complete
  
  - TARGETNAME_GAIADR_densities.txt.backup
  Backup of the above file. This will not be read or changed by running the notebook, but you can check that your stellar densities are 
  the same as those originally calculated by diff'ing these two files. They may differ if, for example, the RNG differs between machines
  
 Figures generated per target will also be placed in the results/TARGETNAME/GAIADR/ directory. Most commands to generate figures are 
 commented out in the notebook to avoid making a surfeit of plots 
