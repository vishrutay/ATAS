# Details of Long_Pause_Short_Pause_Compute Folder  

Compute_long_and_short_pause_stats.ipynb computes long and short pause metrics for each participant data file 
using the ATAS outputs.    

-----------------------------------------

Inputs required   (Also refer to the ATAS/Stat_csv_files folder)  

The output files from ATAS_Multiple_Files_Analysis codes: Streamlined_ATAS_AWNS.ipynb and Streamlined_ATAS_AWS.ipynb
are used an input for Compute_long_and_short_pause_stats.ipynb.   
They are:  
Output file from Streamlined_ATAS_AWNS.ipynb:
AWNS_All_files_together_50_ms_1_win_50_150_csv.csv (The description of the columns can be found in ATAS/README.md)  

Output file from Streamlined_ATAS_AWS.ipynb:
AWS_All_files_together_50_ms_1_win_50_150_csv.csv (The description of the columns can be found in ATAS/README.md)  

Additionally, individual time-series data files derived from each participant data file are also used as an input 
to compute long and short pause information.   
(ATAS/ATAS_Multiple_Files_Analysis/Individual_OutputCSV_Files) e.g. 24fa_f.csv

Also, % Syllable Stuttered (%SS) data is stored in the ATAS/Stat_csv_files/AWS_SSI_details.csv file which 
is used to incorporate the %SS data along with all the ATAS derived data including the long and short pause data. 
------------------------------------------  

The output file for Compute_long_and_short_pause_stats.ipynb is ATAS/Stat_csv_files/AWNS_AWS_all_details.csv  
which provides comprehensive data associated with each participant data file incorporated with the pre-calculated 
clinically relevant metric/s.  

(The description of the columns for AWNS_AWS_all_details.csv can be found in ATAS/README.md)
