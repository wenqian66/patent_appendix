# patent_appendix
# 1. Apply KPSS2017 code to patent data 
1997-2021
```text
July18/
├── code/                                 
│   ├── 1firmiqr.do                          # hfirmiqr = (q3(ret-vwretd)-q1(ret-vwretd))/2
│   ├── 2newproduct.do                       # Create product-level dataset
│   ├── 2product_crsp.do                     # Merge product data with CRSP identifiers
│   ├── 3CompustatData.do                    # Merge Compustat + CRSP + NIPA + GDP + AWI + SIC
│   ├── 3tfp.do                              
│   ├── 4FilterReturnsCreateFirmMeasures.do  # Eq 3,4,6,9, compute firm-year level patent value
│   ├── 5CreateFirmSample.do                 # merges the patent measure with Compustat data and creates the needed variables to run the firm-level regressions*
│   ├── 6_t1PatentValueCites.do              # TABLE I
│   ├── 7_t3FirmSummaryStats.do              # TABLE III; descriptive statistics
│   ├── 8_t4aFirmProfitsRegressionSM.do      # TABLE IIII
│   ├── 8_t4bFirmOutputRegressionSM.do       
│   ├── 8_t4cdFirmReallocationRegressionSM.do
│   ├── 8_t4eFirmTFPRegressionSM.do          
│   │
│   ├── cluster2.ado                         
│   ├── eq6delta.do                          #regression in footnote13
│   └── sic.dta                              
│
├── data/                                 
├──  output/
│   ├── eq6gamma
│   ├── 7_t3FirmSummaryStats
│   ├── t1
├── crsp_dsi.csv                            # Input for 1firmiqr.do; 2product_crsp.do     
├── crsp_dsf.csv                            # Input for 1firmiqr.do; 2product_crsp.do  
├── firmiqr.dta                             # Output from 1firmiqr.do; Input for 4FilterReturnsCreateFirmMeasures.do and 6_t1PatentValueCites.do
├── newproduct_crsp_ccm.csv                 # Input for 2newproduct.do 
├── newproduct_GPT_results_manual_cleaned.csv # Input for 2newproduct.do
├── newproduct_base.dta                     # Output from 2newproduct.do; input for 2product_crsp.do
├── product.dta                             # Output from 2product_crsp.do; Input for 4FilterReturnsCreateFirmMeasures.do and 6_t1PatentValueCites.do
├── price_k.csv                             # Input for 3CompustatData.do  
├── gdp.csv                                 # Input for 3CompustatData.do  
├── awi.csv                                 # Input for 3CompustatData.do  
├── comp_funda.csv                          # Input for 3CompustatData.do  
├── linktable.dta                           # Input for 3CompustatData.do  
├── CompustatData.dta                       # Output from 3CompustatData.do  
├── tfp.dta
├── firm_Af.dta                             # Output from 4FilterReturnsCreateFirmMeasures.do
├── Comp_data.dta                           # Output from 3tfp; Input for 5CreateFirmSample.do
├── CPIAUCNS.csv                            # Input for 5CreateFirmSample.do
├── firm_data.dta                           # Output from 5CreateFirmSample.do
                            
```

# 2. Regression

**1) Equation 12: theta_ft, theta_i/ft using product_value**

**2) Equation 12: two theta_ft using product_value and patent_value**

**3) 4 vars**

```text
Aug1/
├── code/
│   ├── 1a_profit.do                    # 1) log(profits/cpi*100)
│   ├── 1b_output.do                    # log((sale+Dinvt)/cpi*100)
│   ├── 1cd_emp_cap.do                  # log(ppegt/price_k); log(emp)
│   │ 
│   ├── 2a_profit.do                    # 2)
│   ├── 2b_output.do                    
│   ├── 2cd_emp_cap.do                  
│   │
│   ├── 3a_profit.do                    # 3)
│   ├── 3b_output.do                    
│   ├── 3cd_emp_cap.do                  
│   │
│   ├── cluster2.ado                    
│   ├── winsorizeJ.ado                  
│   └── qje.do                          # process 1997-2021 patent_value from https://github.com/KPSS2017/Technological-Innovation-Resource-Allocation-and-Growth-Extended-Data.git
├── data/
│   ├── firm_data.dta                       # Input for the regression
│   ├── qje_data.dta                        # Input for the regression
│   ├── ...{results.txt/tex}                # Regression results


```

# 3. Regression

```text
Aug14/
├── code/
│   ├── t1individual_level
│   ├── t2firm_year.do
│   ├── t3_vars4_1997_2021
│   ├── t4_patent1997_2021       
├── output/
│   ├── 1indiv_summary.tex                 # Descriptive Statistics (Individual level, 1997–2021): Product vs Patent
│   ├── 2agg_summary.tex                   # Descriptive Statistics (Firm-Year, 1997–2021): Product vs Patent
│   ├── t3_1997_2021.tex                   # same with regression 2 #3 
│   ├── t4.tex                             # regression using 1997-2021 patent value(TABLE 4; Eq12)
├── data/...                               # same as previous
```

# 4. R&D response to rival-product shocks + Leader/Laggard tags
```text
Sep16/
├── r1_interaction/                     
│   ├── 1a_dlogrd_laggard.do            
│   ├── 1a_dlogrd_leader.do             
│   ├── 1b_rdintensity_laggard.do       
│   └── 1b_rdintensity_leader.do
│        
├── r2_interaction/                     
│   ├── 2a_3y_inv_rate_laggard.do       # 3-year tag laggard & CAPX/AT
│   ├── 2a_3y_inv_rate_leader.do        # 3-year tag leader & CAPX/AT
│   ├── 2a_rtfp_inv_rate_laggard.do     # RTFP-based tag laggard & CAPX/AT
│   ├── 2a_rtfp_inv_rate_leader.do      # RTFP-based tag leader & CAPX/AT
│   ├── 2b_3y_cap_growth_laggard.do     # Δ ln(PPENT)
│   ├── 2b_3y_cap_growth_leader.do      
│   ├── 2b_rtfp_cap_growth_laggard.do   
│   ├── 2b_rtfp_cap_growth_leader.do    
│   ├── 2c_3y_cap_deepen_laggard.do     # Δ ln(PPENT / EMP)
│   ├── 2c_3y_cap_deepen_leader.do      
│   ├── 2c_rtfp_cap_deepen_laggard.do   
│   └── 2c_rtfp_cap_deepen_leader.do    
├── r1.pdf/
├── r2.tex/
```
**Step 1** 
* Dependent variable:
  Δ ln(XRD + 1) (primary)
  XRD / AT (robustness)

**Step 2** 
* Investment rate: CAPX / AT
* Capital growth: Δ ln(PPENT)
* Capital deepening: Δ ln(PPENT / EMP)

