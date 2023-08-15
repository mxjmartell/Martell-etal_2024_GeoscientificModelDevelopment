[![DOI](https://zenodo.org/badge/265119113.svg)](https://zenodo.org/badge/latestdoi/265119113)

# Martell et al. (2023) Nature Scientific Data - Data Descriptor
Statistical Analysis of the Weather Research and Forecasting Model Thermodynamic Global Warming Simulation Dataset for Outliers and Anomalies
Repository for the TGW WRF QA/QC process within IM3

Max Martell, Casey McGrath, Travis Thurber
Corresponding author(s): Max Martell (max.martell@pnnl.gov)

## Abstract
This paper describes a dataset created for quality assurance and quality control (QA/QC) methodology applied to the Weather Research and Forecasting (WRF) model Thermodynamic Global Warming (TGW) simulation. The 40-year WRF historical dataset (1979-2019) and future time period datasets were analysed for 25 variables over the contiguous United States. Statistical analyses were performed to assess data quality, including summary statistics, tests for normality, and identification of outliers. Specific anomalies were also investigated, such as non-physical values. The standardized QA/QC methodology and resulting dataset provide a framework for comparable climate models to assess and improve confidence in simulation outputs. The QA/QC dataset and code used to generate it are publicly available. This methodology enables rigorous evaluation of model accuracy, while remaining feasible for models with limited resources, demonstrating a straightforward approach to QA/QC that enhances reliability of climate model datasets.

## Code Reference
https://github.com/IMMM-SFA/wrf_qa_qc

## ReadMe
-create_climate_variables.py creates the new climate varaibles (like RH), find_stats_and_dist.py is the functions for analysis of stats and distributions, find_outliers.py is the functions for analysis of outers, get_monthly_stats.py calls the functions and stores them as netcdf files in nested yearly directories by month for "*all_stats.nc", "*all_outliers.nc" and "*normality.nc" (normality stored separately from "*all_stats.nc, since it is a single value across time, and space). Finally run_in_parralell.py runs the analysis in parallel by year

-filter_outliers_nan.py, and run_filter_outliers.py removes the padded nans from the "*all_outliers.nc" files
