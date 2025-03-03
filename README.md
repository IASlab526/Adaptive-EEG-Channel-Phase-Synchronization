# Description
### This repo is for the "Adaptive EEG Channel Phase Synchronization for Individualized Mental Fatigue Detection" journal appendix
* The files contain 10 subjects.

## Contents

###  Non-fatigue brain connectivity map
- **Brain connectivity map during the **non-fatigue state** (0–20 minutes) for 10 subjects.
- **Brain connectivity map during the **fatigue state** (41–60 minutes) for 10 subjects.
  
###  Fatigue Assessment Scale (FAS) questionnaire results
- **Before and after** fatigue questionnaire scores.

###  Frequency Band Power Characteristics
- **: Frequency band power distribution in the **non-fatigue state**  for 10 subjects.
- **: Frequency band power distribution in the **fatigue state**  for 10 subjects.

###  Weighted Phase Lag Index (wPLI) Analysis
- **Top **10** wPLI functional connectivity topology maps for 10 subjects.
- **Top **5** wPLI functional connectivity analysis of brain region category for 10 subjects.

##  Supplementary Data

###  `Supplementary_1.pdf` - EEG Spectral Component Ratio Analysis
- Data from **10 subjects**, divided into **0–20 min (non-fatigue) and 41–60 min (fatigue)**.
- **Power Spectral Density (PSD)** analysis and feature extraction.

###  `Supplementary_2.pdf` - Fatigue Assessment Scale (FAS) Analysis and wPLI-bаsed connectivity analysis

- **FAS is a subjective fatigue assessment** using **a 10-item questionnaire** (score range: 10–50).
- ** wPLI-bаsed connectivity analysis focuses on the top five individual wPLI connections


## Experimental Data Overview
#### Mental Fatigue Experimental EEG data resource [Fatigue Experimental EEG data](https://drive.google.com/drive/folders/1Wf6dAur-h3ABM7QFeatFyG7fkgIk2MF0?usp=sharing)。

This dataset contains electroencephalogram (EEG) signals, categorized into fatigued and non-fatigued states for different subjects. Data was collected from 10 subjects, with each subject having multiple files:

- `raw_EEG/`: Contains original EEG recordings.
- `PSD_data/`: Contains power spectral density (PSD) data.
- `process_EEG/`: Contains preprocessed and normalized EEG data for training.

Here, `x` represents the subject number (e.g., `S1_fatigue.xlsx` refers to Subject 1's fatigued state recording).

## Data Structure
### Raw EEG Data
The data is stored in the `raw_EEG/` directory with the following structure:
```
raw_EEG/
│-- S1/
│   │-- fatigue.xlsx
│   │-- nonfatigue.xlsx
│-- S2/
│   │-- fatigue.xlsx
│   │-- nonfatigue.xlsx
│-- ...
│-- S10/
│   │-- fatigue.xlsx
│   │-- nonfatigue.xlsx
```
Each `.xlsx` file contains data with dimensions **900000 x 32**, calculated as follows:

- Sampling rate: 500 Hz
- Recording duration: 30 minutes (30 min * 60 sec = 1800 sec)
- Total data points: 500 Hz * 1800 sec = 900000
- Number of channels: 32

### PSD Data
The power spectral density (PSD) data is stored in the `PSD_data/` directory with the following structure:
```
PSD_data/
│-- S1.xlsx
│-- S2.xlsx
│-- ...
│-- S10.xlsx
```
Each `.xlsx` file contains two categories of PSD data:
- **Fatigue**
- **Non-fatigue**

Each file has dimensions **30 x 32**, calculated as follows:

- One PSD calculation per minute
- Total duration: 30 minutes
- Number of channels: 32

### Processed EEG Data
The preprocessed and normalized EEG data is stored in the `process_EEG/` directory with the following structure:
```
process_EEG/
│-- S1.xlsx
│-- S2.xlsx
│-- ...
│-- S10.xlsx
```
Each `.xlsx` file contains **two sheets**:
- `fatigue`: Processed EEG data in a fatigued state
- `nonfatigue`: Processed EEG data in a non-fatigued state

Each sheet has dimensions **600000 x 32**, calculated as follows:

- Data is trimmed to **60 minutes**, removing the first and last 10 minutes.
- Remaining **20 minutes per state**.
- Sampling rate: 500 Hz
- Total data points: 500 Hz * 1200 sec = 600000
- Number of channels: 32

## Data Format
- Each `.xlsx` file in `raw_EEG/` consists of **900000 rows (time series) and 32 columns (EEG channels)**.
- Each `.xlsx` file in `PSD_data/` consists of **30 rows (one per minute) and 32 columns (EEG channels)**.
- Each `.xlsx` file in `process_EEG/` contains **two sheets (fatigue and nonfatigue), each with 600000 rows and 32 columns**.
 
## Copyright and Usage
This dataset is for research and academic purposes only. Commercial use is prohibited. For inquiries or if you need access to the files, please contact the author.

---

