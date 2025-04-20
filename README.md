# Robot Status MQTT

This project demonstrates an MQTT-based system for publishing and subscribing to robot status updates. The script connects to an MQTT broker and sends/receives messages to update and monitor the robot's current state.

## Features

- **MQTT Client**: Connects to an MQTT broker to send and receive messages.
- **Robot Status**: Publishes updates on the robot's status (e.g., battery level, health) and subscribes to status updates from other systems.
- **Real-Time Communication**: The robot can send real-time status updates and receive commands from other systems using MQTT.

## Prerequisites

To run this script, you need the following:

1. Install Python 3.8 or higher.
2. Install the required dependencies by using `pip`:
    ```bash
    pip install paho-mqtt
    ```

3. Ensure that you have an MQTT broker running (e.g., Mosquitto). You can use a public broker like `test.mosquitto.org` or set up your own.

## Setup Instructions

1. **Clone the repository**:
    ```bash
    git clone https://github.com/Techboy-lab2025/robot_status_mqtt.git
    cd robot_status_mqtt
    ```

2. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the script**:
    ```bash
    python robot_status_mqtt.py
    ```

This will start the MQTT client, which will begin subscribing to and publishing robot status updates.

## MQTT Topics

The script interacts with the following MQTT topics:

- `robot/status`: This topic is used for publishing the robot's status updates, such as battery level or operational status.
- `robot/command`: This topic listens for commands from other systems (e.g., other robots or control systems).

### Example Payload for Status Update

You can publish a status update in the following format:

```json
{
  "status": "operational",
  "battery_level": 95
}
