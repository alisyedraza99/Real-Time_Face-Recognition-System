# Real-Time_Face-Recognition-System
Read more about this project and learn about the theory and thinking process behind it in [my blog on Medium](https://medium.com/@alisyedraza99/heres-how-i-developed-a-real-time-face-recognition-system-96231eb634d4).
## The Steps
This project has four major steps:
1. Create the dataset
2. Prep the dataset using MTCNN
3. Using a FaceNet model to generate face emeddings for each training example
4. Passing our data through a custom SVM to make predictions
If you want to detect the faces in a videostream in real-time, then you should take a look at [this file](https://github.com/alisyedraza99/Real-Time_Face-Recognition-System/edit/master/src/real_time_face_rec.py).
 
 ### Step 1: Prepping the dataset
 Your dataset directory should have two folders, a train and a validation. In those directories you should have
 a subdirectory for each person you want to detect. Take a look at the [dataset]() I have included in this repo for
 reference. This dataset is the [5 celebrity faces](https://www.kaggle.com/dansbecker/5-celebrity-faces-dataset) dataset from Kaggle. Note, I did not train this model on this dataset.
 I used a custom dataset with images of my firends which I have not included here for privacy reasons. 
 
 ### Step 2: Using MTCNN
 Next, you should run [friends_dataprep.py](https://github.com/alisyedraza99/Real-Time_Face-Recognition-System/edit/master/src/friends_dataprep.py). I developed this script to run MTCNN on every image in the dataset being used. It 
 creates a tensor (numpy array) containing the face pixels in each image and save it as an .npz file.
 
 ### Step 3: Using FaceNet
 Use [facenet.py](https://github.com/alisyedraza99/Real-Time_Face-Recognition-System/edit/master/src/facenet.py) to generate face embeddings and make a new .npz file of the new np array
 
 ### Step 4: SVM
 Train an [SVMclassifier.py](https://github.com/alisyedraza99/Real-Time_Face-Recognition-System/edit/master/src/SVMclassifier.py) using the
 numpy array to classify the faces.
 
 ### Bonus: Make It Real-Time
 Take a look at [this script](https://github.com/alisyedraza99/Real-Time_Face-Recognition-System/edit/master/src/real_time_face_rec.py)
