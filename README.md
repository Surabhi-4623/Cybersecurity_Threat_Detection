# Cybersecurity_Threat_Detection
This project demonstrates the creation of a real-time threat detection platform for network security using Python, TensorFlow, Wireshark, and AWS for scalability. The platform analyzes network traffic, detects anomalies (potential threats), and alerts the user. The solution also incorporates machine learning to enhance detection accuracy.

<h3>Project Structure</h3>
<b>Data Preprocessing:</b><br/>
Using pyshark, network packet data is extracted and converted into features for machine learning.
The processed data is saved as a CSV file for training the model.
<br/>
<b>Model Training:</b>
<br/>
A simple neural network is built using TensorFlow.
The model is trained to classify network traffic as either normal or anomalous.
<b>AWS Integration:</b>
<br/>
Detected anomalies are logged and uploaded to an AWS S3 bucket for storage and monitoring.
<br/>
<b>Real-Time Detection:</b>
<br/>
The platform continuously monitors live network traffic, detects anomalies in real-time, and logs the results.

<h3>Data Preprocessing</h3>
Extracting Features from PCAP Files:
<br/>
The data is extracted from PCAP files using pyshark, which parses packet captures into structured data such as packet length, source and destination IPs, and transport layer protocols.
This data is then ready for training the machine learning model.

<h3>Model Training</h3>
A simple neural network model is trained using the preprocessed data. The model is built using TensorFlow and consists of two hidden layers with ReLU activation functions.
<br/>
Epoch 1/10 <br/>
200/200 [==============================] - 3s 15ms/step - loss: 0.6931 - accuracy: 0.4975 - val_loss: 0.6931 - val_accuracy: 0.5000<br/>
Epoch 2/10 <br/>
200/200 [==============================] - 2s 10ms/step - loss: 0.6824 - accuracy: 0.5200 - val_loss: 0.6811 - val_accuracy: 0.5400<br/>
...<br/>
Test Accuracy: 0.87
<br/>
The model achieves around 87% accuracy in classifying traffic as normal or anomalous.


<h3>AWS Integration</h3>
Once an anomaly is detected, the alert is uploaded to an AWS S3 bucket for storage. This integration allows for scalable monitoring and automated response handling.
<br/>
Uploading Alert Log to AWS S3:
<br/>
Uploading alert_log.txt to S3 bucket...<br/>
File uploaded successfully to s3://cybersecurity-bucket/logs/alert_log.txt


<h3>Real-Time Detection</h3>
The platform can monitor live network traffic using pyshark.LiveCapture and predict anomalies in real-time.<br/>
Threat detected: TCP at 1672539371.54 <br/>
Threat detected: UDP at 1672539382.30
