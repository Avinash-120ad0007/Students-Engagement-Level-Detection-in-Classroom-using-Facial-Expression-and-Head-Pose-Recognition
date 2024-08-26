This project aims to analyze the engagement levels of students during classroom lectures by processing video footage. By utilizing advanced computer vision techniques, we determine the concentration levels of students based on their facial emotions and head poses.

𝐏𝐫𝐨𝐜𝐞𝐬𝐬 𝐎𝐯𝐞𝐫𝐯𝐢𝐞𝐰:

𝑽𝒊𝒅𝒆𝒐 𝑭𝒓𝒂𝒎𝒆 𝑬𝒙𝒕𝒓𝒂𝒄𝒕𝒊𝒐𝒏:

The classroom lecture video is divided into individual frames.
Face Detection Using MTCNN:

Each frame is processed using the MTCNN library to detect faces.
The detected faces are then cropped using the coordinates provided by MTCNN.
Facial Emotion Recognition:

The cropped face images are passed through a Facial Emotion Recognition model based on the Manet architecture.
This model classifies the facial emotion of each student in the frame.
Head Pose Estimation:

The cropped images are also passed through a Head Pose Estimation model.
Using the AFLW 2000 dataset, a Support Vector Regression (SVR) model was trained on the x, y, z coordinates of key facial landmarks (e.g., eyes, nose, lips) to determine the direction the student is looking.
Concentration Index Calculation:

Each student's emotion and head pose are assigned a weight to calculate their concentration index.
The average concentration index of the entire class is computed for each frame and can be aggregated over the whole lecture.
Datasets Used
Facial Emotion Recognition:

Model trained using the RAFDB Dataset Dataset Link.
Model architecture based on the Manet research paper Paper Link.
Head Pose Estimation:

Model trained using the AFLW 2000 Dataset Dataset Link.
Key facial landmarks were used to capture x, y, z coordinates for training the SVR model.
