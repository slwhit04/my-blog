---
layout: post
title:  "How to Use Pyhigh Python Package to access Elevation"
description: This post will teach you how to use Pyhigh to access and add elevation to your data
image: /assets/img/blog-image.jpg
---

<blockquote> When working with locations, it is often useful to know some details about those locations as theses variables could potentially be affecting your results. One such variable is elevation. Elevation can affect all sorts of things with various sets of data. Elevaiton can change how a runner or athlete performs, influence how crops grow, help determine flood risks and so much more. However, your data might not come with elevation already attatched. This post will teach you an easy way to attatch elevation to your data using a Python package called Pyhigh. </blockquote>
  
  
<blockquote> Pyhigh is a package in Python created by <a href="https://github.com/sgherbst" target="_blank">Steven Herbst</a> on github that allows the user to access elevation data. This package relies on caching to avoid unnecessary downloads. To use this package, your data will need to include a latitude column and a longitude column containing latitude and longitude coordinates respectively. Note that elevation will be in meters. </blockquote>

  

## Getting Started

To demonstrate how to use Pyhigh I will be working with a dataset of Chipotle locations which can be downloaded from kaggle using [This Link](https://www.kaggle.com/datasets/jeffreybraun/chipotle-locations). I am specifically insterested in Utah locations so after reading in my Chipotle data I will filter my data to only include Utah rows. This can be done as shown below:

{%- highlight python-%} 
import pandas as pd

#Load your dataset
chipotle_df = pd.read_csv('C:\\Documents\\pythonProject\\blog_tutorial\\chipotle_locations')
#Filter chipotle data to only include Utah
utah_df = chipotle_df[chipotle_df['state'] == 'Utah']

#View your new df
print(utah_df.head())
{%- endhighlight-%}

After filtering your data, there should be five Utah locations in total. 

## Installing and Importing Pyhigh

The First thing you will need to do to use PyHigh is to install it. I use the built in terminal within PyCharm and ran the line of code *pip install pyhigh* as shown below:

```
pip install pyhigh
```

Next you will need to import pyhigh. You can import pyhigh as is however, with larger datasets it is better to use *elevation_batch*. After filtering to only Utah locations, the dataset is small enough that either one would work. However, I will be using elevation_batch in my example. To import elevation_batch use:
{%- highlight python -%}
from pyhigh import get_elevation_batch
{%- endhighlight -%}

## Using Pyhigh

To use pyhigh, you first need to extract each pair of latitude and longitiude coordinates and save them as an variable. 
{%- highlight python-%} 
pairs = list(zip(utah_df['latitude'], utah_df['longitude']))
{%- endhighlight -%}

Next, we will need to use the *get_elevation_batch* function to get the elevation pairs and save them as a new variable.
{%- highlight python-%} 
elevations = get_elevation_batch(pairs)
{%- endhighlight -%}

Now that we have our elevation mapped to our latitude and longitude pairs, we need to add the elevations as a new column and print the first few rows of the data set to unsure everything worked.
{%- highlight python-%} 
utah_df['elevation'] = elevations

#View updated utah df
print(utah_df.head())
{%- endhighlight -%}

Once you have your dataframe looking the way you want it, you can save your data as a new .csv file.

{%- highlight python-%} 
utah_df.to_csv('utah_elevations.csv', index=False)
{%- endhighlight -%}


## Final Thoughts

Here is what my final code looks like all together.
{%- highlight python-%} 
import pandas as pd
from pyhigh import get_elevation_batch

#Load your dataset
chipotle_df = pd.read_csv('C:\\Documents\\pythonProject\\blog_tutorial\\chipotle_locations')
#Filter chipotle data to only include Utah
utah_df = chipotle_df[chipotle_df['state'] == 'Utah']

#Check the filtered DataFrame
print(utah_df.head())

#Extract latitude and longitude pairs
pairs = list(zip(utah_df['latitude'], utah_df['longitude']))

#Get elevations in batch
elevations = get_elevation_batch(pairs)

#Add the elevations as a new column
utah_df['elevation'] = elevations

#View your updated DataFrame
print(utah_df.head())

#Save data as csv file
utah_df.to_csv('utah_elevations.csv', index=False)

{%- endhighlight -%} 


If you have read this far you should now be able to successfully add elevation to your data and be able to visualize your new data! Here is a simple plot I created to illustrate elevation by location using matplotlib and seaborn packages in python.

![Figure](https://slwhit.github.io/my-blog/assets/img/figure_1.png)

Try following along this tutorial using your own data to add and visualize elevation!


*Note that the larger the dataset the longer it will take to get the elevation as it goes through each longitude and latitude pair one at a time and downloads the elevation*


Good luck! ;)
