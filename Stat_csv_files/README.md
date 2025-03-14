# Details of Stat_csv_files Folder

Files designated for analyzing AWS (17 participants) and AWNS (18 participants) data, as outlined in the citation document.   
---------------------------------------------  
# Function files to use:    
Required in multiple .ipynb files

ATAS_functions.ipynb  
Long_short_pause_compute_functions.ipynb  

---------------------------------------------  
AWNS_details.csv  
AWS_details.csv  

Both these files provide details about the participants. 
Columns:  
'ID': ID for each participant which are also used to create the acoustic file names. e.g. if 'ID' - 24fa, then 'File_Name' - 24fa.wav    
'Group': AWNS or AWS  
'Age': Age of the participant in years  
'Sex: F or M  
'Total_words_expected': Total words in the passage to read
'Words_missing_at_end': Number of words missing at the end in the acoustic file - if any  
'Final_word_count': Total words in the acoustic file   


---------------------------------------------   

Input file for Streamlined_ATAS_AWNS.ipynb: AWNS_input.csv    
(File contains start time (Start_time) and end time (optional) inputs based on the length of original file to be analyzed/ inputs for trimming the original file)

Input file for Streamlined_ATAS_AWS.ipynb: AWS_input.csv    
(File contains start time (Start_time) and end time (optional) inputs based on the length of original file to be analyzed/ inputs for trimming the original file)

Output file from Streamlined_ATAS_AWNS.ipynb:  
AWNS_All_files_together_50_ms_1_win_50_150_csv.csv 
(The description of the columns can be found in ATAS/README.md)   

Output file from Streamlined_ATAS_AWS.ipynb:    
AWS_All_files_together_50_ms_1_win_50_150_csv.csv 
(The description of the columns can be found in ATAS/README.md)    

----------------------------------------------   
Input file for Compute_long_and_short_pause_stats.ipynb (applicable if there are %SS scores (as in this case) or any other scores to be analyzed):  
AWS_SSI_details.csv  
Columns: 'No_of_stuttered_syllables', 'No_of_total_syllables', 'Percent_syllables_stuttered', 'Score'  
The relevant column for this analysis: 'Percent_syllables_stuttered'

Output file from Compute_long_and_short_pause_stats.ipynb:    
AWNS_AWS_all_details.csv 
(The description of the columns can be found in ATAS/README.md)   

-----------------------------------------------  
Input file for Figure_5_6_7_8.ipynb (This file contains the group analysis details (GLMs and Neg Binomial models) for all the 13 metrcis for the predictor 'Group'):
pval.csv  
Columns: 'Metric', 'Predictor',	'Coefficient',	'Std Error',	'z-value',	'p-value',	'Model Type'    
The relevant column for analysis: 'p-value'  

