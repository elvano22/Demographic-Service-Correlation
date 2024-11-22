# Demographic-Service-Correlation

## Overview
This project investigates the relationship between demographic factors and access to basic services in Indonesian provinces using **Canonical Correlation Analysis (CCA)**. The analysis provides insights into the multidimensional relationships between population growth, density, and service accessibility (e.g., water, sanitation, and healthcare).

The study revealed:
- A strong canonical correlation (0.728 for the first function) between demographic variables and service accessibility.
- Key variables influencing these relationships include **population density** (demographic factor) and **access to sanitation** (service accessibility).

## Files
- **Code.Rmd**: Contains the R code used for analysis, including data preprocessing, transformation, assumption testing, and CCA.
- **Dataset_Kesehatan.xlsx**: Dataset containing variables for population dynamics and service accessibility across Indonesian provinces.
- **AOL Multivariate Kelompok 3.docx**: Detailed analysis report explaining methods, results, and interpretations.
- **Canonical_Correlation_Analysis_Document.docx**: A structured Word document summarizing the study's findings.

## Methodology
1. **Data Preprocessing**:
   - Variables were grouped into two categories:
     - **Demographic Factors**: Population growth rate, percentage, and density.
     - **Access to Basic Services**: Drinking water, sanitation, and healthcare.
   - Data transformations (log, square root, Box-Cox, Yeo-Johnson) were tested to ensure assumptions were met.

2. **Assumption Testing**:
   - **Multivariate Normality**:
     - Pre-transformation p-values indicated violation of normality (e.g., p < 0.05).
     - Post Yeo-Johnson Transformation: p-values for both groups satisfied normality assumptions.
   - **Multicollinearity**:
     - Variance Inflation Factor (VIF) values for all variables were below 10, indicating no multicollinearity.
   - **Linearity**:
     - Correlation analysis confirmed linear relationships post-transformation.

3. **Canonical Correlation Analysis**:
   - Canonical coefficients, weights, and loadings were calculated for each group.
   - Statistical tests:
     - Wilks’ Lambda (F-approximation) showed the first canonical correlation (p = 0.000877) was significant.

## Key Results
### Canonical Correlation Coefficients
- **First Function**: 0.728 (significant, p = 0.000877)
- **Second Function**: 0.427 (not significant, p > 0.05)
- **Third Function**: 0.063 (not significant, p > 0.05)

### Variable Importance
- **Demographic Factors**:
  - **Population Density**: Most significant variable with a canonical weight of -0.179.
  - **Population Growth Rate**: Contributed less significantly (-0.065).
- **Access to Basic Services**:
  - **Sanitation Access**: Strongest contributor with a canonical weight of -0.110.
  - **Healthcare Access**: Moderate contribution (-0.080).

### Loadings and Relationships
- Population density exhibited a strong negative correlation (-0.807 loading), indicating an inverse relationship with access to services.
- Sanitation access had the highest positive loading (0.909), emphasizing its importance in determining service accessibility.

### Statistical Tests
- Wilks’ Lambda for the first canonical function was 0.383 with an F-approximation p-value of 0.000877.
- Remaining functions were not statistically significant (p > 0.05).

## Interpretation
- High population density is strongly correlated with lower access to basic services, highlighting regional disparities.
- Improving sanitation and healthcare access is critical for mitigating the effects of demographic pressures in densely populated areas.

## Usage
### Requirements
Install the required R libraries using:
```R
install.packages(c('expm', 'car', 'MASS', 'bestNormalize', 'MVN', 'mvShapiroTest', 'CCP', 'CCA', 'GGally'))
```

### Running the Code
1. Open the `Code.Rmd` file in RStudio.
2. Ensure `Dataset_Kesehatan.xlsx` is in the correct path as specified in the code.
3. Run the code sequentially for preprocessing, assumption testing, and analysis.
4. Outputs include canonical coefficients, weights, and diagnostic plots.

### Outputs
- Canonical coefficients for three functions.
- Weights and loadings for interpreting variable contributions.
- Assumption validation plots and correlation matrices.

## Key Insights
- Canonical correlation analysis is a powerful method for exploring relationships between demographic factors and service accessibility.
- Policymakers can use these findings to prioritize resource allocation in regions with high population density and poor sanitation access.
