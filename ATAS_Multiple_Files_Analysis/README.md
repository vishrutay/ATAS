# Details of ATAS_Multiple_Files_Analysis Folder  

Streamlined_ATAS_AWNS.ipynb and Streamlined_ATAS_AWS.ipynb
Analyze multiple acoustic files in a loop to provide a compiled output csv file for all the participant data files. 

------------------------------------------  
Inputs required:  (Also refer to the ATAS/Stat_csv_files folder)  
Pre-processed (if required - as in this ptoject) acoustic files/ original acoustic data files. 

Input file for Streamlined_ATAS_AWNS.ipynb:
AWNS_input.csv
(File contains start time (Start_time) and end time (optional) inputs based on the length of original file to be analyzed/ inputs for trimming the original file)

Input file for Streamlined_ATAS_AWS.ipynb:
AWS_input.csv
(File contains start time (Start_time) and end time (optional) inputs based on the length of original file to be analyzed/ inputs for trimming the original file)

------------------------------------------  

Outputs:

Output file from Streamlined_ATAS_AWNS.ipynb:
AWNS_All_files_together_50_ms_1_win_50_150_csv.csv (The description of the columns can be found in ATAS/README.md)

Output file from Streamlined_ATAS_AWS.ipynb:
AWS_All_files_together_50_ms_1_win_50_150_csv.csv (The description of the columns can be found in ATAS/README.md)

Individual time-series data files derived from each participant  
Time-series data file are in ATAS/ATAS_Multiple_Files_Analysis/Individual_OutputCSV_Files  

