# DCN-ELA-dimensions
Scripts and output for "Characterizing the dimensional structure of early-life adversity in the Adolescent Brain Cognitive Development (ABCD) Study"

5/22/23: We are actively working to refine project scripts to facilitate reproducibility. Please reach out with any questions.

Note: data cannot be shared publicly per ABCD Study data sharing guidelines. Data can be accessed through the National Data Archive at https://nda.nih.gov/abcd/ with an approved Data Use Certification.

This repository contains the following:

01_data_preparation - a directory with scripts and outputs needed to import, prep, and clean data for analysis

  01_pull_variables.Rmd
    -Purpose: read in and merge all necessary data files from the National Data Archive (NDA)
    -Output: a .csv file with 9854 subjects and 79 variables
    -Note: Data for this project were derived from the ABCD 4.0 release (baseline data)
    -Data files (12):
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
    -Output: a .csv file with 7115 subjects and 83 variables
  
  03_aggregate_data.Rmd
    -Purpose: identify variables with high correlations, aggregate any variables that are highly correlated and 
    conceptually similar to retain in factor analysis
    -Output: .csv file with correlation matrix; .csv file with 7115 subjects and 61 variables
    
  04_supplemental_analysis_data.Rmd
  
02_factor_analysis - a directory with factor analysis inputs and outputs
  
  EFA_full_sample.inp/.out
    -Mplus script for Exploratory Factor Analysis with the full analytic sample (as opposed to supplemental leave-site-out analyses)
    -Generates eigenvalues and model fit indices to help determine optimal model
    -Note: Mplus cannot handle string values, so the NDA subject key needs to be replaced
    
  ESEM_10_factorscores.inp/.out
    -Mplus script for Exploratory Structural Equation model that specifies 10 factors (based on EFA results)
    -Exports factor scores for 10 factors as .dat file
    -Note: it is necessary to specify as ESEM (rather than EFA) in order to obtain factor scores from Mplus
    
  factor_loadings_10factors.xlsx
    -formatted factor loadings from EFA 10 factor solution
    
  supplemental_site_analysis - a directory with inputs and outputs for the EFA analysis with one site removed
    -systematically removed one site for each iteration, 22 sites total resulting in 22 iterations

03_mds - a directory with files for multidimensional scaling analyses

  plots - a directory with plot outputs
  
  scripts - a directory with scripts for multidimensional scaling analysis
    
    01a_mds_trainset_allitems.Rmd
    -Purpose: run mds with training set
    -Output: mds goodness of fit metrics and plots
    
    01b_mds_validset_allitems.Rmd
    -Purpose: run mds with validation set
    -Output: mds goodness of fit metrics and plots
    
    02_mds_trainset_childitems.Rmd
    -Purpose: run mds removing parent report items to see if results change
    -Output: mds goodness of fit metrics and plots
    
    03_mds_trainset_parentitems.Rmd
    -Purpose: run mds removing child report items to see if results change
    -Output: mds goodness of fit metrics and plots
  
04_outcomes - a directory with files for analyses testing associations between adversity factors and child outcomes

  plots - a directory with .jpeg plot outputs
  
    scripts - a directory with scripts for outcome analyses
  
    01_data_cleaning_full.Rmd
    -Purpose: merge outcome variables with adversity factors and clean
    -Output: two cleaned .csv data files (one wide format, one long)
    -Data files needed: 10factors_fscores.csv (from 02_factor_analysis), abcd_cbcls01.csv (from NDA),         abcd_tbss01.csv (from NDA)
    
    02_correlations_full.Rmd
    -Purpose: test correlations between factor scores and outcomes
    -Output: .jpeg heatmaps
    
    03_regression.Rmd
    -Purpose: run regression model for associations between factor scores and outcomes (with test and 
    validation sets), including multivariate multilevel models
    -Output: model fits and parameter estimates, plots
    
    04_mvmlm_plots.Rmd
    -Purpose: plot results from the multivariate multilevel models
    -Output: mvmlm plots, scatterpolots for spearman correlations between actual and predicted child
    behavior scores
  
  
  