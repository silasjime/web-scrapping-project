# web-scrapping-project
A web scrapping project on the largest companies in the united state by revenue


#### Below are the steps i took and carried out in doing this projects
#### Import Libraries:

- Imported BeautifulSoup from bs4 for HTML parsing.
- Imported requests to handle HTTP requests.
- Define the URL:

- i Set the target URL as https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue, which links to a Wikipedia page listing the largest companies in the U.S. by revenue.

- Send HTTP Request:

- Used requests.get(url) to send a GET request to the URL and stored the response in the page variable.
- Parse HTML Content:

- i Initialized a BeautifulSoup object, soup, with the page content (page.text) using an HTML parser to navigate and extract data from the HTML structure.

- i Inspected the HTML Structure:

- I Printed the entire parsed HTML (soup) to examine the structure and locate the table containing the data.
- Find the Target Table:

- I Used soup.find('table', class_='wikitable sortable') to locate the table element with the class wikitable sortable, which contains the list of companies and their revenue.

- Extract Table Element:

- I Called soup.find_all('table')[1] to select the second table (assuming the relevant data is in this table), and assigned it to the table variable.

- I Printed table to verify the content.
- Extract Column Headers:

- Located all header elements (<th>) within the table using table.find_all('th') and stored the result in world_titles.
- Process Header Titles:

- Created a list comprehension to extract and clean the text from each header element, storing the column names in - - ----- 
 world_table_titles.
Printed world_table_titles to verify the extracted headers.
- Prepared  DataFrame:

- I Imported pandas as pd and initialized an empty DataFrame df with world_table_titles as column names.
- Extracted Rows of Data:

- I Located each table row (<tr>) within the table using table.find_all('tr') and stored it in column_data.
- Process Row Data and Populate DataFrame:

- Used a loop to iterate over each row (excluding the header row) in column_data.
- For each row, used row.find_all('td') to find all data cells and cleaned their text.
- Added each processed row to the DataFrame, df, by appending to the next available index.
- Output DataFrame:

- Displayed the populated DataFrame (df) to review the extracted data.
- Save Data to CSV:

- Saved the DataFrame as a CSV file at the specified path, "C:\\Users\\Admin pc\\Downloads\\Data Science\\companies.csv", without the index column.

