---
layout: post
title:  "Life Expectancy Goes to the Dogs: A Streamlit Data Adventure"
description: In this post I show how I created a streamlit app to help learn about different dog breeds and explore how their height and weight affects their life expectancy. 
image: /assets/img/dog_banner.jpg
---


I consider myself an avid pet lover and I especially love dogs. Growing up, my family always had at least two dogs, sometimes three at a time and they were often all different breeds of dogs. Now that I am older, I am at a point in my life where I will be able to get my own dog and will need to decide on what kind of dog I want. This is a big decision as there are hundreds of different dog breeds to choose from, each with their own distinct qualities. To help me with this choice, I created a "dog breed insights" app to help in visualizing my options. 
  
  
Using streamlit, I created an app which you view [here](https://slwhit04-dog-data.streamlit.app/). This app was designed to help myself, as well as other dog lovers, quickly learn about different dog breeds and to be able to compare their height, weight and life expectancy. Users can filter to specific dog breeds, breed types, as well as filter the average height, weight and life expectancy for the breed.


<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/dogs.jpg' alt = "" style = "width: 90%;"/>

</figure>
  

## Using My Streamlit App

As aforementioned, my app consists of several interactive elements. These include filters, a dataset overview, visualizations and a comparative analysis tab.

#### Filter Tab

* You can add the following filters:
  * Breed Group
  * Height (6-31 inches)
  * Weight (5-195 pounds)
  * Life Expectancy (6-18 years)
  * Specific Breed

 <figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/filter.png' alt = "" style = "width: 100%;"/>

</figure>

#### Dataset Overview Tab

The dataset overview lists all the different dog breeds and their data and as you explore my app you can see that the dataset responds to the filters applied. There is also an option to download the data


#### Visualization Tab

I have three different plots under the visualization tab to answer my question as to how a dog’s size affects its life expectancy. Each graph is interactive and responds to the filters that are applied, the user can also zoom in and out on the graphs. I included one of my plots below:

<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/scatterplot.png' alt = "" style = "width: 100%;"/>

</figure>


This plot is a scatterplot which shows the relationship between a dog’s weight and its life expectancy. I included a blue regression line to clearly show the trend that as a dog’s weight increases, the life expectancy drops. On the right side there is also a key which has a different color dot to represent the different breed groups. In the app, the user may also filter data which the graph will adjust to and the user may also zoom in and out and scroll to view different dots more closely. The user may also hover over a specific dot and can see which dog the specific data point represents

#### Comparative Analysis Tab

The last tab allows you to do a breed comparison of two different dog breeds so you can directly see how the two breeds differ. In the example below I chose to compare the rottweiler vs the doberman. Both are similar breeds that were bred for the same purpose, have the same country of origin (Germany), and share similar coat markings. Using the comparative analysis tab one can quickly see some of key differences between the two breeds.

<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/dog_compare.png' alt = "" style = "width: 100%;"/>

</figure>


## Final Thoughts

I hope that all my fellow dog lovers find my app interesting and are able to get some use out of it. I personally enjoyed being able to quickly compare the different breeds and seeing how the plots changed based on the filters I chose. I encourage everyone who looks at my app or reads this post to take the time to explore the features of my app and to discover new things about your favorite dog breeds. 

If you would like a better look at my code and how I set up my streamlit app, you can access it at my [github repo](https://github.com/slwhit04/streamlit2).

If you would like to learn how to set up your own streamlit app I recommend [geeksforgeeks's](https://www.geeksforgeeks.org/a-beginners-guide-to-streamlit/) tutorial.



Good luck! ;)
