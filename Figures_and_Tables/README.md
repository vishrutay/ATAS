# Statistics and Table Data 
Group_statistics.ipnyb includes checking our model assumptions for all the 13 metrics. Based on the seven ATAS metrics and the additional six - long and short pause metrics which we focus on, we have used the GLM models on continuous data, and negative binomial models for all count data.  
This file provides all the Table outputs in the paper (Tables 1, 2, and 3).  
For inputs refer to ATAS/Stat_csv_files folder:  
AWNS_AWS_all_details.csv  

# Figures: 
Figure_1_2.ipynb, Figure_4.ipynb: Paper specific (requires raw and preprocess data files)  
  
Figure_5_6_7_8.ipynb: Generates figures for AWS and AWNS data comparission for selected metrics which are significantlly different between the groups. (Requires ATAS/Stat_csv_files/pval.csv and AWNS_AWS_all_details.csv files as input)  
  
Figure_9_DT.ipynb: Decision Tree model (with figures included in paper). (Requires Stat_csv_files/AWNS_AWS_all_details.csv as an input)  
  
Figure_9_RF.ipynb: Random Forest model (with figures included in paper). (Requires Stat_csv_files/AWNS_AWS_all_details.csv as an input)  
  
Figure_10_LSTM.ipynb: Long short-term memomry (LSTM) model (with figures included in paper). (Requires Stat_csv_files/AWNS_AWS_all_details.csv as an input)   
