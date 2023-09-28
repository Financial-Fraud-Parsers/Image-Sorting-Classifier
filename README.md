# Running-Classifier

#### Model Overview

- A CNN model with 7 Conovolution and 4 dense layers with SGD optimizer and trained over 35000 images of 3 classes Bank Accounts, Money Apps, Cheques.
- Model accuracy for classifying checks is 78%.
- Model is around 25MB, uploaded here - https://www.dropbox.com/scl/fo/xs7472r946nmu05ylue9t/h?rlkey=4dil05t4k0xxc9ztzakrocmtw&dl=0
- Classifier code - https://github.com/Financial-Fraud-Parsers/Image-Sorting-Classifier

#### Classifier Overview

- GSU Arctic cluster is used to store directory structure in the cluster.
- Model is stored on the cluster for direct import and run.
- Data is scraped every 5 days and loaded to the runtime from dropbox.
  -  The data comes from 80 channeles and is loaded into single array.
  -  Next step is to preprocess the data.
  -  For pre-processing, images are resized to 255x255 pixel images and converted to gray scale.
  -  Model to predict the class of each image as 0,1 or 2.
  -  Class 0 is cheques, class 1 is for bank accounts, class 2 is for money apps.
  -  Data stored in the two folders are transfered to the dropbox.


#### To Run the Classifier
- change the Dir_Name to "Month date - date" which is usually the folder name.
- change the Root_Dir to the folder path.

#### Data preparation
- #### Local
  - Download the image zip folder.
  - Used as it is by changing a name in code.
 
- #### Google CoLab
  - Create a folder in google drive
  - Upload the model folder
  - Upload the data zip
  - Upload the code into that folder
  - Open code in colab
  - goto runtime > select change Runtime > make it to GPU and save changes.
  - To use the data in colab
      - Mount the data using
        ```
             from google.colab import drive
             drive.mount('/content/drive')
        ```
      - Make changes in the code to run classifier in google colab due to different OS library.
        
