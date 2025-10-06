# patent_appendix
# use patent data to the KPSS2017 code
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
    ├── eq6gamma
    ├── 7_t3FirmSummaryStats
    ├── eq6gamma
├── crsp_dsi.csv                            # Input for 1firmiqr.do; product_crsp.do     
├── crsp_dsf.csv                            # Input for 1firmiqr.do; product_crsp.do  
├── firmiqr.dta                             # Output for 1firmiqr.do; Input for 4FilterReturnsCreateFirmMeasures.do
├── newproduct_crsp_ccm.csv                 # Input for 2newproduct.do 
├── newproduct_GPT_results_manual_cleaned.csv # Input for 2newproduct.do
├── newproduct_base.dta                     # Output for 2newproduct.do
├── price_k.csv                             #  for 1firmiqr.do  
├── gdp.csv
├── awi.csv
├── comp_funda.csv
├── linktable.dta
├── CompustatData.dta
├── tfp.dta
├── Comp_data.dta
                            
```
