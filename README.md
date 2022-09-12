# iCU-Burglar-Detector

A burglar behavior detector using Openpose, Python and LSTM, a vision based approach excluding additional sensors that uses a pre-trained pose based feature extracting model. A skeleton based approach to determine human burglar behavioral patterns by utilizing time series sequences from data acquired from live surveillance captured from IP cameras by using RTSP. This application is designed for the age of mobiles targeting mobile applications and mobile devices.  Integrated with Firebase Cloud Messaging in order to send notifications to the client (android/IOS/web application)

![image](https://user-images.githubusercontent.com/32609286/189542758-c6028169-d4eb-4ddc-9cf4-95c06d6e8c17.png)

# Functionality

1. Manage recorded and saved burglar footage - The burglar event details detected will be stored in the database and a 10-12 second clip of 
the surveillance is stored for evidential evidence of the burglar occurrence. 
2. Push notification alert - Upon loosing connection to a camera or upon detecting suspicious behavior an immediate notification is sent to the client.
3. User login and registration
4. Enable burglar detection on IP camera as and when required - This allows the user to just view the live surveillance instead of arming the camera at all times.
4. Manage emergency contacts - The user has the ability add their closest contacts into the application so that the user can contact them via the application directly.

# Burglar behavior classes

1. Break down door with hammer.
2. Break down door with shoulder
3. Kick door open.
4. Picklock door
5. Jump in through window
6. Pry open door with a lever

# Architecture

![image](https://user-images.githubusercontent.com/32609286/189542580-5b83d7b1-1a1e-401b-a317-ef8d01e0d017.png)

The presentation layer is the android application which is developed using android jetpack for UI simplicity, libVLC in order to play real-time videos 
transmitted over the RTSP protocol and firebase has been integrated to receive push notifications.

The business layer is a centralized hub which has the bulk of the application business logic. This is implemented in Google colaboratory and the server is built 
using python, flask and Ngrok to open a tunnel in order to connect to the server hosted in a remote cloud machine. Tensorflow is used to load the trained model to make predictions on the surveillance acquired. Google drive is used as the file storage location of the surveillance footage.

_PS: You will have to change the folder paths accordingly run this_
