[![DOI](https://zenodo.org/badge/265119113.svg)](https://zenodo.org/badge/latestdoi/265119113)

# Martell et al. (2024) Geoscientific Model Development
Statistical Analysis of the Weather Research and Forecasting Model Thermodynamic Global Warming Simulation Dataset for Outliers and Anomalies
Repository for the TGW WRF QA/QC process within IM3

Max Martell, Casey McGrath, Travis Thurber. 
Corresponding author(s): Max Martell (max.martell@pnnl.gov)

## Abstract
This paper describes a dataset created for quality assurance and quality control (QA/QC) methodology applied to the Weather Research and Forecasting (WRF) model Thermodynamic Global Warming (TGW) simulation. The 40-year WRF historical dataset (1979-2019) and future time period datasets were analysed for 25 variables over the contiguous United States. Statistical analyses were performed to assess data quality, including summary statistics, tests for normality, and identification of outliers. Specific anomalies were also investigated, such as non-physical values. The standardized QA/QC methodology and resulting dataset provide a framework for comparable climate models to assess and improve confidence in simulation outputs. The QA/QC dataset and code used to generate it are publicly available. This methodology enables rigorous evaluation of model accuracy, while remaining feasible for models with limited resources, demonstrating a straightforward approach to QA/QC that enhances reliability of climate model datasets.

## Code Reference
https://github.com/IMMM-SFA/wrf_qa_qc

## Reproducing Datasets
* create_climate_variables.py creates the new climate varaibles (like RH), find_stats_and_dist.py is the functions for analysis of stats and distributions, find_outliers.py is the functions for analysis of outers, get_monthly_stats.py calls the functions and stores them as netcdf files in nested yearly directories by month for "*all_stats.nc", "*all_outliers.nc" and "*normality.nc" (normality stored separately from "*all_stats.nc, since it is a single value across time, and space). Finally run_in_parralell.py runs the analysis in parallel by year

* filter_outliers_nan.py, and run_filter_outliers.py removes the padded nans from the "*all_outliers.nc" files

## Usage Notes
The QA/QC dataset can be accessed using the Xarray Python package, but the files are stored as NetCDF data, so any language with NetCDF reading capability may be used. The outlier and anomaly tables stored in Python dictionaries can be accessed using standard Python dictionary methods. The structure for these dictionaries is shown below: 

* outlier_dict[month (int)][outlier_type (str)][variable (str)]

If the user is interested in any additional analysis or in reproducing the data, the analysis code is wrapped into a single function with arguments to specify the date range of data and analysis types to perform. The code itself is designed to be highly modular for customizing further analyses and including additional functions.

## References
* Jones, A.D., D. Rastogi, P. Vahmani, A. Stansfield, K. Reed, T.B. Thurber, P. Ullrich, & J.S. Rice, (2022). IM3/HyperFACETS Thermodynamic Global Warming (TGW) Simulation Datasets (v1.0.0). MSD-LIVE Data Repository. [doi:10.57931/1885756](https://www.osti.gov/biblio/1885756 "IM3/HyperFACETS Thermodynamic Global Warming (TGW) Simulation Datasets")
