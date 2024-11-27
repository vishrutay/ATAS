# Details of Stat_csv_files Folder

Files designated for analyzing AWS (17 participants) and AWNS (18 participants) data, as outlined in the citation document.   

Function files to use:  

ATAS_functions.ipynb  
Long_short_pause_compute_functions.ipynb  

  < br / > 
  < br / > 
  
Input file for Streamlined_ATAS_AWNS.ipynb:  
AWNS_details.csv  
(File contains start time (Start_time) and end time (optional) inputs based on the length of original file to be analyzed/ inputs for trimming the original file)

Input file for Streamlined_ATAS_AWS.ipynb:  
AWS_details.csv  
(File contains start time (Start_time) and end time (optional) inputs based on the length of original file to be analyzed/ inputs for trimming the original file)

  < br / > 
  
Output file from Streamlined_ATAS_AWNS.ipynb:  
AWNS_All_files_together_50_ms_1_win_50_150_csv.csv (The description of the columns can be found in ATAS/README.md)   

Output file from Streamlined_ATAS_AWS.ipynb:    
AWS_All_files_together_50_ms_1_win_50_150_csv.csv (The description of the columns can be found in ATAS/README.md)    

  < br / > 
  < br / > 
  
Input file for Compute_long_and_short_pause_stats.ipynb (applicable if there are %SS scores (as in this case) or any other scores to be analyzed):  
AWS_SSI_details.csv  
Columns: 'No_of_stuttered_syllables', 'No_of_total_syllables', 'Percent_syllables_stuttered', 'Score'  
The relevant column for this analysis: 'Percent_syllables_stuttered'

  < br / > 
Output file from Compute_long_and_short_pause_stats.ipynb:    
AWNS_AWS_all_details.csv (The description of the columns can be found in ATAS/README.md)   

