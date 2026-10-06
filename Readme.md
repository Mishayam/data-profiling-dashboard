# TheFlow
[ 1. Import Data ] ──> [ 2. Generate HTML Profile ] ──> [ 3. Clean & Impute ] ──> [ 4. Export Dashboard Image ]

# Data Profiling & Universal Dashboard Generator (Google Colab)

An automated notebook for data cleaning, profiling, and visualization. Built to ingest datasets, detect missing values, sanitize text columns, and render a 2x2 exploratory dashboard—all in a single execution flow.

---

# Features

- **Automated Data Profiling**: Generates rich interactive HTML data health summaries using `fg-data-profiling`.
- **Intelligent Cleaning**: 
	- Drops duplicate rows.
  	- Standardizes column headers to lowercase `snake_case`.
  	- Removes empty/sparse columns exceeding a configurable threshold (default: >60% missing).
  	- Imputes missing numeric values using column medians and categoricals with `'unknown'`.
- **Dynamic 2x2 Visualization Dashboard**:
- **Distribution**: Histograms with Kernel Density Estimation (KDE) for continuous variables.
- **Time Series / Categoricals**: Automatic datetime detection for daily trend tracking or frequency counts.
- **Relationships**: Scatter plots / Box plots across primary variables.
- **Correlation Matrix**: Annotating top numerical feature dependencies via heatmaps.

---

## How to Run in Google Colab

1. **Open the Notebook**: Upload `data_profiling_dashboard.ipynb` to [Google Colab](https://colab.research.google.com/).
2. **Install Dependencies**: Run the first cell to install the required profiling package:
   ```python
   !pip install fg-data-profiling

3. **Upload Your Dataset: Place your dataset (e.g., data.csv) into the Colab session storage.

4. **Run All Cells: Execute the notebook cells sequentially to execute the pipeline:

    Step 1: Load and profile raw data (raw_profile.html).

    Step 2: Clean, deduplicate, and impute missing values (cleaned_data.csv).

    Step 3: Generate and display the 2x2 summary dashboard.

Output Artifacts:

Running the notebook produces three main files in your Colab file viewer:

Output File		Format		Description
raw_profile.html		HTML		(Interactive exploratory report detailing dataset health and statistics.)

cleaned_data.csv		CSV		(Cleaned dataset ready for downstream model building or analysis.)
	
universal_dashboard.png	PNG 		(Image2x2 visualization grid showing distributions, trends, and correlation heatmaps.)

Requirements:

    Google Colab (Python 3.10 runtime)
    Packages used: pandas, numpy, matplotlib, seaborn, fg-data-profiling

