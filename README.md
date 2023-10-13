# Offline_Messanger
This project is mage by using mqtt to develop offline messanger

In order to test this project you need to have the following.

# Mosquitto MQTT Setup Guide

This guide will walk you through the process of setting up the Mosquitto MQTT broker on a Linux-based system. MQTT is a lightweight and efficient protocol for message communication, making it ideal for IoT and other applications.

## Prerequisites

Before you begin, ensure you have the following:

- A Linux-based operating system (e.g., Ubuntu, Debian, Kali, etc.)
- Administrative privileges (sudo or root access)
- An internet connection to download packages

## Installation

### Step 1: Install Mosquitto Broker

1. Update your package repository:

   ```bash
   sudo apt update
Install the Mosquitto broker and clients:
sudo apt install mosquitto mosquitto-clients

Verify the installation:
mosquitto --version

Step 2: Start the Mosquitto Broker
sudo systemctl start mosquitto
sudo systemctl stop mosquitto
sudo systemctl restart mosquitto

!!! Another important note if you are running it in you localhost use the following

Test the Broker:
Publish a message:
mosquitto_pub -h localhost -t "test/topic" -m "Hello, MQTT!"

Subscribe to the topic:
mosquitto_sub -h localhost -t "test/topic"
You should see the published message in the subscriber's terminal.

Check the broker's status:

To ensure the broker is running, use the following command:
sudo systemctl status mosquitto


!!!In case if you want to use it with another device your pc can be as server and you need to modify the /etc/mosquitto/mosquitto.conf file

# =================================================================
# General configuration
# =================================================================

# Uncomment to run as a background service
# daemon

# Log destination
log_dest file /var/log/mosquitto/mosquitto.log

# Log level
log_type all

# =================================================================
# MQTT protocol and port
# =================================================================

# Default listener
listener 1883 <YOUR_IP_ADDRESS>
# If you want to bind to all interfaces, you can use
# listener 1883

# Uncomment to enable MQTT over WebSockets
# listener 9001
# protocol websockets

# =================================================================
# Security settings
# =================================================================

# Allow anonymous connections
allow_anonymous true


Do not to forgot to restart the mosquitto and replace the localhost with <YOUR_IP>



