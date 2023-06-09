# Deep-Learning-Challenge

## Overview


The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. 

The purpose of this analysis is to evaluate the performance of machine learning models and deep learning neural networks, on funding with the best chance of success in the charity's ventures. The aim is to evaluate how successfully the neural network can predict if an applicant will be successful if funded by Alphabet Soup.

Alphabet Soup’s business team provided a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

- EIN and NAME — Identification columns
- APPLICATION_TYPE — Alphabet Soup application type
- AFFILIATION — Affiliated sector of industry
- CLASSIFICATION — Government organization classification
- USE_CASE — Use case for funding
- ORGANIZATION — Organization type
- STATUS — Active status
- INCOME_AMT — Income classification
- SPECIAL_CONSIDERATIONS — Special considerations for application
- ASK_AMT — Funding amount requested
- IS_SUCCESSFUL — Was the money used effectively


## Results

### Step 1: Data Preprocessing

- The target variable for this model is the "IS_SUCCESSFUL" variable. This is a categorical data indicating whether funding was used effectively for an approved application.

- The following variables are the feature variables of the model:

    - EIN and NAME — Identification columns
    - APPLICATION_TYPE — Alphabet Soup application type
    - AFFILIATION — Affiliated sector of industry
    - CLASSIFICATION — Government organization classification
    - USE_CASE — Use case for funding
    - ORGANIZATION — Organization type
    - STATUS — Active status
    - INCOME_AMT — Income classification
    - SPECIAL_CONSIDERATIONS — Special considerations for application
    - ASK_AMT — Funding amount requested

- EIN and NAME variable were removed intially from the input data because they are neither targets nor features. However, only EIN has been removed in the optimization file

### Step 2: Compiling, Training, and Evaluating the Model

- For the initial model 3 layers were used for the model compilation, training and evaluation process. On the other hand, 3 layers were used for the optimization process as 4 layers were enough to predict most of the data. Layer details are as follows:

    Initial Model:

    - First hidden layer: 80 neurons, relu activation function
    - Second hidden layer: 30 neurons, relu activation function
    - Output layer: 1 neuron, sigmoid activation function

    Optimization Model:

    - First hidden layer: 90 neurons, relu activation function
    - Second hidden layer: 30 neurons, relu activation function
    - Third hidden layer: 20 neurons, relu activation function
    - Output layer: 1 neuron, sigmoid activation function

-  Target initial Keras model performance was achieved as follows

<img width="742" alt="initial_model" src="https://github.com/FahmidaBilla/Deep-Learning-Challenge/assets/120361200/9ec76488-f323-4be2-91c5-defa8f8ce061">




-  Target optimized model performance was achieved as follows

<img width="1159" alt="optimization_model" src="https://github.com/FahmidaBilla/Deep-Learning-Challenge/assets/120361200/f7f92220-25cd-4df7-853d-ac4a5b6f2b16">





- Steps taken to increase model peformance:

    - Kept the NAME variable and binned any values with a count less than 100 as 'Other'

        <img width="887" alt="name" src="https://github.com/FahmidaBilla/Deep-Learning-Challenge/assets/120361200/608575fa-b4c0-4468-aa0d-c9c894752841">




    - Binned AFFILIATION variable for any values with a count less than 60 as 'Other'

        <img width="784" alt="affiliation" src="https://github.com/FahmidaBilla/Deep-Learning-Challenge/assets/120361200/1da035a7-9a41-414e-9dec-6b995f528de3">





    - Binned CLASSIFICATION variable for any values with a count less than 1000 as 'Other' instead of 700 

        <img width="830" alt="classification" src="https://github.com/FahmidaBilla/Deep-Learning-Challenge/assets/120361200/f24a888d-0bfe-4541-8db4-e899705bc6cd">






    - Added a third hidden layer
    - Trained the model with 110 epochs


## Summary

By optimizing the model target achivement accuracy improved and reached a little over 75% accuracy in classfying applications as successful or unsuccessful. The model accuracy started with 72% accuracy with the initial neural network model. 

Keeping the NAME variable might have resulted in overfitting the model and might impact the process of classifying applications. We could incorporate Random Forest Model to assess the importace of each variable and eliminate them according to their importance to better predict the model with less possibility of overfitting. 







