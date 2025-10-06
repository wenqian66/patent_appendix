# patent_appendix
# Apply KPSS2017 code to patent data 
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
