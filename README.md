## Mosquitto
* MQTT: Message Queuing Telemetry Transport used to handle sensor data
* MQTT protocol (implemented by
Mosquitto ): Designed as an extremely lightweight publish/subscribe messaging
transport, it is useful for connections with remote locations where a small code footprint is required and/or network
bandwidth is at a premium.
* MQTT Broker is responsible for receiving network connections from the client and handling the client’s requests of
Subscribe/Unsubscribe and Publish, as well as forwarding the messages published by the client to other subscribers.
![](/images/mqtt.png)

<a href="https://randomnerdtutorials.com/what-is-mqtt-and-how-it-works/">Image Source</a>

## ThingsBoard
An "open source platform that allows for the development, implementation, and testing of input
and output data from IoT devices." 
<a href="https://thingsboard.io/">thingsboard.io</a> 

### Key Features
- Device management
- Data collection
- Processing and Visualization for IoT
### Components
- Devices
- Assets
- Rule Engine
- Root Rule Chain

## Installation

<details><summary>Project_Docker folder</summary>

<p align="center">

  <img src="images/24P11.png">

</p>

</details>

1. Run the ```docker-compose up``` command from within the parent folder.
2. Install the Paho MQTT Python client library locally by running ```pip install paho-mqtt``` in the terminal.
3. Inside of your home folder, create two folders named ```.mytb-data``` and ```.mytb-logs```.

<details><summary>Project_MQTT folder within Project_Docker folder</summary>
<p align="center">

<img src="images/24P13.png">

</p>

</details>

5. Values for temperature and humidity will start appearing after running the ```TBPublish.py``` file in VS Code.
    ```
    Temperature: 25 humidity: 95
    Temperature: 81 humidity: 58
    Temperature: 39 humidity: 69
    Temperature: 30 humidity: 54
    Temperature: 50 humidity: 71
    Temperature: 70 humidity: 92
    Temperature: 98 humidity: 54
    ```
6. In a browser window, navigate to http://localhost:8080/. Log in to ThingsBoard using the default tenant administrator account:
    ```
    Login: tenant@thingsboard.org
    Password: tenant
    ```
    ![](/images/TBpage.png)
7. Open the ```DHT11 Demo Device``` by selecting it from the menu on the left. Navigate to the Latest Telemetry tab to see the latest telemetry.
    ![](/images/latest_telemetry.png)
8.  Create a project in Firebase then add a field in the database titled ```temperature``` and initialize the corresponding field to zero.
9. Create a ```Firebase node```, connect it to a ```Message Type Switch``` node, and add ```Post telemetry``` as the link label.
    ![](/images/nodes.png)
10. Realtime database updates will appear in ThingsBoard and publish temperature and humidity data.
    ![](/images/realtime_db.png)
## Rule Chains
Sending information about the streaming MQTT data that is above a certain threshold to Firebase.

### CreateAndClearAlarm

![](/images/CreateAndClearAlarms.png)

### TempToFirebase

![](/images/TempToFirebase.png)

### AlarmToFirebase and TempToFirebase connection

![](/images/NodeConnections.png)

### SaveTimeseries and CreateAndClearAlarm connection

![](/images/SaveTimeseriesAndCreateAndClearAlarm.png)


## Firebase
* ```alarm``` field publishes the live streaming data from the CreateAndClearAlarm rule chain.
* ```temperature``` field publishes temperature and humidity data.
