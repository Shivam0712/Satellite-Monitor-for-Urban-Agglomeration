# Satellite-Monitor-for-Urban-Agglomeration

## What is this monitor all about?
The monitor will comprise of a machine learning(CNN) model at core which will take night light images thumbnail as input and output whether the place is urban or not.

## What are its feature?
The sytem will identify urban places and will keep record of its co-ordinates:
1. It will keep augmenting itself and keep adding new coordinates which it identifies as to be urban.
2. for the existing urban places it will identify the growth of these agglomerations and keep augmenting the boundaries.
3. It will monitor the intensity of night light in these centres and will create a time series analysis.

## How this will work?
A CNN model will be the core of this model.

### For feature 1: Augmenting new coordinates of URBAN CITIES.
High night light value pixels will be identified in whole India.
A thumbnail of nearing pixels will be passed to the model and will get classified as Urban or Not.
If True then thumbnail of similar size in all the 8 directions: N,S,E,W, NE, NW, SE, SW will be passed to the model. If again any of the thumbnail gets classified as urban, nearing thumbnails of that thumbnail will be passed into the model and the loop will continue till it breaks. Once the loop is complete, the constructed picture of these thumbnails will be passed into another model which will mark the boundaries and generate KML file.

### For feature 2: Study growth of these agglomerations.
The boundary file generated will be compared to the boundary file of previous run and if there is some change; then, the change will be quantified and studied again.

### For feature 3: Time series analysis of these agglomerations.
The intensity output at every period P(month or quarter) for these agglomerations will be saved in a database and a comparison study will be done to extract out time series features such as disruptions and other seasonal/trend attributes. 
