# data-scrape-challenge
Data Analytics Course Module 11

# Task
This web-scraping and data analysis task requires extracting information from two sources (a Mars news site and a Mars temperature data site) and creating two delivarables. The first deliverable will scrape titles and preview text from the news site while the second will scrape and analyze weather data from a table on the data site.

# Methodology
I will first identify HTML elements on a web page, particularly id and class attributes, in order to find titles and text previews for the first deliverable and data obejcts (ids, time records, temperature values, etc) for the second deliverable. I'll use automated browsing with Splinter and HTML parsing with Beautiful Soup.

## Exploration
Deliverable 1: Using inspect, I located all the text elements on the Mars news website. From there, I was able to see that titles were stored in a class named "content title" while the text preview was stored in a class called "article teaser body". I created a function that looped through each article to extra its title and preview text, storing the results in a list of dictionaries.
  
Deliverable 2:
1. I created a 'table' variable which held all rows of the table on the Mars temperature data website. Using inspect, I became familiar with how the table was arranged, looking particularly for column header elements (identified with a <th> or 'table header' tag) and stored data elements (identified with a <td> or 'table data' tag). With the goal of storing the table information as a Pandas DataFrame, I first tried creating a for loop that extracted both the header and the data. However, after troubleshooting, I realized that I needed two separate for loops: the first loop for column headers which would append the elements to a list of headers and a second loop, which ran through each row (identified with <tr> or 'table row') to extra data and append those elements to a list of data. I used these two lists to create the Pandas DataFrame.
2. With the website table now stored as a Pandas DataFrame, I changed the data types of most columns (originally all objects) in order to perform calculations on them.
  
## Analysis

Deliverable 1 did not require analysis.
Deliverable 2 required the use of Pandas functions to answer the following questions:
- How many months exist on Mars? **12 months**
- How many Martian (and not Earth) days worth of data exist in the scraped dataset? **1867**
- What are the coldest and the warmest months on Mars (at the location of Curiosity)? To answer this question:
  - Find the average the minimum daily temperature for all of the months.
  - Plot the results as a bar chart.
    ![bar chart of sorted daily temperatures on Mars]()
- Which months have the lowest and the highest atmospheric pressure on Mars? To answer this question:
  - Find the average the daily atmospheric pressure of all the months.
  - Plot the results as a bar chart.
    ![bar chart of sorted daily pressure on Mars]()

- About how many terrestrial (Earth) days exist in a Martian year? To answer this question:
  - Consider how many days elapse on Earth in the time that Mars circles the Sun once.
  - Visually estimate the result by plotting the daily minimum temperature.
  ![bar chart of sorted daily minimum temperatures on Mars]()
