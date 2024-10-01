Clinical Data Analysis Using MIMIC-III Dataset
This project involves the analysis of clinical data from the MIMIC-III dataset, including diagnoses, procedures, and clinical notes. The analysis aims to generate insights about patient diagnoses, procedures, note lengths, and common words used in clinical notes.

Table of Contents
Project Overview
Dataset
Dependencies
Installation
Running the Code
Data Cleaning and Preprocessing
Analysis and Visualizations
Results
File Structure
Contributing
Project Overview
The goal of this project is to explore and analyze the MIMIC-III dataset, specifically focusing on:

Diagnoses and procedures
Distribution of clinical note lengths
Most common words in clinical notes
Temporal trends in diagnoses
Patient data statistics such as unique patient counts
Dataset
MIMIC-III: Medical Information Mart for Intensive Care (MIMIC-III) is a freely accessible critical care database. You can find more information and download the dataset here.

The project uses the following reduced files:

diagnosis_icd_reduced.csv
procedures_icd_reduced.csv
note_events_reduced.csv
Note: These files should be preprocessed and stored in the specified paths before running the code.

Dependencies
This project requires the following R packages:

sparklyr
dplyr
ggplot2
lubridate
wordcloud
tidytext
tidyr
RColorBrewer
tm
reshape2
Installation
Follow the steps below to set up and run the project:

Clone the repository:
git clone <repository-url>
cd <repository-directory>
Install the required R packages: You can install all required packages by running the following command in R:
install.packages(c("sparklyr", "dplyr", "ggplot2", "lubridate", "wordcloud", 
                   "tidytext", "tidyr", "RColorBrewer", "tm", "reshape2"), 
                 repos='http://cran.us.r-project.org')
Install Apache Spark: Run the following commands to install Spark and establish a connection:
spark_install(version = "3.4.0")
sc <- spark_connect(master = "local")
Running the Code
Prepare the Dataset: Ensure you have the three CSV files (mentioned above) stored in the correct paths.

Run the R Script: Open the R script in R Studio and run it step by step. The script reads the datasets, performs data cleaning, and generates insights through various visualizations.

View the Results: The analysis results will be displayed in the R Studio environment as plots and tables.

Data Cleaning and Preprocessing
Removing missing values: Any missing or null values are filtered out from the diagnoses, procedures, and note events datasets.
Removing duplicates: Duplicate entries are removed from the datasets to ensure accurate analysis.
Renaming columns: For easier interpretation, columns are renamed to avoid ambiguity.
Analysis and Visualizations
The analysis involves:

Top Diagnoses and Procedures: Bar plots showing the top 10 most frequent diagnoses and procedures.
Word Cloud: A word cloud showing the most common words in clinical notes after removing stopwords.
Note Length Distribution: A histogram of the distribution of clinical note lengths.
Diagnoses Over Time: A line plot showing diagnoses counts over time.
Common Words in Clinical Notes: A bar plot of the most common words in clinical notes.
Results
Here are the key results of the analysis:

The top 10 most frequent diagnoses and procedures.
A word cloud of the most common terms used in clinical notes.
Statistics on the distribution of note lengths.
Insights into diagnoses trends over time.
File Structure
|-- /data                        # Directory for dataset files
|   |-- diagnosis_icd_reduced.csv
|   |-- procedures_icd_reduced.csv
|   |-- note_events_reduced.csv
|-- analysis.R                   # Main R script for data analysis
|-- diagnosis_counts.csv         # Exported CSV for diagnosis counts
|-- procedure_counts.csv         # Exported CSV for procedure counts
|-- note_length_statistics.csv   # Exported CSV for note length statistics
|-- common_words_in_notes.csv    # Exported CSV for common words in notes
|-- README.md                    # This README file
Contributing
If you wish to contribute to the project:

Fork the repository.
Create a new branch.
Submit a pull request with your changes.
