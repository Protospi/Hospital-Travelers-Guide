# Hospital-Travelers-Guide

This project repo was created as a version control and file storage/share/collaborate. The main purpose of this project is the developement of an prototype application that will be presented as a data product for the stakeholders of a travel insurance company for approval. The purpose of the application is to guide traveler to the __near hospitals__ based on they're location coordinates.

***

Links:

* [Travelers Hospitals Guide App](https://loes.shinyapps.io/travelers_hospitals_guide_app/)

* [Travelers Hospitals Guide Slides](https://loes.shinyapps.io/travelers_hospitals_guide_press/#1)

***

## Overview

* This is an R Markdown presentation that explains the implementation and usability of __Hospital Travelers Guide__ application developed as a final project to the __Coursera Jonh Hopkins Pratical Data Science Course__.

* I'm currently working on a chatbot company named __Guide121__ in Brazil as a data analysist. For one of our clients, a travel insurance company, we implemented a network model to classify travelers needs based on text inputs between __16__ categories and one of then is health inssurance.

* The main purpose of the application is to guide the traveler to the __near hospitals__ based on the traveler location coordinates shared by __whatsapp__.

***

## Conversation Flow

1. Travelers start to talk with the chatbot and write they're main reason to reach for insurance support.
2. A __Neural Network__ model predicts that the user wants information about near hospitals.
3. The bot asks for user location.
4. The application calculate distances from latitudes and logitudes agaist the hospitals database.
5. A world map is rendered on a __html__ page with the __traveler__ and the __3__ hospitals markers with name and adresses of the hospitals and also __3__ lines with the distances in kilometers.
6. A __url__ link is sent to the travelers on whatsapp so they can vizualize the map on a __browser__.

***

## Data Scource

* The dataset was retrieved through the donwload of a file in `.csv` format on the website below.

* [Geoplatform Opendata Arcgis](https://hifld-geoplatform.opendata.arcgis.com/datasets/6ac5e325468c4cb9b905f1728d6fbf0f_0/explore?location=36.946719%2C64.325615%2C4.00)

* This feature class/shapefile contains Hospitals derived from various sources for the [Homeland Infrastructure Foundation-Level Data](https://gii.dhs.gov/HIFLD)
  
* The data base contains __7.623__ hospitals with features like names, adresses, latitudes and longitudes. It's not even __10%__ of the total hospitals in the world but the data is free and this project is just a prototype for a _minimum viable product_ that will go onto production if it's approved by stakeholders.

***

## Algorithm

1. Load the hospitals data base, filter for _name_, _address_, _latitude_ and _longitude_.
2. Bind the rows with traveler coordinates data.
3. Calculate the euclidian distance between coordinates of the traveler and hospitals, arrange by distance and slice first __3__.
4. Tranform the coordinate to the projection __+init=epsg:4326__ and calculate the distance in kilometers.
5. Draw the leafleat map plot in html web shiny reactive enviroment with the fllowing elements:
6. Overlay markers for the traveler and __3__ nears hospital with hoover tooltip containing the name and address of the hospitals. Lines between the traveler and the __3__ hospitals with hoover tooltip showing the distance in kilometers. 

***
