# NBA-MVP-BOT
![](https://i.imgur.com/QQZ1ZUQ.png)
APP That predicts the MVP for the next basketball game based on previous stats for the season. I use Dwight Howard and the Taoyuan Leopards as an example. Contributions are welcomed with limitations. Check the license for details.
Disclaimer: Obtain permission from owners of the website before scraping data from them!!! 
Licensor: Frame Tech Solutions Ltd., Co. 框架技術解決方案
-> Founder: Nigel Kelly "Huanglong" Phillips
````
Logic:
Over winter break, I created an API BOT that extracts data from https://t-leopards.com/stats/players and predicts which player is most likely to score the most points
1. Fetching the data: I fetch the data from the website using Python. Once the data is fetched, I parse it into a format that can be used for analysis.
2. Cleaning and preprocessing the data: I clean and preprocess the data so that it can be used for analysis. Future patches may involve changes- removing missing or irrelevant data, converting data into a numerical format, and scaling the data.
3. Exploratory Data Analysis (EDA): I perform exploratory data analysis on the data to understand the distribution of the data, identify patterns and correlations, and gain insights into the data.
4. Choosing a Machine Learning model: I choose a machine learning model that can be used to predict which player is most likely to score the most points. Future patches could use a different supervised learning model- such as a linear regression, decision tree, or random forest, etc., if the problem changes.
5. Training the model: I train the model using the preprocessed data and the chosen machine learning algorithm.
6. Evaluating the model: I evaluate the performance of the model by calculating metrics such as accuracy, precision, and recall.
7. Deployment: Once the model is trained and evaluated, you can deploy it to an application or a website where users can access the predictions. It converts miles to kilometers.
````
Libraries needed: 
Pip, Python, Pandas, and Seaborn

In this tutorial, we will focus on the first step of the process: fetching the data, downloading the libraries, cleaning and preprocessing the data.

## Fetching the data

The first step in the process is to fetch the data from the website. We will use the requests library in Python to fetch the data.

The requests library is a popular library in Python that allows you to send HTTP requests using Python. It abstracts the complexities of making requests behind a simple API so that you can focus on interacting with the services and consuming data in your application.

To install the requests library, you can use the pip package manager. Open the terminal and run the following command:

```
pip install requests
```

Once the requests library is installed, you can import it into your Python script and use it to fetch the data from the website. Easy!

```
import requests

url = 'https://t-leopards.com/stats/players'

response = requests.get(url)

print(response.text)
```

The code above fetches the data from the website and prints it to the terminal.

## Cleaning and preprocessing the data

The next step in the process is to clean and preprocess the data.

The data that we fetched from the website is in HTML format. We will need to parse the HTML data into a format that can be used for analysis.

We will use the BeautifulSoup library to parse the HTML data.

The BeautifulSoup library is a popular library in Python that allows you to parse HTML and XML documents. It provides a simple API for navigating, searching, and modifying the parse tree.

To install the BeautifulSoup library, you can use the pip package manager. Open the terminal and run the following command:

```
pip install beautifulsoup4
```

Once the BeautifulSoup library is installed, you can import it into your Python script and use it to parse the HTML data.

```
from bs4 import BeautifulSoup

soup = BeautifulSoup(response.text, 'html.parser')

print(soup.prettify())
```

The code above parses the HTML data and prints it to the terminal.

The next step is to extract the data from the HTML data.

We will use the find_all method to extract the data from the HTML data.

The find_all method finds all the elements that match the specified name, keyword arguments, and limit.

```
table = soup.find_all('table')[0]

print(table.prettify())
```

The code above extracts the table from the HTML data and prints it to the terminal.

The next step is to extract the rows from the table.

We will use the find_all method to extract the rows from the table.

```
rows = table.find_all('tr')

print(rows)
```

The code above extracts the rows from the table and prints them to the terminal.

The next step is to extract the columns from the rows.

We will use the find_all method to extract the columns from the rows.

```
for row in rows:
    columns = row.find_all('td')
    print(columns)
```

The code above extracts the columns from the rows and prints them to the terminal.

The next step is to extract the data from the columns.

We will use the get_text method to extract the data from the columns.

The get_text method returns the text content of the element without the HTML tags.

```
for row in rows:
    columns = row.find_all('td')
    for column in columns:
        print(column.get_text())
```

The code above extracts the data from the columns and prints them to the terminal.

The next step is to store the data in a dataframe.

We will use the pandas library to store the data in a dataframe.

The pandas library is a popular library in Python that provides high-performance, easy-to-use data structures and data analysis tools.

To install the pandas library, you can use the pip package manager. Open the terminal and run the following command:

```
pip install pandas
```

Once the pandas library is installed, you can import it into your Python script and use it to store the data in a dataframe.

```
import pandas as pd

data = []

for row in rows:
    columns = row.find_all('td')
    data.append([column.get_text() for column in columns])

df = pd.DataFrame(data)

print(df)
```

The code above stores the data in a dataframe and prints it to the terminal.

## Happy Coding! 

Beta membership Available in the ".github" -> "FUNDING.yml" to see how I figured it out and to contribute to further patches!
New Patch drops when I get 20 subscribers to my Patreon: 
````
Copy/Paste into browser:
patreon.com/swooshcode
````
