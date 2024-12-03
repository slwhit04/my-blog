---
layout: post
title:  "Do Small Dogs Live Longer?"
description: In this post I explain my process of scraping data from the web while exploring the question of how height affects a dog's life expectancy.
image:"https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/dog_banner.jpg"
---


Dogs are a man's best friend; however, we usually outlive our furry friends. There is not much we can do to increase their lifespan; however, the type of dog or size of dog may help determine how long they live.
  
  
I love dogs and have always been interested in them and I’ve heard that larger dogs don’t live as long as smaller dogs due to health complications. I decided to combine two of my interests, dogs and statistics, to explore if a dog’s size effects its life expectancy.




<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/Cairn-Terrier-puppies.avif' alt = "" style = "width: 80%;"/>

</figure>
  

## How I got Started

To collect my dog data, I scraped all the dogs, as well as their breed info, from the [American Kennel Club official website]([https://www.akc.org/dog-breeds/](https://www.geeksforgeeks.org/selenium-python-tutorial/](https://www.akc.org/))) To ensure ethical scraping practices, I first checked the website's robots.txt file which includes the website's policy on scraping data. 


There are several different packages that can help with webscraping; however, selenium allows for automated webscraping and is what I used to scrape the AKC website. There are many approaches to using selenium and it varies per website, nonetheless, there are a few universal steps that are taken when using selenium for any website. 

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

Once you have your scraped data, you will almost always need to clean it before performing EDA. Within the pandas package alone, there are dozens of ways to manipulate your data. For example, there are functions to drop all NA values, drop duplicates, remove columns, rename columns, do string manipulation, and more. [This website](https://realpython.com/python-data-cleaning-numpy-pandas/) covers how to clean data using Python's pandas and NumPy libraries.

For my own data, I used *the drop_duplicates()* function and *str.replace*


## The Results

Once I was done cleaning and had dropped all duplicates, there were a total of 290 rows and below I have listed the summary statistics for numeric variables:


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

Additionally, I created three plots to help answer my question as to whether small dogs live longer.

AKC lists a range for height, weight, and life expectancy so before I could do my EDA, I found the average of each of those values for each dog breed. Once that was done, I used *matplotlib* and *seaborn* to create the following visuals:

<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/dog_weight_and_life_expectancy.png' alt = "" style = "width: 80%;"/>

</figure>


<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/dog_height_and_life_expectancy.jpg' alt = "" style = "width: 80%;"/>

</figure>

<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/life_expectancy_by_breed_group.png' alt = "" style = "width: 80%;"/>

</figure>


The first plot is a scatterplot which shows the relationship between a dog’s weight and its life expectancy. I included a red regression line to clearly show the trend that as a dog’s weight increases, the life expectancy drops. 

The second plot is very similar to the first but shows the relationship between height and life expectancy instead of weight. Here you can see the trend is not as strong, but there is still an overall negative that illustrates how as a dog’s height increases their life expectancy drops.

The third plot is a box plot of the different breed types and their average life expectancy. Once again you can see that the larger breed groups have shorter life spans than the smaller breed groups such as the toy group or terrier group. 


## Final Thoughts

I am not sure of all the reasons why larger dogs do not live as long as their smaller counterparts, I know that there are sometimes issues with the heart being unable to pump blood all the way through the larger dog’s body. That being said, I am sure there are countless other reasons as well that I encourage you to research on your own either by doing a quick google search, or running your own eda to answer your questions. 

For more detail on how to use selenium I recommend following [geeksforgeeks's](https://www.geeksforgeeks.org/selenium-python-tutorial/) tutorial.

If you would like a better look at my code, you can access it at my [github repo](https://github.com/slwhit04/my_blog_code/tree/main).


Good luck! ;)
