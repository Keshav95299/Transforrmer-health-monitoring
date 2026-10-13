# Transformer Health Monitoring Tool

A Python notebook for exploring transformer loading, oil temperature, and maintenance history. It summarizes operating data, assigns risk categories, and displays charts to support review.

## Features

- Inspect input data and missing values.
- Identify transformers with loading above 100% or oil temperature above 80°C.
- Calculate loading and oil temperature summary statistics.
- Join transformer data with maintenance history using `Transformer_ID`.
- Classify transformers as Normal, Warning, Critical, or Unknown.
- Display the 20 most heavily loaded transformers and risk category counts.

## Data Source
  This project uses synthetic transformer loading and maintenance datasets created for learning and demonstration purposes. They do not represent actual utility or company records.

The analysis workflow, missing-data checks, risk-classification logic, and visualizations are designed to demonstrate realistic power-system asset monitoring tasks.
  

## Project files

```text
transformer-health-monitoring/
├── transformer_health_monitoring.ipynb
├── data/
│   ├── transformer_loading_final.xlsx
│   └── maintenance_history_final.xlsx

├── README.md
├── requirements.txt
└── 
```

The notebook includes saved tables and charts. Separate plot files are not required.

## Run the notebook

1. Install Python, then download or clone this repository.
2. Open a terminal in the project folder and install the required libraries:

   ```sh
   python -m pip install -r requirements.txt
   ```

3. Start Jupyter from that same folder:

   ```sh
   python -m jupyter notebook
   ```

4. Open `transformer_health_monitoring.ipynb`, run all cells, and save the notebook.

The two input files are Excel workbooks. Their filenames have been given the `.xlsx` extension, and the notebook reads them from `data/`.

## Risk classification

| Category | Rule |
| --- | --- |
| Normal | Loading ≤ 100% and oil temperature ≤ 80°C |
| Warning | Exactly one of these two limits is exceeded |
| Critical | Both limits are exceeded |
| Unknown | Loading or oil temperature is missing |

These thresholds are the rules used by this project, rather than a validated operational assessment of transformer health.

## Libraries

Pandas handles tables and analysis, Matplotlib creates charts, OpenPyXL reads Excel files, and Jupyter runs the notebook.
