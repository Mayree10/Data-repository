🔍 Objective
To analyze corn yield variation across a farm field and determine whether these variations are better explained by differences in seeding rate or by field performance in a previous growing season.

📁 Data
Data from four years (2017–2020), including:

Seeding Rate Data (2018, 2020)

Yield Data (2017, 2018, 2019, 2020)

Each dataset contains geospatial coordinates (latitude and longitude) and either:

AppliedRate (for seeding)

Yield (for harvest)

🧮 Methodology
Grid Cell Aggregation:

GPS coordinates were grouped into spatial grid cells.

Mean and count of observations were computed for each cell.

Filtering:

Only cells with ≥30 observations were retained for robustness.

Normalization:

Data were rank-normalized to minimize the impact of outliers.

Data Integration:

Aggregated values across years were merged into a master dataframe keyed by grid cell.

Bayesian Network Modeling:

Several DAG models were created using bnlearn to explore causal relationships between:

Past yield and current seeding

Current seeding and resulting yield

Sequential year-to-year dependencies

📊 Key Libraries
dplyr: Data manipulation

bnlearn: Bayesian network structure and parameter learning

Rgraphviz: DAG visualization

✅ Results
The final DAG network illustrates strong sequential influence of past yields and seeding rates on current-year yields.

The analysis supports the hypothesis that both previous performance and seed rates contribute to current field performance.

📂 Files
/Corn Yield Analysis/Project Code: Clean code version for full reproducibility

Mary.Ogwo.10.pdf: Output PDF showing full modeling steps and visualizations


