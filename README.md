# Scene Reconstruction for Edge using Metadata (AMQP Implementation)

**IMPORTANT : Due to organization policy, source code cannot be shared. The basic idea can be obtained from respective README.md files.**

## Objective
Reconstruction or Approximation of environment from edge data. Using pre-trained models, we are analyzing the incoming edge data (CCTV camera footage) and extracting the detected objects and person's pose. These metadata are sent to remote server, where using these metadata, the video scene is reconstructed or approximated on a Real-time manner.

## Installation of Necessary Libraries/Packages

There are two different implementations of the system using two different communication protocols. They are as follows,
- Message Queuing Telemetry Transport (MQTT)
- Asymmetric Message Queuing Protocol (AMQP)

Find the respective source codes in respective branches. The necessary libraries and/or packages for AMQP are mentioned in the respective `requirements.txt` files. Use the command below to install necessary dependencies.

```
pip install -r requirements.txt
```

### Regarding AMQP Implementation

For running the system, RabbitMQ has been used. RabbitMQ is the AMQP implementation on AWS platform. Create a RabbitMQ broker on AWS and note down the Queue id and other necessary attributes which is/are to be defined in the code.

## Running the System

- Clone the Repository using the command below.
- Switch to the `amqp-rmq` branch.
- Check whether the RabbitMQ Broker on AWS is running or not. If not, create a new one. Check if the `main.py` is updated with proper credentials or not. 
- Open two different Command Prompts.
- On one prompt, run the Publisher.
- On the other prompt, run the Subscriber.

## Constraints and Future Improvements

- The system is only limited to Single person pose estimation
- Object detection using YOLO-v3 is quite slow and sometimes inconsistent
- The Image superposition only works if the object is fully inside the frame (Camera's field of view)