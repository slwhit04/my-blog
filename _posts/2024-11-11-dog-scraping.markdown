---
layout: post
title:  "Do Small Dogs Live Longer?"
description: In this post I explain my process of scraping data from the web while exploring the question of how height effects a dog's life expectancy.
image: /assets/img/blog-image.jpg
---


<blockquote> Dogs are a man's best friend, however, we usually outlive our furry friends. There is not much we can do to increase their lifespan, however, the type of dog or size of dog may help determine how long they live. </blockquote>
  
  
<blockquote> I love dogs and have always been interested in them and I’ve heard that larger dogs don’t live as long as smaller dogs due to health complications. I decided to combine two of my interests, dogs and statstics, to explore if a dog’s size effects its life expectancy.</a>  </blockquote>

  

## How I got Started

To collect my dog data, I scraped all the dogs, aswell as their breed info, from the [American Kennel Club official website]([https://www.akc.org/dog-breeds/](https://www.geeksforgeeks.org/selenium-python-tutorial/)) To ensure ethical scraping practices, I first checked the website's robots.txt file which includes the website's policy on scraping data. 

![this will eventually be a dog](/assets/img/diving-horse.jpg)

/assets/img/blog-image.jpg


There are several different packages that can help with webscraping, however, selenium allows for automated webscraping and is what I used to scrape the AKC website. There are many approaches to using selenium and it varies per website, nonetheless, there are a few universal steps that are taken when using selenium for any website. 

1. The first step with any Python code is to install and import the packages that you need.
   - For Selenium, the base packages you will need are:
     ```python
     from selenium import webdriver
     from webdriver_manager.chrome import ChromeDriverManager
     ```

2. The next step is to set up your Selenium webdriver.
   - The basic script is as follows:
     ```python
     driver = webdriver.Chrome()  # or webdriver.Firefox()
     driver.get("http://example.com")
     driver.quit()
     ```

3. Once you have the base packages and scripts set up, your code will vary greatly depending on the website you are trying to scrape.

Example of how I set up my Selenium WebDriver
{%- highlight python -%}
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
import time
import pandas as pd

# Set up Selenium
options = webdriver.ChromeOptions()
options.add_argument("--start-maximized")
driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()), options=options)

# Open the website
driver.get("https://www.akc.org/dog-breeds/")
{%- endhighlight -%}


## Cleaning

Once you have your scraped data, you will almost always need to clean it before performing EDA. Within the pandas package alone, there are dozens of ways to manipulate your data. For example, there are functions to drop all NA values, drop duplicates, remove columns, rename columns, do string manipulation, and more.[This website]([https://realpython.com/python-data-cleaning-numpy-pandas/) covers how to clean data using Python's pandas and NumPy libraries.

For my own data, I used *the drop_duplicates()* function and *str.replace*


## The Results

Once I was done cleaning and had dropped all duplicates, there were a total of 290 rows and below I have listed the summary statistics for numeric valriables:


	Summary statistics for numeric variables:
           Height  Life Expectancy
	count  216.000000       280.000000
	mean    19.303819        12.739286
	std      6.010377         1.652052
	min      6.500000         6.500000
	25%     14.000000        12.000000
	50%     19.500000        13.000000
	75%     24.812500        13.500000
	max     31.000000        18.000000

Additionally, I ran created three plots to help answer my question as to whether small dogs live longer.

AKC lists a range for height, weight, and life expectancy so before I could do my EDA, I found the average of each of those values for each dog breed. Once that was done, I used *matplotlib* and *seaborn* to create the following visuals:

![dog weight and life expectancy](/assets/img/diving-horse.jpg)

![dog height and life expectancy](/assets/img/diving-horse.jpg)

![life expectancy by breed](/assets/img/diving-horse.jpg)


## Continue Learning

For more detail on how to use selenium I reccommend following [geeksforgeeks's]([https://www.geeksforgeeks.org/selenium-python-tutorial/) tutorial.

If you would like a better look at my code, you can access it at my [github repo].([https://www.geeksforgeeks.org/selenium-python-tutorial/)


Good luck! ;)
