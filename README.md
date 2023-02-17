# DCN-ELA-dimensions
Scripts and output for "Characterizing the dimensional structure of early-life adversity in the Adolescent Brain Cognitive Development (ABCD) Study"

This repository contains the following:

01_data_preparation - a directory with scripts and outputs needed to import, prep, and clean data for analysis

  01_pull_variables.Rmd
    -Purpose: read in and merge all necessary data files from the National Data Archive (NDA)
    -Output: a .csv file with XX subjects and XX variables
    -Note: Data for this project were derived from the ABCD 4.0 release (baseline data)
    -Data files:
      -acspsw03.txt (family ID variable)
      -abcd_fhxssp01.txt (family substance use)
      -pdem02.txt (demographics including marital status, socioeconomic status, etc.)
      -crpbi01.txt (parenting)
      -fes02.txt (family environment scale, parent report)
      -abcd_fes01.txt (family environment scale, youth report)
      -abcd_ptsd01.txt (KSADS trauma interview)
      -pmq01.txt (parental monitoring)
      -abcd_sscep01.txt (neighborhood safety and crime, parent report)
      -abcd_nsc01.txt (neighborhood safety and crime, youth report)
      -abcd_asrs01.txt (parent psychopathology, ASR)
      -abcd_rhds01.txt (area deprivation index)
    
  02_data_cleaning.Rmd
    -Purpose: clean raw data and prepare for analysis (e.g., exclude relatives, handle mising values, recoding)
    -Output: a .csv file with XX subjects and XX variables
  
  03_aggregate_data.Rmd
    -Purpose: identify variables with high correlations, aggregate any variables that are highly correlated and 
    conceptually similar to retain in factor analysis
    -Output: .csv file with correlation matrix; .csv file with XX subjects and XX variables
    
  04_supplemental_analysis_data.Rmd
  
