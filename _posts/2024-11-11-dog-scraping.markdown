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

1. The first step with any python code is to install and import the packages that you need
    a. For Selenium, the base packages you will need is:
   {%- highlight python -%} from selenium import webdriver {%- endhighlight -%}
   {%- highlight python -%} from webdriver_manager.chrome import ChromeDriverManag {%- endhighlight -%}
2. The next step is to set up your Selenium webdriver
    a. The basic script is as follows:
   {%- highlight python -%} driver = webdriver.Chrome()  # or webdriver.Firefox()
driver.get("http://example.com")
driver.quit()
{%- endhighlight -%}
3. Once you have the base packages and scripts set up, your code will vary greatly depending on the website you are trying to scrape

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

Some general concepts of cleaning data. Explain what I used specifically and why.

{%- highlight python -%}
pass
{%- endhighlight -%}

## The Results

Summary statistics, summary graphics, and information about final dataset (e.g., total sample size, counts of categorical variables, numerical summaries of numeric variables)


	<This is an example >


## Continue Learning

[geeksforgeeks]([https://www.geeksforgeeks.org/selenium-python-tutorial/))


Good luck! ;)
