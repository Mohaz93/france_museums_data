
# Museum Data Analysis Project


## Overview

This project aims to analyze museum data in France using Python and JupyterLab. The dataset used for this analysis is sourced from [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/liste-et-localisation-des-musees-de-france/), which provides a comprehensive list and location of museums in France.

The project involves the following steps:

1. Loading the museum dataset from a CSV file.
2. Exploring the data by checking the available columns and their information.
3. Performing descriptive statistics on the dataset.
4. Visualizing the data using graphs and maps.

The goal of this project is to gain insights into the distribution of museums across different regions in France and provide interactive visualizations for better understanding.

## Source of Data

The museum dataset used in this project is obtained from [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/liste-et-localisation-des-musees-de-france/), which is an open platform for sharing public data in France. The platform is developed by Etalab, a mission placed under the authority of the French Prime Minister.

[data.gouv.fr](https://www.data.gouv.fr/fr/datasets/liste-et-localisation-des-musees-de-france/) offers a wide range of datasets, including governmental, statistical, and geographic data, with the aim of promoting transparency and facilitating the use of public information.

By leveraging the museum dataset provided by data.gouv.fr, we can analyze and visualize the distribution and characteristics of museums in France, enabling us to gain valuable insights into the cultural landscape of the country.

## Requirements

To run this project, you will need:

- Python (version 3.7 or higher)
- JupyterLab

### Installing Python

You can download and install Python from the official website: [Python.org](https://www.python.org/downloads/)

Follow the instructions specific to your operating system to install Python.

### Installing JupyterLab

[JupyterLab](https://jupyter.org/) is a web-based interactive development environment for Jupyter notebooks, code, and data. To install JupyterLab, you can use the Python package manager, pip.

Open your command prompt or terminal and run the following command:

```shell
pip install jupyterlab
```

Once the installation is complete, you can launch JupyterLab by running the following command:

```shell
jupyter lab
```

JupyterLab will open in your default web browser, and you can create a new notebook to start working on the museum data analysis project.


## License

This project is licensed under the [MIT License](LICENSE).

## Code Explanation

The following code snippet demonstrates how to load the museum dataset from a CSV file, perform basic data exploration, and visualize the data using pandas, matplotlib, and folium libraries in Python:



```python
import pandas as pd
import matplotlib.pyplot as plt
import folium
```

- `pandas` is a powerful library for data manipulation and analysis. It provides data structures and functions to efficiently handle and analyze structured data, such as CSV files. We use it here to load the museum dataset from a CSV file, perform data exploration, and access various data manipulation capabilities.

- `matplotlib.pyplot` is a plotting library in Python. It provides a convenient way to create various types of plots and visualizations. We use it to create an histogram showing the number of museums by region.

- `folium` is a library for creating interactive maps and visualizations. It is built on top of the `leaflet.js` library. We use it to create a map and add markers for each museum, with different marker colors indicating whether a museum has a website or not.

```python
# Path to the CSV file
csv_path = '/home/moaz/Documents/jupyter/france_museum_data/museums.csv'

# Loading the CSV file
data = pd.read_csv(csv_path, delimiter=';')
```

In these lines, we specify the path to the CSV file containing the museum data. The `pd.read_csv()` function from the `pandas` library is then used to read the CSV file and load it into a pandas DataFrame object called `data`.

```python
# Displaying the first few rows of the CSV file
print("First few rows of the CSV file:\n")
print(data.head().to_string(index=False))
```

This code snippet prints the first few rows of the loaded CSV file using the `head()` function of the DataFrame object. It helps us quickly inspect the structure and content of the data.

```python
# Checking the available columns
print("Available columns:\n")
print(data.columns.to_list())
```

Here, we print the names of the available columns in the DataFrame using the `columns` attribute. It gives us an overview of the different data fields present in the dataset.

```python
# Checking information about the data
print("Data information:\n")
print(data.info())
```

The `info()` function of the DataFrame provides a summary of the dataset, including the number of non-null values in each column, the data types, and memory usage. It helps us understand the data's structure and identify any missing values or potential issues.

```python
# Checking descriptive statistics
print("Descriptive statistics:\n")
print(data.describe().to_string())
```

The `describe()` function generates descriptive statistics of the dataset, including measures like count, mean, standard deviation, minimum, maximum, and quartiles for numerical columns. It provides a statistical summary of the dataset's distribution and central tendencies.

```python
# Displaying the histogram of the number of museums by region
print("Histogram of the number of museums by region:\n")
data['region_administrative'].value_counts().plot(kind='bar', figsize=(12, 6))
plt.xlabel('Region')
plt.ylabel('Number of Museums')
plt.title('Number of Museums by Region')
plt.show()
```

In these lines, we create a histogram using `value_counts()` on the 'region_administrative' column to get the count of museums in each region. We then use `plot(kind='bar')` to create a bar plot of the counts. The `xlabel()`, `ylabel()`, and `title()` functions from `matplotlib.pyplot` are used to set the labels and title for the plot. Finally, `plt.show()` displays the histogram.

