# Text Analysis for Economic Literatures

This project conducts a descriptive text analysis of 74,292 abstracts from papers published in the top 30 economic journals between 1990 and 2023, from EconLit Database. Three models are deployed in this project during the process. One byproduct of this project is a sentence-level economic literature classification dataset of equivalent scale.

## Table of Contents
1. [Setup and Installation](#setup-and-installation)
   - [Prerequisites](#prerequisites)
   - [Installation Guide](#installation-guide)
2. [Usage](#usage)
   - [Executing the Scripts](#executing-the-scripts)
   - [DEMO_MODE](#demo_mode)
   - [Output File Structure](#output-file-structure)
3. [Data Source](#data-source)
4. [Acknowledgments](#acknowledgments)

## Setup and Installation

To get started with this analysis, you'll need to ensure your environment meets the necessary requirements and that all dependencies are installed. This project is developed with Python 3.x, and uses several additional libraries detailed in the `requirements.txt` file.

### Prerequisites

- Python 3.6 or higher is required.
- It's recommended to use a virtual environment for Python projects to manage dependencies.

### Installation Guide

1. **Clone the Repository**

   First, clone the project repository to your local machine using Git:

   ```bash
   git clone https://github.com/Henry-Louis/TextAnalysisEconomicLiterature.git
   cd your-project-repo
   ```

2. **Set Up a Virtual Environment** (Optional)

   Create a virtual environment to isolate the project dependencies:

   - For Windows:
     ```bash
     python -m venv venv
     .\venv\Scripts\activate
     ```

   - For macOS/Linux:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. **Install Required Packages**

   With your virtual environment activated, install the required Python packages specified in `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

This will install all the necessary packages to run the analysis scripts successfully. After completing these steps, your environment will be set up, and you'll be ready to run the analysis.

Please ensure that your working directory is the root of the project repository when running the installation commands and subsequent analysis scripts. If you encounter any issues during the installation process, double-check that your Python and pip versions are up to date and compatible with the project requirements.


## Usage

This section of the README guides you through the process of executing the scripts included in this project, enabling both a comprehensive run and a demonstration mode intended for users who wish to quickly view the generated plots without going through the entire data preparation process.

### Executing the Scripts

To run the analysis scripts, navigate to the root directory of the project in your terminal or command prompt and execute the scripts in the following order:

```bash
python src/prep_1_download_data_EconLit.py
python src/prep_2_prepare_data_EconLit.py
python src/prep_3_add_nationality.py
python src/prep_4_classify_sentence.py
python src/prep_5_add_writing_features.py
python src/analyze_1_generate_wordcloud.py
python src/analyze_2_generate_trend_plots.py
```

Each script is responsible for a specific part of the analysis pipeline, from data downloading and preparation to the final analysis and visualization steps.

### DEMO_MODE

For users primarily interested in viewing the generated plots without processing the entire dataset, the project supports a `DEMO_MODE`. When activated, `DEMO_MODE` skips the data preparation steps and utilizes an already processed version of the data. This mode significantly reduces the setup time and allows users to directly engage with the analysis results.

To activate `DEMO_MODE`, ensure that the `DEMO_MODE` variable in the `config.py` file is set to `True` (default):

```python
DEMO_MODE = True
```

If `DEMO_MODE` is disabled (set to `False`), the scripts will proceed with the complete data preparation process, which may take several hours.

### Output File Structure

Upon successful execution of the scripts, an `output` directory will be created in the project's root. This directory includes a `plot` folder, which stores all generated visualizations, such as word clouds and trend plots. The structure is as follows:

```
project_root/
│
└───output/
    │
    └───plot/
        │   wordcloud_plot
        │   trend_plot
        │   ...
```

## Data Source

The dataset utilized in this study encompasses abstracts from papers published in the top 30 economic journals, as ranked by the IDEAS organization. The comprehensive list of these leading journals can be accessed at [IDEAS Top Journals](https://ideas.repec.org/top/top.journals.all.html). 

The metadata for these publications was meticulously extracted from the EconLit Database. This extensive database is available through the Ludwig Maximilian University of Munich (LMU), a member institute, providing a rich source of academic literature in the field of economics. For further details on accessing the database, visit [EconLit Database Access](https://web-p-ebscohost-com.emedien.ub.uni-muenchen.de/ehost).

## Acknowledgments

This project was made possible through the efforts of:

- **Henry Liu**: I tackled the project's technical requirements, by a detailed analytical framework and a formatted execution of related computational tasks.

- **Mathias Bühler**: My supervisor, whose invaluable insights, guidance, and support were instrumental in shaping the direction and execution of this project. 

We extend our heartfelt gratitude to the IDEAS organization, EconLit Database and the Ludwig Maximilian University of Munich for providing access to the data.
 
