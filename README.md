# ATER Job Opportunity Finder in French Higher Education

## Description

This Jupyter Notebook is designed to help you find "Attaché Temporaire d'Enseignement et de Recherche" (ATER) job opportunities in French higher education institutions. It retrieves data from an official source (or a fallback CSV file), filters it based on your specified keyword and application closing date, and presents the results in a readable format. You also have the option to save the filtered results to an Excel file, grouped by the institution.
## see in colab https://colab.research.google.com/github/URIB4u/ATER_Finder/blob/main/ATER%20positions.ipynb
## How to Use

Follow these steps to effectively use the notebook:

1.  **Ensure Libraries are Installed:** Make sure you have the necessary Python libraries installed. These include `requests`, `pandas`, and `io`. You can install them using pip if you haven't already:
    ```bash
    pip install requests pandas openpyxl
    ```

2.  **Define `ater_url` and `fallback_csv`:** In the first code cell, you will need to define the URL of the official data source (usually an Excel file) and the path to a fallback CSV file (in case the URL is not accessible).

3.  **Run the Data Loading Cell:** Execute the cell containing the `load_and_filter_data` function. This will attempt to download the job data from the specified URL. If it fails, it will try to load from the fallback CSV file. This cell also performs initial data cleaning and filtering to select the columns of interest and drop the initial metadata rows from the URL source.

4.  **Define Search Criteria:** In the cell that contains the filtering logic, you will need to define the following variables:
    * **`keyword`:** Enter the keyword(s) in **French** that represent your area of interest (e.g., 'informatique', 'droit privé', 'biologie marine'). The search is case-insensitive.
    * **`target_date_str`:** Enter the closing date you are interested in, in the format **YYYY-MM-DD** (e.g., '2025-03-20').
    * The code will then convert this string to a datetime object.

5.  **Run the Filtering and Display Cell:** Execute the cell containing the filtering logic. This will:
    * Filter the loaded job data based on the `keyword` found in the 'Profil appel à candidatures' column.
    * Filter the data to include only positions with a 'Date cloture candidature' on or after the `target_date` you specified.
    * Display the matching job opportunities one by one, showing the details for each relevant column.

6.  **Save to Excel (Optional):** After the results are displayed, you will be prompted if you want to save them to an Excel file grouped by institution.
    * If you enter 'yes', you will be asked to provide a filename for the Excel file (e.g., `ater_results.xlsx`).
    * The notebook will then create an Excel file with the specified name, where each sheet contains the job postings for a particular institution.

## Important Considerations for Keywords and Dates

* **Keywords (Mots-clés):** To get the most relevant results, use specific keywords in **French** related to your field of expertise. Consider using synonyms or broader terms if your initial search doesn't yield many results.
* **Dates (Dates):** Ensure that you enter the target closing date in the **YYYY-MM-DD** format. The filtering is set to show positions with a closing date on or after the specified date.

## Disclaimer

This notebook provides information on ATER job opportunities based on the data available from the specified source at the time of retrieval. The accuracy and completeness of this information depend on the source data. The creator of this notebook is not responsible for any inaccuracies or omissions in the data. Job availability and application deadlines may change, so it is always recommended to verify the information on the official websites of the respective institutions. This tool is intended for informational purposes only and should not be considered as professional career advice.
