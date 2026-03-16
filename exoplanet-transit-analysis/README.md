#  Exoplanet Transit Analysis — Detecting and Modeling an Exoplanet Transit from Real Light Curve Data

## 1. Project Overview

This project focuses on **detecting and characterizing an exoplanet transit** from real astronomical photometric data.  
Using methods commonly employed by missions such as *Kepler* or *TESS*, the objective was to identify periodic dips in stellar brightness that correspond to a planet passing in front of its host star.

The analysis combines **data preprocessing, detrending, transit detection with the Box Least Squares (BLS) algorithm, and physical transit modeling** to estimate planetary parameters such as orbital period, transit depth, and planet radius.

The notebook follows a fully documented scientific workflow — from raw data to physical interpretation — emphasizing reproducibility and analytical reasoning rather than automated pipelines.


## 2. Objectives

- Detect periodic signals consistent with exoplanet transits.  
- Model the light curve and estimate key planetary parameters:  
  - Orbital period (P)  
  - Transit duration  
  - Depth and planet-to-star radius ratio (Rp/Rs)  
- Derive the approximate planet radius assuming a solar-type star.  
- Compare the obtained results with values from the scientific literature to validate the methodology.  


## 3. Methodology

The notebook is structured like a scientific analysis, with clear and progressive sections:

1. **Scientific Background** — Theoretical explanation of exoplanet transits and the photometric detection principle.  
2. **Data Access and Cleaning** — Loading raw light curve data, removing null and outlier flux values, and normalizing brightness.  
3. **Detrending** — Removing long-term stellar variability to isolate potential transit signals.  
4. **Transit Detection (BLS Algorithm)** — Using Box Least Squares to detect the periodic dips caused by transits and estimate the orbital period.  
5. **Transit Folding and Modeling** — Aligning the light curve on the detected period and fitting a trapezoidal transit model to extract physical parameters.  
6. **Parameter Estimation** — Deriving Rp/Rs, transit depth, and estimated planet radius, assuming a solar-type star.  
7. **Error and Uncertainty Analysis** — Quantifying the precision and limits of the model parameters.  
8. **Comparison with Literature** — Validating results by comparing with published exoplanet catalogs (radius, period, and depth consistency).  
9. **Conclusion** — Summary of findings and potential improvements (MCMC fitting, limb darkening, stellar parameter refinement).


## 4. Results Summary

| Parameter | Estimated Value | Description |
|------------|-----------------|--------------|
| Orbital period (days) | 0.8373 | Time between consecutive transits |
| Transit depth (ppm) | 99 | Relative brightness decrease during transit |
| Transit duration | 1.93 hours | Time span of the transit event |
| Rp/Rs | 0.00623 | Planet-to-star radius ratio |
| Estimated planet radius | 0.68 Earth radii | Assuming a 1 R☉ host star |

These values are consistent with a **small terrestrial planet**, orbiting very close to its star — a configuration typical of short-period exoplanets detected by missions like *Kepler*.


## 5. Tools and Libraries

- **Python 3.11+**
- `NumPy`, `Pandas` — Data manipulation  
- `Matplotlib`, `Seaborn` — Visualization  
- `Astropy` — Astronomical time and light curve handling  
- `Lightkurve` — BLS detection and photometric processing  
- `SciPy` — Signal detrending and numerical fitting  


## 6. Insights and Takeaways

- The project demonstrates the **entire analytical pipeline** of an astrophysical data science task — from raw data cleaning to scientific inference.  
- It highlights the importance of **detrending and model selection** in extracting faint periodic signals.  
- The results show consistency with **published exoplanet parameters**, validating the workflow and methodology.  
- This notebook bridges physics and data science by combining **signal processing, modeling, and interpretability**.


## 7. Repository Structure

exoplanet-transit-analysis/
├── notebooks/
│   └── exoplanet_analysis.ipynb
└──── README.md


## 8. Future Work

- Integrate **Bayesian parameter estimation** with `emcee` or `PyMC3` for uncertainty quantification.  
- Include **limb darkening models** for more precise fits.  
- Automate the pipeline for batch analysis of multiple stars.  
- Deploy an interactive visualization dashboard using `Plotly` or `Streamlit`.



Author : **Sergio Sánchez**
