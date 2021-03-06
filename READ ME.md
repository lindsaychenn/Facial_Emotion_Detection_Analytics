# Objective:

This project focuses on analyzing video data to perform facial recognition and understand human emotions in the retail space.We intend to create an intelligent prototype for companies to identify their customers’ emotions in real-time and optimize staffing using automated email alerts to the store manager in case of the queue at the billing counter.   
We used Python to record live video, Intel HAAR Cascades for facial detection and Loggly to ingest, process and build business intelligence dashboard on the video streaming data. All the camera-detected data are finally passed to MySQL database to created a repository for future use by other business purposes.
The use cases are diverse, from A/B testing on promotion effect to security check in the crowd. By changing the pre-trained machine learning models, corporates can customize this process for there own needs.

# File Introduction
    1. The folder named "age_gender_models" contains pre-trained ML models to identify two features - gender, age
    2. "facial_expression_model_structure.json": for face expression recognizer initialization
    3. "facial_expression_model_weights.h5" : to load the weights
    4. "haarcascade_frontalface_default.xml": for face detection
    5. "webcam_cv3.py": pipeline script to connect the whole working flow
    6. "save_db.py": script to upload log data into Loggly to analyze
    7. "webcam.log": saved log data

# Operation steps
## 1. Python Modules to install 
    OpenCV: I installed the OpenCV3 on my MAC throught the command "conda install --channel https://conda.anaconda.org/menpo opencv3"

## 2. Run webcam_cv3.py on terminal using: 
    "python webcam_cv3.py"
    *make sure all the files are saved under one folder and their paths are specified correctly
    *need to fill-in with your own customer Loggly token by replacing all the "<customer_token>" in following command with yours
    *"r = requests.post('https://logs-01.loggly.com/inputs/<customer_token>/tag/python', json=temp_json_face_no)"

## 3. Run save_db.py to save log
    "python save_db.py"

## 4. Requires a Loggly.com's account, you can use the free trial to test the code. 
    Need to mention that each part of our process is free except for the loggly account.

## 5. automate e-mail alert setting is through Loggly.com. You can customize your own.

## 6. You can modify the pre-trained ML models to serve your own purpose.


