---
layout: post
title: "[Projects] GPS Mapping Analysis of FSU Campus Movements"
---
This was a class project for my Map Analysis class. The assignment was very vague and consisted of making any kind of map that you wanted. For my project, I wanted to use GPS data of my movements around campus to see if there was any true correlation between the elevation of campus and my transportation choices.

For the data collection I used the android App [Moves](https://www.moves-app.com/). This allowed me to collect all of my movements around campus as it ran in the background on my phone. From here, it would classify the transportation type based on the speed of my movement so I was able to parse out the difference between walking and biking very easily. Now that I had all of my data collected, you are able to export the data into KML format and it is separated into daily, weekly, or monthly files. From here, I used Google Earth to visualize the data points.

From here, it was tricky and I needed to develop a way to count the points that were along each of the routes around campus stemming from my dorm. My first idea on the direction that I wanted to go was to use SQL in order to query a csv and count the points that were within bounding boxes of the routes. After about 20 hours of trying to teach myself the entirety of SQL in order to get that method working, I gave in and went back to the drawing board.

After consulting with my professor, she suggested a route using [R](https://www.r-project.org/). I kept the same bounding box technique because I thought that was the most direct way for me to be able to count the GPS points along the routes. That part was tedious and I imagine there is a much better programmatic way to complete that task, especially using the Mapbox.js library.

R was quite the language to learn and I got a lot of help from my professor to figure out the queries needed in order to make those counts. Once we were able to get some solid counts with the scripts, I was able to iterate through all of the bounding boxes and use each of the biking and walking data sets for the month.

Taking the counts, I was able to assign the routes scores and then simply changed the line thickness based on different internvals of counts, thus creating a scaled legend for the trips taken along certain paths. The lines simply lived in KML files that I loaded into Google Earth in order to visualize the lines. The resulting visualization is by no means something good to look at but it communicated and confirmed my hypothesis.

![Final Visualization Map](/images/posts/kml-map-final.png )

The code 
