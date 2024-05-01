# NYC_congestion_modeling
We determine optimal toll pricing for incoming cars for the Queens Midtown Tunnel. We use a publicly available dataset linked <a href="https://data.ny.gov/Transportation/Hourly-Traffic-on-Metropolitan-Transportation-Auth/qzve-kjga/about_data">here</a> that tracks hourly traffic from 2010-presen on all major bridges and tunnels entering NYC. We formulate this problem as a CTMC stochastic process, fitting paramters from the dataset using Maximum Likelihood Estimates, and determining an optimal pricing scheme based on the steady state distribution of the CTMC. 

### Notebooks:
- `EDA.ipynb`: notebook for conducting basic exploratory data analysis on the dataset
- `data_filter.ipynb`: reads in houly traffic dataset and keeps only data points corresponding to incoming traffic at the Queens Midtown Tunnel. Writes this filtered data to Queens_Midtown_Tunnel.csv
- `data_conversion.ipynb`: reads in Queens_Midtown_Tunnel.csv and converts it into CTMC-friendly observations. Writes this to CTMC_QMT.csv
- `MLE.ipynb` reads in CTMC_QMT.csv and uses previously closed-form MLE for CTMC parameters to fit rate and transition probabilities to CTMC. Calculates steady state distribution.
- `pricing_model.ipynb`: determines optimal prices based on the steady state distribution of the CTMC

### Data Files:
- `CTMC_QMT_Bucket_*`: 4 different files contining the modified CTMC-friendly observations for 5,10,15,and 20 state CTMCs
- `Hourly_Traffic_on_Metropolitan_Transportation_Authority__MTA__Bridges_and_Tunnels__Beginning_2010_20240319.csv`: original dataset
- `Queens_Midtown_Tunnel.csv`: filtered data that only includes data of cars incoming (entering Manhattan) through the Queens Midtown Tunnel