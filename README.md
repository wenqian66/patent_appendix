# patent_appendix
# use patent data to the KPSS2017 code

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
│   ├── 8_t4aFirmProfitsRegressionSM.do      # TABLE IIII: 
│   ├── 8_t4bFirmOutputRegressionSM.do       
│   ├── 8_t4cdFirmReallocationRegressionSM.do
│   ├── 8_t4eFirmTFPRegressionSM.do          
│   │
│   ├── cluster2.ado                         # Two-way clustering ado (firm × year)
│   ├── eq6delta.do                          # Auxiliary Δ-equation regression
│   └── sic.dta                              # SIC-to-industry mapping data file
│
├── data/                                 # Raw and intermediate datasets (Compustat, CRSP, patents)
└── output/                               # Regression results, tables, and figures
