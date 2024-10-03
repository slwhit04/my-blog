---
layout: post
title:  "How to Use Pyhigh Python Package to access Elevation"
description: This post will teach you how to use two different python packages to get elevation for your data.
image: /assets/img/blog-image.jpg
---

### Introduction to Pyhigh

Pyhigh is a package in Python that is used to access elevation data that was created by "sgherbst" on github. This package relies on caching to avoid unecessary downloads.To use this package, your data will need to include a latitude column and a longitude column containing latitiude and longitude coordinates respectively. 

### Getting Started

 To demonstrate how to use each one I will be working with a dataset of Chipotle locations which can be downloaded [Here](https://www.kaggle.com/datasets/jeffreybraun/chipotle-locations). I am specifically insterested in Utah locations so after reading in my Chipotle data I will filter my data to only include Utah rows. This can be done as shown below:
```
import pandas as pd

# Load your dataset
chipotle_df = pd.read_csv('C:\\Documents\\pythonProject\\blog_tutorial\\chipotle_locations')
# Filter chipotle data to only include Utah
utah_df = chipotle_df[chipotle_df['state'] == 'Utah']

# View your new df
print(utah_df.head())

```
