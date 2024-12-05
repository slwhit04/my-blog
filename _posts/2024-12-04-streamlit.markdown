---
layout: post
title:  "Life Expectancy Goes to the Dogs: A Streamlit Data Adventure"
description: In this post I show how I created a streamlit app to help learn about different dog breeds and explore how their height and weight affects their life expectancy. 
image: /assets/img/dog_banner.jpg
---


I consider myself an avid pet lover and I especially love dogs. Growing up, my family always had at least two dogs, sometimes three at a time and they were often all different breeds of dogs. Now that I am older, I am at a point in my life where I will be able to get my own dog and will need to decide on what kind of dog I want. 
  
  
Using streamlit, I created an app to help users quickly learn about different dog breeds and to be able to compare their height, weight and life expectancy. Users can filter to specific dog breeds, breed types, as well as filter the average height, weight and life expectancy for the breed.




<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/Cairn-Terrier-puppies.avif' alt = "" style = "width: 80%;"/>

</figure>
  

## using my streamlit app

As aforementioned, my app consists of several interactive elements. These include filters, a dataset overview, visualizations and a comparative analysis tab.

### Filter Tab

* You can add the following filters:
  * Breed Group
  * Height (6-31 inches)
  * Weight (5-195 pounds)
  * Life Expectancy (6-18 years)
  * Specific Breed

 <figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/Cairn-Terrier-puppies.avif' alt = "" style = "width: 80%;"/>

</figure>

### Dataset Overview Tab

The dataset overview lists all the different dog breeds and their data and as you explore my app you can see that the dataset responds to the filters applied. There is also an option to download the data


### Visualization Tab

I have three different plots under the visualization tab to answer my question as to how a dog’s size affects its life expectancy. Each graph is interactive and responds to the filters that are applied, the user can also zoom in and out on the graphs. I included one of my plots below:

<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/dog_weight_and_life_expectancy.png' alt = "" style = "width: 80%;"/>

</figure>



The first plot is a scatterplot which shows the relationship between a dog’s weight and its life expectancy. I included a red regression line to clearly show the trend that as a dog’s weight increases, the life expectancy drops. 

The second plot is very similar to the first but shows the relationship between height and life expectancy instead of weight. Here you can see the trend is not as strong, but there is still an overall negative that illustrates how as a dog’s height increases their life expectancy drops.

The third plot is a box plot of the different breed types and their average life expectancy. Once again you can see that the larger breed groups have shorter life spans than the smaller breed groups such as the toy group or terrier group. 

### Comparative Analysis Tab

The last tab allows you to do a breed comparison of two different dog breeds so you can directly see how the two breeds differ.

<figure>

<img src='https://raw.githubusercontent.com/slwhit04/my-blog/refs/heads/main/assets/img/dog_weight_and_life_expectancy.png' alt = "" style = "width: 80%;"/>

</figure>



## Final Thoughts

I am not sure of all the reasons why larger dogs do not live as long as their smaller counterparts, I know that there are sometimes issues with the heart being unable to pump blood all the way through the larger dog’s body. That being said, I am sure there are countless other reasons as well that I encourage you to research on your own either by doing a quick google search, or running your own eda to answer your questions. 

If you would like a better look at my code and how I set up my streamlit app, you can access it at my [github repo](https://github.com/slwhit04/streamlit2).

If you would like to learn how to set up your own streamlit app I recommend [geeksforgeeks's](https://www.geeksforgeeks.org/a-beginners-guide-to-streamlit/) tutorial.



Good luck! ;)
