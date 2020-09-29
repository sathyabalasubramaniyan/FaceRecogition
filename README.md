# FaceRecogition
face recogition with opencv
FACE RECOGNITION
Face Recognition is basically the task of recognizing a person based on its facial image. 
There are different types of face recognition algorithms, for example:
   Eigenfaces 
   Fisherfaces 
   Local Binary Patterns Histograms (LBPH)  
   Scale Invariant Feature Transform (SIFT) 
   Speed Up Robust Features (SURF)
Eigenfaces face recognizer  
      
      This algorithm looks at all the training images of all datasets as a whole and tries to extract the components which are relevant and useful and discards the rest. These important features are called principal components.
      Eigenfaces are images that can be added to a mean (average) face to create new facial image.Eigenfaces are calculated by estimating the principal components of the dataset of facial images. EigenFaces algorithm takes illumination as an important feature. In consequence, lights and shadows are picked up by EigenFaces, which classifies them as representing a ‘face.'Its recognition rate decreases for recognition under varying pose and illumination. 
Fisherfaces face recognizer
        
       The fisherfaces facerecognizer  is aimed to solve the illumination problem by maximizing the ratio of between-class scatter to within-class scatter,Fisherfaces algorithm extracts principle components that separates one individual from another. So , now an individual's features can't dominate another person's features.
       By using Fisherfaces we can prevent features of an individual from being dominant but it still considers illumination an important feature. But we know that illumination is not an important feature as it's not even a part of face
 Local binary patterns histograms (LBPH) Face Recognizer
 ALGOIRTHM:
        
      1.Divide face images into R( for example R = 8 x 8 = 64 Regions) local regions to extract LBP histograms.
      2.The LBP histograms extracted from each sub-region are used for calculation and combined into a single, histogram with spatial advanced features
      3.The nearest-neighbor classifier is used to match the new image with the trained template
  It creates one histogram for each image  and stores them for recognition   
  LBP faces are not affected by changes in light conditions
IMPLEMENTATION:
 1.Import Required Modules:
     import cv2: is OpenCV module for Python which we will use for face detection and face recognition.
     import os: We will use this Python module to read our training directories and file names.
     import numpy: We will use this module to convert Python lists to numpy arrays as OpenCV face recognizers accept numpy arrays
 2.Preparing Data:
      Multiple images were trained  and a dataset was created with the web cam itself and an ID was assigned to each user.Here ,I have used images of few of my favorite characters in THE VAMPIRE DIARIES(TVD) and trained them
 3.Labelling the prepared data
   OpenCV face recognizer accepts information in a particular format. In fact, it receives two vectors:
      One is the faces of all the people.
      The second is the integer labels for each face.
 4.Training the prepared data:
     Creating LBPH model and training it with the prepared data
       model = cv2.face.createLBPHFaceRecognizer()
       model.train(faces, np.array(labels))
  5.Testing the model:
       take one test image of each person, use face detection and test the model.
