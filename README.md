# Raspberry PI RFID Reader and MQTT Broker Bundle

## 1. Problem  
Establish communication between Raspberry Pi and Mobile devices.

## 2. Solution
I have used MQTT protocol which is designed for IoT applications and Machine-to- Machine (M2M) connectivities.

Raspberry Pi takes places as a Server and Broker in this implementation.

## 3. Implementation
### 3.1. MQTT

MQTT stands for MQ Telemetry Transport. It is a publish/subscribe, extremely simple and lightweight messaging protocol, designed for constrained devices and low-bandwidth, high-latency or unreliable networks. The design principles are to minimise network bandwidth and device resource requirements whilst also attempting to ensure reliability and some degree of assurance of delivery. These principles also turn out to make the protocol ideal of the emerging “machine-to-machine” (M2M) or “Internet of Things” world of connected devices, and for mobile applications where bandwidth and battery power are at a premium.

### 3.2. Raspberry PI
In this Project i have used MFRC522 to get data from RFID Cards or tags.  

MFRC522 Chip is reading data with python and send them to the MQTT Broker with a specific topic, then any MQTT Client can Subscribe the topic and read data. Client can be in local area network or anywhere connected on internet. (Port 1883 must be set open in router)  

- **Read.py**  
Reads UIDs from RFID Cards and prints them on console. It imports MFRC522 file for chip settings.
- **Write.py**  
 Write UIDs to RFID Cards
- **Mqtt.py**  
It contains required python codes to send data to mqtt broker. It uses paho.mqtt library.
- **Ip.py**  
It connects to 8.8.8.8:80 and get local ip from socket. It is required for MQTT Broker which is connected to internet.
- **Deploy.py**   
It combines python files above in a single file. It is ready to deploy.