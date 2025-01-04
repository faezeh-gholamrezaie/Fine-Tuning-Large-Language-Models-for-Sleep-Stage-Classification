# Fine Tuning LLM for Sleep Stage Classification
Sleep consists of distinct stages: Wake (Stage 0), Light Sleep (NREM1 - Stage 1), Deep Sleep (NREM2 and NREM3 - Stages 2 and 3), and REM (Stage 4). Each stage is essential for learning, memory, and overall health. Using EEG signals recorded in 30-second intervals, the goal is to classify these stages accurately based on brain activity patterns.

### Accessing the Dataset

There are two ways to access the dataset for this project:

#### 1. **Manual Download**
- Use the following link to download the dataset manually:  
  [**Download Dataset**](https://drive.google.com/file/d/1Y2cTYR_t_10NAbznspE5bBjuATPdTgtq)
- After downloading, place the file in the `data` directory of the project.

#### 2. **Using Python (gdown)**
- If you're working in Google Colab or a Python environment, use the following code to download the dataset directly:

```python
!pip install gdown

import gdown
file_id = '1Y2cTYR_t_10NAbznspE5bBjuATPdTgtq'
gdown.download(f'https://drive.google.com/uc?export=download&id={file_id}', 'file.zip', quiet=False)
