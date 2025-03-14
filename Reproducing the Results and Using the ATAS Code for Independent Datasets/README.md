# Reproducing the Results and Using the ATAS Code for Independent Datasets  

This document provides a comprehensive guide to using the **Automatic Temporal Analysis of Speech (ATAS) pipeline**, either for **reproducing the results of this study** or for **adapting the code to independent datasets**.
  
---
  
## 1. Reproducing the Results in This Study   
  
### 1.1 Prerequisites   
- **Required Dependencies**:  
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
  
### 1.2 Data Availability and Preprocessing   
- The compelete derived dataset is available to replicate the analysis.  
- If access to the raw data is available, preprocessing steps (such as clipping and removing extraneous noise) can be followed as described in the dataset documentation (ATAS/README.md).  
- Otherwise, users can proceed directly with the derived data files.  
  
### 1.3 Steps for Running the Analysis  
  
1. **Prepare the Input Files**:  
   - AWS Data: `AWS_input.csv`  
   - AWNS Data: `AWNS_input.csv`  
2. **Run the Speech Analysis Pipeline**:  
   - Execute `Streamlined_ATAS_AWNS.ipynb` for AWNS participants.  
   - Execute `Streamlined_ATAS_AWS.ipynb` for AWS participants.  
   - Outputs:  
     - `ATAS/Stat_csv_files/AWNS_All_files_together_50_ms_1_win_50_150_csv.csv`  
     - `ATAS/Stat_csv_files/AWS_All_files_together_50_ms_1_win_50_150_csv.csv`  
     - Time-series data for individual participants (Details about every event). E.g. '24fa_f.csv' (Location here: ATAS/ATAS_Multiple_Files_Analysis/Individual_OutputCSV_Files/)  
3. **Compute Long and Short Pause Metrics**:  
   - Run `Compute_long_and_short_pause_stats.ipynb`.  
   - Outputs: `ATAS/Stat_csv_files/AWNS_AWS_all_details.csv`  
4. **Perform Statistical Analysis and Generate Figures**:  
   - Run the scripts in `Figures_and_Tables/` to generate results and visualizations.  
   - Run `Group_statistics.ipynb` for model assumption checks as well as generating models (in this case specific GLMs and Negative Binomial models).  
   - Run `Figure_9_DT.ipynb`, `Figure_9_RF.ipynb`, and `Figure_10_LSTM.ipynb` for ML analysis. This includes decision tree, random forest and long short-term memomry (LSTM) models.  
  
### 1.4 Expected Outputs  
- Compiled statistical CSV files.  
- Figures and tables for publication.  
- ML model results (Decision Trees, Random Forest, LSTM).  
  
---  
  
## 2. Using the Code for an Independent Dataset    
  
### 2.1 Data Preparation  
- Ensure that input audio files have a **sampling rate of 48 kHz**.  
- Format the dataset with metadata similar to `AWS_input.csv` and `AWNS_input.csv`.  
- If preprocessing is needed:  
  - Trim extraneous content.  
  - Save files in WAV format.  
  
### 2.2 Running the Analysis on a New Dataset   
1. **Format Input Files**:  
   - Create CSV files with `Start_time` and `End_time` for trimming.  
   - Place them in `ATAS/Stat_csv_files/`.  
2. **Modify Configuration Parameters** (Optional):  
   - Adjust speech and pause thresholds in `Streamlined_ATAS_AWNS.ipynb` and `Streamlined_ATAS_AWS.ipynb`.  
3. **Run the ATAS Pipeline**:  
   - Execute `Streamlined_ATAS_AWNS.ipynb` and `Streamlined_ATAS_AWS.ipynb`.  
4. **Compute Long and Short Pause Metrics**:  
   - Run `Compute_long_and_short_pause_stats.ipynb` with updated input data.  
5. **Analyze the Results**:  
   - Use `Figures_and_Tables/` scripts to generate figures.  
   - Modify machine learning scripts to train models on new data if applicable.  
   - You can run `Figure_9_DT.ipynb`, `Figure_9_RF.ipynb`, and `Figure_10_LSTM.ipynb` for ML analysis. This includes decision tree, random forest and long short-term memomry (LSTM) models.  
  
### 2.3 Expected Outputs for Independent Dataset  
- CSV files with extracted speech and pause metrics (Cumulative event data for each participant file).
- Time-series data for individual participants (Details about every event).  
- Figures visualizing key metrics.  
- Optionally, machine learning classification models.  
  
---  
  
# 3. Code Overview  
  
| File/Folder | Description |  
|------------|-------------|  
| `Dataset_statistics/` | Provides dataset comparison and summary statistics. |  
| `Dataset_statistics/Comparing_groups_balanced_dataset.ipynb` | Checks for dataset balance (Age and Sex distribution) |  
| `ATAS/Stat_csv_files/` | Contains input and output CSV files. |  
| `ATAS_Multiple_Files_Analysis/` | Processes multiple acoustic files in a loop. |  
| `ATAS_Multiple_Files_Analysis/Streamlined_ATAS_AWNS.ipynb` | Processes AWNS audio files, extracting speech and pause metrics. |
| `ATAS_Multiple_Files_Analysis/Streamlined_ATAS_AWS.ipynb` | Processes AWS audio files, extracting speech and pause metrics. |  
| `Long_Pause_Short_Pause_Compute/` | Computes additional metrics related to long and short pauses. |                            
| `Long_Pause_Short_Pause_Compute/Compute_long_and_short_pause_stats.ipynb` | Computes long and short pause metrics. |   
| `Dataset_statistics/Group_statistics.ipynb` | Performs statistical analysis of extracted metrics. |  
| `Figures_and_Tables/` | Scripts for generating figures and tables. |  
---  

