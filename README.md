# 11-Module-Mars-DataScraping
Python, BeautifulSoup, Splinter, HTML/CCS, data-scraping, data visualization<br><br>

In this project we perform web-scraping on  Mars news and weather sites and analyze the extracted data to produce visualizations. The data is inspected and identified via HTML id and class attributes and then extracted using Splinter and Beautiful Soup. Pandas and Matplotlib are then leveraged to collect, organize/store, analyze and visualize the data.<br><br>

## PART 1: Scrape Titles and Preview Text from Mars News

Dependancies are loaded and automated browsing is used to visit the Mars news site. From here we leverage ChromeDevTools to explore the HTML code and identify the necessary id and class elements that will be extracted.

A Beautiful Soup object is created and used to extract all elements in the 'list_text' class and stored into a variable.

Next we extract the titles and preview texts of the news articles and store the results in in Python data structures.

To do this, an empty list is first created. Then a for loop is executed to iterate through the previously extracted data and use Beautiful Soup .find function to identify each article title and it's corresponding preview text by thier div/class combination and saved into their respective variable. The title and preview pair is stored in a dictionarry and finally the dictionary data is added to the list.

The list is printed to confirm a successful extraction and finally the browser session is closed.<br><br>


## PART 2: Scrape and Analyze Mars Weather Data
Extract data captured by the Curiosity Rover
Dependancies are loaded and automated browsing is used to visit the Mars weather site. From here we leverage ChromeDevTools to explore the HTML code and identify the necessary elements to will be extracted.

A Beautiful Soup object is created and used to extract all elements in the 'table' class and stored into a variable, then all elements in the 'data-row' class are extracted from the 'table' variable and stored in a new vairable titles 'rows'.

An empty list is created and a for loop is executed to iterate through the rows data, extract the row data and popule the list.

A Pandas DataFrame is created from the list with the column heading specifically named to match the source table from the Mars weather site.

The data is examined and converted to the appropriate data type (where necessary) using the .astype function.<br><br>

Next we analyze the dataset by using Pandas function to answer the following questions.

**1. How many Months Exist on Mars?**
- .value_counts() function used to calculate the count of each moth

**2. How Many Martian days worth of data exist in the scraped dataset?**
- .count() used to calculate the toal days in the dataset.

**3. What are the colest and warmest months on Mars (at the location of the Curiosity)?**
- .mean() used to capture the average minimum temperatere per month (and grouped by month). The data is then visualized using bar plots.

**4. Which Months have the lowest and highest atmospheric pressure on Mars?**
- average pressue calculated using the .mean() function and grouped by month and visualized using a bar plot.

**5. About how many terrestiral days exit in a Martian Year?**
- The data is visualzed using chart that shows the minimum temperater for each (Earth) day in the dataset.

The data is exported to a CSV file and the browser session is closed


<br><br><br>

Sources:
Extracting Table Data for Dataframe - https://stackoverflow.com/questions/50633050/scrape-tables-into-dataframe-with-beautifulsoup