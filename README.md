# Grocery Data Scraping and NOVA Classification

## Project Description

This project involves scraping product data from a grocery website, such as product name, manufacturer name, volume, price, compare price, and ingredients. After collecting the data, the project utilizes an OpenAI model to classify products based on their ingredients and level of processing using the NOVA food classification system. The classified data is then saved to both Google Colab and Google Drive for further analysis.

## Table of Contents
1. Installation and Set Up

   1.1 Running in Google Colab

      1.1.1 Execute Notebook Cells

      1.1.2 Google Drive Integration

      1.1.3 Configure Chrome Options

      1.1.4 Set Up OpenAI API

2. Usage

   2.1 Product Data Scraping and Initial CSV Files Creation

   2.2 Retrieving Ingredients Data

   2.3 NOVA Classification Using OpenAI/ChatGPT

   2.4 Combining Data Across Categories

3. NOVA Classification

## 1. Installation and Set Up
### 1.1 Running in Google Colab

1. #### Execute Notebook Cells:
    - Run the notebook cells sequentially in Google Colab to install necessary dependencies and set up the environment. 
    - Execute setup cells for WebDriver, dependency installation, and Google Drive mounting.

2. #### Google Drive Integration:
    - Make sure your Google Drive is mounted at /content/drive/My Drive/scraped_files/ to save scraped data files to Google Drive.

3. #### Configure Chrome Options:
    - Review and adjust Chrome options (chrome_options) in the notebook to suit your specific scraping requirements.

4. #### Set Up OpenAI API:
    1. Obtain an API key from OpenAI.
    2. Store the API key in a .env file named openai_api_key.env in the format OPENAI_API_KEY=*your_api_key*. 
    3. Upload the .env file to the content folder in Google Colab for the notebook to access the API.

## 2. Usage
#### 2.1 Product Data Scraping and Initial CSV Files Creation

1. **Retrieve Category Links:**
   - Retrieve all category links from *Hemköps* shop online site.

2. **Save Product Data:**   
   - Open each category link to perform the initial scraping.
   - Initial scraping retrieves product data such as product name, manufacturer name, volume, compare price, and price.
   - Save data for each category into separate CSV files (`category_data_1.csv`, `category_data_2.csv`, etc.) to prevent data loss due to potential timeouts.

#### 2.2 Retrieving Ingredients Data

1. **Navigate to Product Links:**
   - Reopen each CSV file to access product links.
   - Visit each product page to extract the list of ingredients from the 'Produktfakta' section.

2. **Save Ingredients Data:**
   - Save ingredient data into new CSV files per category (`category_ingredients_1.csv`, `category_ingredients_2.csv`, etc.).

#### 2.3 NOVA Classification Using OpenAI/ChatGPT

1. **Reopen CSV Files:**
   - Reopen all CSV files containing ingredient data.

2. **Utilize OpenAI/ChatGPT for Classification:**
   - Use OpenAI/ChatGPT to classify each product into one of the 4 NOVA groups based on ingredients and processing level.
   - Save classification results (`category_classified_data_1.csv`, `category_classified_data_2.csv`, etc.) along with detailed classification descriptions.

#### 2.4 Combining Data Across Categories

1. **Create Combined DataFrame:**
   - Combine individual CSV files into a single DataFrame (`final_combined_df`).

2. **Save Combined Data:**
   - Save `final_combined_df` as `final_combined_df.csv` for comprehensive analysis across all categories.


## 3. NOVA Classification
The NOVA classification system categorizes foods into four groups based on their level of processing and ingredients. This classification helps in understanding the nutritional quality and processing levels of various food products.

- **Group 1:** Unprocessed or minimally processed foods.
-  **Group 2:** Processed culinary ingredients.
-  **Group 3:** Processed foods.
-  **Group 4:** Ultra-processed foods.