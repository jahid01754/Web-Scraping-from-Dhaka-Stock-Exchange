**Web Scraping**
The web scraping process starts by defining a function called scrap_other_info, which is responsible for extracting specific information from a table on the website. The function takes the following parameters:

r: The row index of the table to extract information from.
company: The name of the company for which information is being extracted.
other_info_table: The BeautifulSoup object representing the table containing the desired information.
The function performs the following steps:

It attempts to find the specified row (r) and extracts the cells from that row.
It extracts the date from the first cell and searches for a specific pattern using regular expressions. If a match is found, it retrieves the date in the specified format.
It extracts the data from the second cell.
It defines patterns using regular expressions to match specific information within the data, such as "Sponsor/Director," "Govt," "Institute," "Foreign," and "Public."
It uses the defined patterns to find matches within the data and extracts the numerical values.
It converts the extracted values to floating-point numbers and constructs a list containing the company, date, and the extracted values.
It returns the constructed list.
The main part of the code then performs the following steps:

It defines the URL of the website to scrape ("https://www.dsebd.org/company_listing.php").
It sends a request to the website and retrieves the page content.
It creates a BeautifulSoup object from the page content for easier parsing.
It searches for the <div> elements with the class "BodyContent" to find all the relevant company information.
It iterates over each company and extracts its code, excluding certain unwanted values.
It creates a Pandas DataFrame to store the company codes.
It renames the column of the DataFrame to "Company Code".
It initializes empty lists to store the company details and other information.
For each company, it performs the following steps:
It sends a request to the specific URL of the company's page.
It creates a BeautifulSoup object from the page content.
It extracts the company name from the <h2> element with the class "BodyHead".
It iterates over the rows of a table to extract various company details.
It finds specific tables using their class names and extracts the sector information.
It appends the company details to the company_details list.
It extracts additional information by calling the scrap_other_info function for specified rows in a table.
It appends the extracted information to the other_info list.
It filters out any None values from the other_info list.
It creates a Pandas DataFrame from the other_info list and assigns appropriate column names.
It exports the company_info_df DataFrame to a CSV file named "company_info.csv".
It creates a Pandas DataFrame from the company_details list and assigns appropriate column names.
It exports the company_details_df DataFrame to a CSV file named "company_details.csv".
**How to Use the Code**
To use this code, you need to have the required libraries (requests,
