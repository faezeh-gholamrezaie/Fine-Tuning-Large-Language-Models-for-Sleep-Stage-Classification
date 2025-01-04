# Fine Tuning LLM for Sleep Stage Classification
Sleep consists of distinct stages: Wake (Stage 0), Light Sleep (NREM1 - Stage 1), Deep Sleep (NREM2 and NREM3 - Stages 2 and 3), and REM (Stage 4). Each stage is essential for learning, memory, and overall health. Using EEG signals recorded in 30-second intervals, the goal is to classify these stages accurately based on brain activity patterns.

<img src="https://github.com/faezeh-gholamrezaie/Fine-Tuning-Large-Language-Models-for-Sleep-Stage-Classification/blob/main/Picture/Picture.png" width="300" />

![]([))

## Accessing the Dataset

There are two ways to access the dataset for this project:

### 1. **Manual Download**
- Use the following link to download the dataset manually:  
  [**Download Dataset**](https://drive.google.com/file/d/1Y2cTYR_t_10NAbznspE5bBjuATPdTgtq)
- After downloading, place the file in the `data` directory of the project.

### 2. **Using Python (gdown)**
- If you're working in Google Colab or a Python environment, use the following code to download the dataset directly:

```python
!pip install gdown

import gdown
file_id = '1Y2cTYR_t_10NAbznspE5bBjuATPdTgtq'
gdown.download(f'https://drive.google.com/uc?export=download&id={file_id}', 'file.zip', quiet=False)
```
## EEG Feature Extraction

To optimize the input for the model, we extracted key features from the EEG data. These features capture both time-domain and frequency-domain characteristics, enabling effective classification of sleep stages. 

The extracted features include:
- **Time Features**: Statistical metrics representing temporal dynamics.
- **Hjorth Parameters**: Indicators of activity, mobility, and complexity.
- **Wavelet Entropies**: Measures of signal randomness across wavelet scales.
- **Kurtosis and Skewness**: Describing the distribution of signal amplitudes.
- **Frequency Features**: Power spectral density across frequency bands.

These features were selected for their relevance to analyzing single-channel EEG data and enhancing model performance.

## Saving the Dataset in Dictionary Format

To streamline data processing and access, the dataset can be converted and saved in a dictionary format. This structure allows efficient storage and retrieval of EEG data and associated labels for classification tasks.

Below is an example code snippet for saving the dataset in dictionary format:

```python
import pickle

# Example: Organizing data into a dictionary
dataset_dict = {
    'EEG_signals': eeg_data,  # Replace 'eeg_data' with your EEG data array
    'labels': sleep_stages    # Replace 'sleep_stages' with corresponding labels
}
```
## fine-tuning process 
