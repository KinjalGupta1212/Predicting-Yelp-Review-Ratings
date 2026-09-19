# Predicting Yelp Review Ratings Using Sentiment Analysis
## Environment
The environment required to run this code is Google Workspace, specifically Google Drive and Google Colab. The necessary files to run the code (such as data files) should be stored in Google Drive and the code will be ran via Google Colab. Google Colab was choosen as the coding environment due to its GPU offerings, which our group did not have on our local machines. It is preferable to use Google Colab Pro so the GPU is consistently available while running the code and the large amount of data can be processed at a reasonable speed.
## Data
The data used for this project is the ["Yelp Open Dataset."](https://business.yelp.com/data/resources/open-dataset/)
The link above provides an option to "Download JSON." Click on that to down the necessary JSON files to your local machine. The are in a TAR file. Uncompress the TAR file and then add "yelp_academic_dataset_business.json",    "yelp_academic_dataset_review.json", and "yelp_academic_dataset_user.json" to your desired folder in Google Drive. 
## Required Packages
The code uses the following packages. Because the environment is Google Colab, the following packages are pre-installed and used in our code through from/import statements:
- google.colab 
- os
- json
- pandas 
- random
- concurrent 
- transformers 
- torch
- tqdm 
- sklearn
- scipy 
- numpy  
- seaborn
- matplotlib 

We also install [gibberish-detector](https://github.com/domanchi/gibberish-detector?tab=readme-ov-file) using 
```
pip install gibberish-detector
```
To effectively use gibberish-detector, navigative to the link above, access the "examples" folder, then download "big.txt". Then, on your local machine, such as in Terminal, navigate to the folder which includes big.txt and run: 
```
gibberish-detector train big.txt > big.model
```
Store "big.model" in the same Google Drive folder as the dataset json files. 
## How to Run
1. Open the ipynb notebook in Google Colab. Navigate to Edit > Notebook Settings and select "High-RAM" and "T4 GPU". 
2. In the first code cell in the notebook, change the drive path to the location of your json files and big.model files. 
3. Now, in the code cell under "Load Data From Json Files", set the sample size to your desired sample size in ```load_review_data_reservoir```. We used 200,000 for our experiments but for a faster run of the code, use a sample size of 1000. 
4. Now, each code cell can be run in order to ensure proper drive mounting, data loading, data exploration, cleaning, gibberish detection, sample set creation, sentiment analysis and feature building, training and testing set creations for for each ablation,  model creations for all ablations, and parameter hypertuning. 
