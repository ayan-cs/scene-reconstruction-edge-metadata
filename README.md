# Scene Reconstruction for Edge using Metadata (MQTT Implementation)

**IMPORTANT : Due to Organization Policy, Source Code cannot be shared The basic idea can be obtained from respective `README.md` files**

## Objective
Reconstruction or Approximation of environment from edge data. Using pre-trained models, we are analyzing the incoming edge data (CCTV camera footage) and extracting the detected objects and person's pose. These metadata are sent to remote server, where using these metadata, the video scene is reconstructed or approximated on a Real-time manner.

## Installation of Necessary Libraries/Packages

There are two different implementations of the system using two different communication protocols. They are as follows,
- Message Queuing Telemetry Transport (MQTT)
- Asymmetric Message Queuing Protocol (AMQP)

Find the respective source codes in respective branches. The necessary libraries and/or packages for MQTT are mentioned in the respective `requirements.txt` files. Use the command below to install necessary dependencies.

```
pip install -r requirements.txt
```

### Additional Requirements for MQTT

You need to install the MQTT broker from [Mosquitto](https://mosquitto.org/download/) or if you have Docker installed on your machine, then you can easily run the Dockerized Mosquitto which will act as your broker. The code does not required to be changed for any of these.

## Running the System

- Clone the Repository
- Switch to the necessary branch with respect to the protocol
- Start running the broker
- Open two different Command Prompts
- On one prompt, run the Publisher
- On the other prompt, run the Subscriber 

## Constraints and Future Improvements

- The system is only limited to Single person pose estimation
- Object detection using YOLO-v3 is quite slow and sometimes inconsistent
- The Image superposition only works if the object is fully inside the frame (Camera's field of view)