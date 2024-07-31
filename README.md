# Country Development Analysis
## Project Overview
This project aims to group countries using socio-economic and health factors to determine the development status of each country. 
The analysis uses a dataset originally sourced from Help.NGO, an international non-governmental organization specializing in emergency response, preparedness, and risk mitigation.

## Data Source
The data used in this task was originally sourced from Help.NGO. 
This international non-governmental organization specializes in emergency response, preparedness, and risk mitigation.

## Dataset Attributes
The dataset includes the following attributes:
- **country**: Name of the country
- **child_mort**: Death of children under 5 years of age per 1000 live births
- **exports**: Exports of goods and services per capita, given as a percentage of the GDP per capita
- **health**: Total health spending per capita, given as a percentage of GDP per capita
- **imports**: Imports of goods and services per capita, given as a percentage of the GDP per capita
- **income**: Net income per person
- **inflation**: Measurement of the annual growth rate of the Total GDP
- **life_expec**: Average number of years a newborn child would live if the current mortality patterns remain the same
- **total_fer**: Number of children that would be born to each woman if the current age-fertility rates remain the same
- **gdpp**: GDP per capita, calculated as the Total GDP divided by the total population

## Project Objectives
The primary objective of this project is to analyze and group countries based on various socio-economic and health factors to understand their development status better.
This can provide insights into:
- The correlation between different socio-economic and health factors
- The impact of these factors on the overall development of a country
- Identifying patterns and clusters of countries with similar development profiles

## Approach
- Loading the Dataset: The dataset was loaded into a pandas DataFrame for analysis.

- Brief Look at the Data: The dataset's info and a statistical description of each feature were examined.

- Handling Missing Data: Missing data in each column was identified and cleaned to ensure the dataset's integrity.

- Dropping Non-Numeric Features: The country column was dropped as the algorithm does not work with non-numeric features since it may not be possible to calculate the distance or similarity between two categorical values.

- Feature Correlation Analysis: Correlation between the features was explored using the Seaborn pairplot and Seaborn heatmap to understand the relationships between different variables, particularly discovering the features most correlated to gdpp.

- Outlier Removal: Outliers from the chosen independent variables were removed to improve model performance.

- Data Transformation and Scaling: The underlying distribution of each column was examined to decide on the appropriate transformations and scaling methods.

- Model Training and Labelling: The data was fitted to the k-means model multiple times, each time changing the number of clusters and evaluating the inertia of the model.

- Scoring the Model: The performance of the K-means model was evaluated by distinguishing the clusters with different numbers of clusters using the Silhouette Score method.

- Labelling the Data: The model with the highest Silhouette score was used to label the data.

- Analysing the Labelled Data: The clusters were visualized by plotting Child Mortality vs GDPP and Inflation vs GDPP, showing each cluster with a different color.

- Naming Each Cluster: Each cluster was labeled as "Developed", "Less Developed", or "Fully Developed" based on the findings from the previous analysis step.

## Installation
To run the project locally, follow these steps:

- Clone the repository:
```sh
git clone https://github.com/dorsasam/kmeans-countries-clustering.git
cd kmeans-countries-clustering
```

- Create a virtual environment and activate it:
```sh
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

- Install the required dependencies:
```sh
pip install -r requirements.txt
```

- Run the Jupyter notebooks or scripts as needed.
