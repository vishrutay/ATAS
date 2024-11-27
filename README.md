# ATAS
A pipeline for automatic detection of silent pauses in speech  
(...and much more)

This pipeline offers a user-friendly and flexible solution for understanding temporal speech patterns and analyzing stuttering-related metrics (in this context) or any other user-defined metrics, making it valuable for both research and clinical purposes.   


The figure below shows audio data from a reading sample in the open-source FluencyBank dataset, recorded from a participant, with color-coded ATAS-detected events.   

![image](https://github.com/user-attachments/assets/95824fbf-192a-43f0-af08-750b298eaf84)  


ATAS is designed to automatically detect silent pauses in speech and analyze them. It allows users to customize settings, such as thresholds for detecting pauses and vocal sounds (events), to suit different needs. In addition to identifying pauses, it calculates detailed statistics, like the average duration of pauses, their total count, and more. These results are saved as summary files (CSV) and separate files for each audio recording, showing the exact timing of detected pauses and vocal events.

The pipeline can also divide pauses into "long" and "short" categories based on a threshold you can customize, with separate statistics provided for each. It’s capable of incorporating clinically relevant data, such as % Syllable Stuttered (%SS), for a deeper understanding of the speech patterns.  

In this context, ATAS metrics are used to analyze speech data from adults who stutter (AWS) and adults who do not stutter (AWNS). Machine learning models, including Random Forest and Decision Trees, utilize these metrics to classify participants as AWS or AWNS based on their speech data, such as reading a passage. Additionally, combining ATAS metrics with time-series data enables the use of LSTM or Long Short-Term Memory models (a type recurrent neural network model specifically designed to process and analyze sequential data, such as time series) for the same classification task.      


# Citation 
If you find this code useful in your research, please cite the following paper:
Yawatkar, V., Chow, H. M., & Usler, E. R. (2023). Automatic Temporal Analysis of Speech: A Quick and Objective Pipeline for the Assessment of Overt Stuttering. PsyArXiv. https://doi.org/10.31234/osf.io/yu6f5 

# Acknowledgment
Parts of this codebase are adapted from the following sources:
- Functions detect_silence_t and detect_nonsilent_t: Adapted from James Robert's implementation in their repository: pydub [https://github.com/jiaaro/pydub/blob/master/pydub/silence.py]

# Dependencies  
Dependencies (version dependent)  
Python version: 3.7.6  

noisereduce: 3.0.2  
scipy: 1.7.3  
matplotlib: 3.5.3  
librosa: 0.10.1  
numpy: 1.21.6  
pydub: 0.25.1  
pandas: 1.0.1  
sklearn: 1.0.2  
tensorflow: 2.11.0  
IPython: 7.12.0  
glob: 0.7      

Pre-processing steps in audio files in the dataset used for this project:
- The dataset comprised acoustic data from adults who do not stutter (AWNS, 18 participants) and adults who stutter (AWS, 17 participants). AWNS data was obtained from the open source FluencyBank dataset. AWS data was collect at the Interpersonal Neurophysiology Lab at UD. 12 out of 17 participants provided permission to share their data.  
- Pre-processed the audio files by clipping to remove extraneous content before and after the reading task.
- For AWNS participants, who read passages from a computer screen and pressed the spacebar once during the reading, the resulting key press noise varied in duration but never exceeded 2 seconds. To maintain consistency across all files, a 2-second segment was systematically removed from each recording, including AWS files, ensuring uniformity in the pre-processing procedure.
- The sampling rate for all the acoustic files utilized was 48 kHz. This version of ATAS is optimized for operation at the specified sampling rate.  


# Output parameters in ATAS:
Notebooks: ‘Streamlined_ATAS_AWNS’ and ‘Streamlined_ATAS_AWS’ 

# Description of columns in the compiled csv file (without long and short pause details)
Filename: (ATAS/Stat_csv_files/AWNS_All_files_together_50_ms_1_win_50_150_csv.csv)  
Filename: (ATAS/Stat_csv_files/AWS_All_files_together_50_ms_1_win_50_150_csv.csv)  


'File_Name' - name of the file e.g. 'C1_DS.wav'  
'Speech Time Threshold_ms' - minimum speech event selection threshold (temporal)  
'Pause Time Threshold_ms' - minimum pause event selection threshold (temporal)  
'Percent_Pause' - percent of (total duration of all pause events in file/ total duration of file)  
'Percent_Speech' - percent of (total duration of all speech events in file/ total duration of file)  
'Total_Duration_Unclipped_s' - Total original file duration  
'Total_Duration_Clipped_s' - Total final file duration (for analysis)  
'Speech_Duration_s' - Total duration of all speech events in file  
'Pause_Duration_s'- Total duration of all pause events in file  
'Speech_Events' - Speech events total count  
'Pause_Events' - Pause events total counts  
'Mean Speech_s' - Mean duration metric of all the speech event durations  
'Std Dev Speech' - Standard deviation metric of all the speech event durations  
'CV Speech' - Covariate of variation metric of all the speech event durations   
'Mean Pause_s' - Mean duration metric of all the pause event durations  
'Std Dev Pause' - Standard deviation metric of all the pause event durations  
'CV Pause'- Covariate of variation metric of all the pause event durations  


# Output parameters in the individual CSV file  
(Time series data for each acoustic file after ATAS processing)  

Notebooks: ‘Streamlined_ATAS_AWNS’ and ‘Streamlined_ATAS_AWS’  

# Description of columns in individual participant time series data csv file  
e.g. '24fa_f.csv'  

'level_0' - This column holds previous event positions that were part of a 
          multi-level index from an earlier stage in the function.  

'index' - This column represents the original row position of each event in the DataFrame, 
          which can be useful for backtracking or verifying the original sequence of detected events  

'Time_start' - Start time of the detected event (in seconds, with respect to the time of the file)  
'Time_end' - End time of the detected event (in seconds, with respect to the time of the file)  
'Labels' - Type of event  
'Lables_X' - Type of preceeding event  
'Time_diff' - Duration of the detected event (in seconds)  


# Long Short Pause analysis and incorporation of pre-calculated SSI-4 score metric - Stuttering Severity %SS     

Notebook: ‘Compute_long_and_short_pause_stats’    

# Description of columns in the compiled csv file (with long and short pause details)  
Filename: (ATAS/Stat_csv_files/AWNS_AWS_all_details.csv)  

 
'File_Name' - name of the file e.g. 'C1_DS.wav'  
'Group' - Category e.g. AWS and AWNS, CWS and CWNS  
'Age' - Age - unit as you input  
'Sex' - as you input e.g. F or M  
'Total_words_expected' - total number of words in the passage to be read  
'Words_missing_at_end' - incase if any less words were read  
'Final_word_count' - total number of words read present in the acoustic file  
'Speech Time Threshold_ms' - minimum speech event selection threshold (temporal)  
'Pause Time Threshold_ms' - minimum pause event selection threshold (temporal)  
'Percent_Pause' - percent of (total duration of all pause events in file/ total duration of file)  
'Percent_Speech' - percent of (total duration of all speech events in file/ total duration of file)  
'Total_Duration_Unclipped_s' - Total original file duration  
'Total_Duration_Clipped_s' - Total final file duration (for analysis) - based on the start and stop time input from the csv file  
'Speech_Duration_s' - total duration of all speech events in file  
'Pause_Duration_s' - total duration of all pause events in file  
'Speech_Events'- speech events total count  
'Pause_Events' - pause events total counts  
'Mean Speech_s' - mean duration metric of all the speech event durations  
'Std Dev Speech' - standard deviation metric of all the speech event durations  
'CV Speech' - covariate of variation metric of all the speech event durations   
'Mean Pause_s' - mean duration metric of all the pause event durations  
'Std Dev Pause' - standard deviation metric of all the pause event durations  
'CV Pause' - covariate of variation metric of all the pause event durations   
'All_events_durations' - all the individual event durations  
'long_p_durations' - all the individual event (long pause) durations  
'short_p_durations'- all the individual event (short pause) durations  
'long_p_count' - long pause events total counts  
'short_p_count' - short pause events total counts  
'long_p_durations_mean' - mean duration metric of all the long pause event durations  
'short_p_durations_mean' - mean duration metric of all the short pause event durations  
'long_p_durations_cv' - covariate of variation metric of all the long pause event durations  
'short_p_durations_cv'- covariate of variation metric of all the short pause event durations  
'Speech_Rate'- speech rate (total words read/ total file time)  
'ID' - redundant - file name present for the files for which %SS scores and other clinical assessment related scores are available
'No_of_stuttered_syllables' - no of stuttered syllables in the speech file
'No_of_total_syllables' - no of total syllables in the speech file
'Percent_syllables_stuttered' - (No_of_stuttered_syllables/No_of_total_syllables)
'Score' - SSI-4 score
