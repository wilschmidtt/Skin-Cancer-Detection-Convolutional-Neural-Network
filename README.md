# Skin Cancer Detection Convolutional Neural Network - HackDavis 2020
#### The Event 
UC Davis's Premir Hack-A-Thon for social good! On January 18-19, over 600 students, hackers, and creators came together for 24 hours of hacking. For the 5th year in a row, the most talented students in California come together to address the world’s most pressing issues. Participants are able to build projects that address any social good initiatives.
#### Team's Solution
Build and train a Convolutional Neural Network to detect if skin scans show signs of cancer. [View Project Website Here](https://devpost.com/software/ml-diagnose)

### Prerequisites
* Anaconda (Python 3.7 Version)
  - [Anaconda Instillation Instructions](https://docs.anaconda.com/anaconda/install/)
  - Chosing to use Anaconda is optional; however, the Spyder environment included is very useful for Machine Learning projects

## Libraries to Install
* keras - neural network library
  - `conda install -c conda-forge keras`

## Running the tests

* First, download the files titled model.json and model.h5 and save them to a desired directory.
* Next, open Anaconda, launch Spyder (used version 3.3.6 to create this program), and run the program titled: skin_cancer_prediction_regression.py
  - NOTE: There is another file titled Skin_Cancer_CNN.py. This file contains much of the same code as skin_cancer_prediction_regression.py; however, this is the module that was used to train the CNN, and running it will take a significant amount of time. The regression equation has been exported to the skin_cancer_prediction_regression.py file, so this one will be much quicker to run.
* Next, user will need to change the program lines containing the directories of the .json and .h5 files that were used to store the regression equation. The line used to open the .json file looks as follows: 
`json_file = open('/content/drive/My Drive/Skin Cancer CNN/model.json', 'r')`. 
As you can see, I had this file saved to a folder in my Google Drive; nevertheless, the user will have to change the specified directory to match that of where the .json file is located for them. Next, the code used to import the .h5 file is as follows: `loaded_model.load_weights("/content/drive/My Drive/Skin Cancer CNN/model.h5")`. 
This too will need to be changed to match the directory that the user saved the .h5 file in.
* Finally, the user will need to obtain an image of a skin scan in question. How to go about obtaining this image is up to the user's disgression; it can be as simple as a picture taken with a cell phone of one's skin. The image can be of any format. Once obtained, save the image to a desired directory. The line of code within the program used to make a prediction about the image is as follows: `user_data = test_datagen.flow_from_directory('/content/drive/My Drive/Skin Cancer CNN/User-Data/test', target_size = (64, 64), batch_size = 1, class_mode = 'binary')`. As can be seen, the image that I used was located inside of my Google Drive. This directory will need to be changed to match the directory of the user's image.
* Once the program is run, the user can expect to see one of two messages: 
  1) The convolutional neural network predicts that this tumor is benign.
  2) The convolutional neural network predicts that this tumor is malignant!

## Final Thoughts
* After training the model, our team was able to get it to classify images in the test set with **87% accuracy**. The model was trained using the free Google Colaboratory service and their remote GPU, but the time required to train this model was still substantial. If the user has access to more computing power, then this model can be trained with more data and epochs, and reach a much higher accuracy (99% and above). The file used to train the neurl network is titled "Skin_Cancer_CNN.py", and users can feel free to run this program on their own GPU, tune the parameters differently, and use any training data desired.

## Next Steps
* A next step that could be taken with this project is potentially pairing it with a mobile app so that photos can be taken by users and predictions can be made in real-time about the photos in question. The back end code is pretty much complete, so if the regression equation is exported and and paired with the front end code, a skin cancer detection app could be very possible.

## Authors

* **William Schmidt** - [Wil's LikedIn](https://www.linkedin.com/in/william-schmidt-152431168/)
* **Danial Khan** - [Danial's LikedIn](https://www.linkedin.com/in/danial-khan-98415b18b/), [Danial's GitHub](https://github.com/danialk1?tab=repositories)
* **Matthew Meer** - [Matt's LikedIn](https://www.linkedin.com/in/matthew-meer-8356b572/), [Matt's GitHub](https://github.com/meerkat1293?tab=repositories)
* **Awen Li** - [Awen's GitHub](https://github.com/BabyMochi)

## Acknowledgments

* Thank you to UC Davis and Major League Hacking for hosting this event!
  - [HackDavis 2020 Website](https://hackdavis2020.devpost.com/?ref_content=default&ref_feature=challenge&ref_medium=discover)
