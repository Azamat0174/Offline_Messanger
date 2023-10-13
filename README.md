# 📬 Offline_Messenger

**Offline_Messenger** offers a unique solution for messaging through the use of MQTT, ensuring seamless communication even offline! 🚀

## 📖 Table of Contents

- [Mosquitto MQTT Setup Guide](#mosquitto-mqtt-setup-guide)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Managing the Broker](#managing-the-broker)
  - [Testing Locally](#testing-locally)
  - [External Devices Setup](#external-devices-setup)
  
## 📡 Mosquitto MQTT Setup Guide

This guide simplifies the process of setting up the Mosquitto MQTT broker on a Linux-based system. Given MQTT's nimbleness, it's a top choice for IoT and a myriad of other applications.

### 📋 Prerequisites

Before we dive in, make sure you're equipped with:

- 🐧 A Linux-based OS (e.g., Ubuntu, Debian, Kali).
- 🔑 Administrative privileges (sudo or root access).
- 🌐 Active internet connection.

### 🛠 Installation

#### **Step 1: Installing the Mosquitto Broker**

1. **Update Your Package Repository**:
   ```bash
   sudo apt update

Install Mosquitto & Its Companions:
sudo apt install mosquitto mosquitto-clients

Verify the installation:
mosquitto --version

🎛 Managing the Broker

Commands to be the master of your Mosquitto broker!
sudo systemctl start mosquitto
sudo systemctl stop mosquitto
sudo systemctl restart mosquitto

!!! Another important note if you are running it in you localhost use the following

🖥 Testing Locally

Engage in a quick conversation with your broker:
Publish a message:
mosquitto_pub -h localhost -t "test/topic" -m "Hello, MQTT!"

Subscribe to the topic:
mosquitto_sub -h localhost -t "test/topic"
You should see the published message in the subscriber's terminal.

Check the broker's status:

To ensure the broker is running, use the following command:
sudo systemctl status mosquitto


!!!In case if you want to use it with another device your pc can be as server and you need to modify the /etc/mosquitto/mosquitto.conf file

🌍 External Devices Setup

Want to chat with distant devices? Here's how:

Adjust /etc/mosquitto/mosquitto.conf with:

# General Configuration
...

# MQTT Protocol & Port
listener 1883 <YOUR_IP_ADDRESS>

...

# Security Settings
allow_anonymous true



🔥 Remember: Post-edit, rekindle Mosquitto's spirit and replace localhost with your special <YOUR_IP>.


