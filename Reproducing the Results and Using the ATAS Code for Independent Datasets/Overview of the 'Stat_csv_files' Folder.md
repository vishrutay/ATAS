# Overview of the 'Stat_csv_files' Folder  
  
## Description  
This folder contains various files for analyzing AWS (17 participants) and AWNS (18 participants) data, as outlined in the citation document. It includes function files required across multiple Jupyter notebooks, participant details, input files, and output files generated from different analyses.  
  
---  
  
## Function Files  
These files are used across multiple `.ipynb` notebooks:  
- **ATAS_functions.ipynb**  
- **Long_short_pause_compute_functions.ipynb**  
  
---  
  
## Participant Details Files  
These CSV files provide details about participants:  
- **AWNS_details.csv**  
- **AWS_details.csv**  
  
### Columns:  
- **ID**: Participant ID (also used in acoustic file names, e.g., `24fa.wav` for `ID` 24fa)  
- **Group**: AWNS or AWS  
- **Age**: Age of the participant in years  
- **Sex**: F or M  
- **Total_words_expected**: Expected word count in the passage  
- **Words_missing_at_end**: Missing words at the end in the acoustic file (if any)  
- **Final_word_count**: Total words in the acoustic file  
  
---  
  
## Input Files  
Used in specific Jupyter notebooks:  
  
| File Name                     | Used In Notebook                          | Description |  
|--------------------------------|---------------------------------|-------------|  
| **AWNS_input.csv**             | Streamlined_ATAS_AWNS.ipynb    | Contains start and optional end time inputs for trimming the original file |  
| **AWS_input.csv**              | Streamlined_ATAS_AWS.ipynb     | Contains start and optional end time inputs for trimming the original file |  
| **AWS_SSI_details.csv**        | Compute_long_and_short_pause_stats.ipynb | Contains %SS scores and other stuttering-related metrics |  
| **pval.csv**                   | Figure_5_6_7_8.ipynb          | Contains group analysis details for GLMs and Neg Binomial models |  
  
### Relevant Columns for Analysis:  
- **AWS_SSI_details.csv**: `Percent_syllables_stuttered`  
- **pval.csv**: `p-value`  
  
---  
  
## Output Files  
Generated from different Jupyter notebooks:  
  
| File Name                                      | Generated From Notebook                 | Description |  
|------------------------------------------------|---------------------------------|-------------|  
| **AWNS_All_files_together_50_ms_1_win_50_150_csv.csv** | Streamlined_ATAS_AWNS.ipynb    | Detailed in ATAS/README.md |  
| **AWS_All_files_together_50_ms_1_win_50_150_csv.csv** | Streamlined_ATAS_AWS.ipynb     | Detailed in ATAS/README.md |  
| **AWNS_AWS_all_details.csv**                  | Compute_long_and_short_pause_stats.ipynb | Detailed in ATAS/README.md |  
  
---  
  
## Summary Table of All Files in 'Stat_csv_files'  
  
| File Name                                    | Type         | Purpose |  
|----------------------------------------------|-------------|---------|  
| **ATAS_functions.ipynb**                     | Function File | Used across multiple `.ipynb` files |  
| **Long_short_pause_compute_functions.ipynb** | Function File | Used across multiple `.ipynb` files |  
| **AWNS_details.csv**                         | Data File | Contains participant details for AWNS group |  
| **AWS_details.csv**                          | Data File | Contains participant details for AWS group |  
| **AWNS_input.csv**                           | Input File | Start/end time inputs for Streamlined_ATAS_AWNS.ipynb |  
| **AWS_input.csv**                            | Input File | Start/end time inputs for Streamlined_ATAS_AWS.ipynb |  
| **AWS_SSI_details.csv**                      | Input File | Stuttering-related metrics for Compute_long_and_short_pause_stats.ipynb |  
| **pval.csv**                                 | Input File | Group analysis for Figure_5_6_7_8.ipynb |  
| **AWNS_All_files_together_50_ms_1_win_50_150_csv.csv** | Output File | Output from Streamlined_ATAS_AWNS.ipynb |  
| **AWS_All_files_together_50_ms_1_win_50_150_csv.csv** | Output File | Output from Streamlined_ATAS_AWS.ipynb |  
| **AWNS_AWS_all_details.csv**                 | Output File | Output from Compute_long_and_short_pause_stats.ipynb |  
  
---  

