# NYC_congestion_modeling
Determining optimal toll pricing for bridges and tunnels entering NYC by modeling congestion states as a continuous-time Markov chain

### File Descriptions:
- `data_filteripynb` reads in houly traffic dataset and keeps only data points corresponding to incoming traffic at the Queens Midtown Tunnel. Writes this filtered data to Queens_Midtown_Tunnel.csv
- `data_conversion.ipynb` reads in Queens_Midtown_Tunnel.csv and converts it into CTMC-friendly observations. Writes this to CTMC_QMT.csv
- `MLE.ipynb` reads in CTMC_QMT.csv and uses previously closed-form MLE for CTMC parameters to fit rate and transition probabilities to CTMC. Calculates steady state distribution.  