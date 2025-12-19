# 📌 Risk Spillover Analysis from Real Estate to Financial Sector

This study analyzes the spillover risk transmission from the real estate sector to financial sectors in Vietnam during the period 2018–2024 using ΔCoVaR based on the ARMA–GJR–GARCH–DCC–Copula model.

## 📂 Files
- `Dữ liệu Lịch sử Banks.xlsx` - historical data for the banking sector

- `Dữ liệu Lịch sử Financial Services.xlsx` - historical data for the financial services sector

- `Dữ liệu Lịch sử Insurance.xlsx` - historical data for the insurance sector

- `Dữ liệu Lịch sử Real Estate.xlsx` - historical data for the real estate sector

- `Risk_Spillover_RealEstate_Financial_Vietnam_code.Rmd` - R Markdown source file with full code

- `Risk_Spillover_RealEstate_Financial_Vietnam_code.html` — rendered HTML output produced from the R Markdown file (viewable in browser)

## 🎯 Study Objective

- Measure the risk spillover effect from the real estate sector to key financial sectors in Vietnam:
  - banking (tổ chức tín dụng)
  - financial services (dịch vụ tài chính)
  - insurance (bảo hiểm)
  - general finance (tài chính nói chung)

- Provide empirical insights into risk spillover mechanisms between markets

## 📅 Data Description

- The dataset consists of daily closing prices and trading volumes from the Vietnamese stock market during 02/01/2018 to 31/12/2024.

- Data were collected from Investing.com, and sector classifications follow Vietstock.

- The period captures major market events:

  - 2018–2019: corporate bond boom
  - 2020–2021: COVID-19 and loose monetary policy
  - 2022–2024: inflation, monetary tightening, bond crisis and real estate distress

- Each sector (Real Estate, Banks, Financial Services, Insurance) is represented by the 20 largest Vietnamese listed companies by market capitalization, ensuring coverage of key market players.

- Industry indices are constructed using market-cap weighting and returns are calculated using continuous compounding.

## 🧠 Methodology Overview

- The study methodology follows a 5-step quantitative pipeline:

  - Step 1: Estimate the ARIMA(p,d,q) model for the return series and select the optimal ARIMA model, consistent for the entire dataset.  
  - Step 2: Combine ARIMA with GARCH/GJR-GARCH to model conditional variance and select the optimal GARCH model for all sectors.  
  - Step 3: From the standardized residuals of the ARIMA-GARCH model, estimate the Copulas (Gaussian, t, Clayton, Gumbel, Frank) and select the most appropriate Copula for each sector pair.  
  - Step 4: Use the DCC-GARCH model to obtain the time-varying correlation matrix for each sector pair.  
  - Step 5: Combine the time-varying correlations from the DCC model and the optimal Copula to calculate CoVaR and ΔCoVaR, reflecting the level of risk contagion between sectors over time.

## 🔍 Key Findings

- 2018-2019: Strongest risk contagion from real estate to finance, focusing on the non-bank sector.
- 2020-2021 (COVID-19): ΔCoVaR decreased due to loose monetary policies and abundant cheap capital, masking risks.
- 2022-2024: Risk contagion increased again, especially in insurance companies, driven by inflation, tightening policies and the corporate bond crisis.

## 📈 Tools & Libraries
- **R** programming language
- R packages:
  - `readxl`  
  - `tidyr`  
  - `dplyr`  
  - `purr`  
  - `stringr`  
  - `tseries`  
  - `FinTS`  
  - `fBasics`  
  - `urca`  
  - `lmtest`  
  - `forecast`  
  - `rugarch`  
  - `psych`  
  - `fGarch`  
  - `copula`  
  - `qrmtools`  
  - `lubridate`  

## 👤 Author

GiaPhuong2004

