This project aims to analyze the engagement levels of students during classroom lectures by processing video footage. By utilizing advanced computer vision techniques, we determine the concentration levels of students based on their facial emotions and head poses.

FILENAMES:

MTCNN_HEAD : Final File which have loaded models and also gives the analysis of the frames of the lecture
Head_pose_AFLW : Developing of Head Pose Estimation model
RAFDB : Developing of Facial Emotion Recognition Model

𝐏𝐫𝐨𝐜𝐞𝐬𝐬 𝐎𝐯𝐞𝐫𝐯𝐢𝐞𝐰:

  1)𝑽𝒊𝒅𝒆𝒐 𝑭𝒓𝒂𝒎𝒆 𝑬𝒙𝒕𝒓𝒂𝒄𝒕𝒊𝒐𝒏:

The classroom lecture video is divided into individual frames by using OpenCV Techniques.

  2)𝑭𝒂𝒄𝒆 𝑫𝒆𝒕𝒆𝒄𝒕𝒊𝒐𝒏 𝑼𝒔𝒊𝒏𝒈 𝑴𝑻𝑪𝑵𝑵:

Each frame is processed using the MTCNN library to detect faces.
The detected faces are then cropped using the coordinates provided by MTCNN.

  3)𝑭𝒂𝒄𝒊𝒂𝒍 𝑬𝒎𝒐𝒕𝒊𝒐𝒏 𝑹𝒆𝒄𝒐𝒈𝒏𝒊𝒕𝒊𝒐𝒏:

The cropped face images are passed through a Facial Emotion Recognition model based on the MaNet architecture.
This model classifies the facial emotion of each student in the frame.

  4)𝑯𝒆𝒂𝒅 𝑷𝒐𝒔𝒆 𝑬𝒔𝒕𝒊𝒎𝒂𝒕𝒊𝒐𝒏:

The cropped images are also passed through a Head Pose Estimation model.
Using the AFLW 2000 dataset, a Support Vector Regression (SVR) model was trained on the x, y, z coordinates of key facial landmarks (e.g., eyes, nose, lips) to determine the direction the student is looking.

  5)𝑪𝒐𝒏𝒄𝒆𝒏𝒕𝒓𝒂𝒕𝒊𝒐𝒏 𝑰𝒏𝒅𝒆𝒙 𝑪𝒂𝒍𝒄𝒖𝒍𝒂𝒕𝒊𝒐𝒏:

Each student's emotion and head pose are assigned a weight to calculate their concentration index.
The average concentration index of the entire class is computed for each frame and can be aggregated over the whole lecture.


𝘿𝙖𝙩𝙖𝙨𝙚𝙩𝙨 𝙐𝙨𝙚𝙙

  1)𝑭𝒂𝒄𝒊𝒂𝒍 𝑬𝒎𝒐𝒕𝒊𝒐𝒏 𝑹𝒆𝒄𝒐𝒈𝒏𝒊𝒕𝒊𝒐𝒏:

Model is trained using the RAFDB Dataset
Model architecture based on the MaNet research paper 
Dataset Link- https://www.kaggle.com/datasets/shuvoalok/raf-db-dataset
Paper Link - https://ieeexplore.ieee.org/document/9474949
Paper Name : Learning Deep Global Multi-Scale and Local Attention Features for Facial Expression Recognition in the Wild

  2)𝑯𝒆𝒂𝒅 𝑷𝒐𝒔𝒆 𝑬𝒔𝒕𝒊𝒎𝒂𝒕𝒊𝒐𝒏:

Model is trained using the AFLW 2000 Dataset
Key facial landmarks were used to capture x, y, z coordinates for training the SVR model.
Dataset Link- https://www.kaggle.com/datasets/mohamedadlyi/aflw2000-3d
