# Analyzing Live Streaming Data Using ThingsBoard

## Installation
![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/24P11.png)
1. Run the ```docker-compose up``` command from within the parent folder.
2. Install the Paho MQTT Python client library locally by running ```pip install paho-mqtt``` in the terminal.
3. Inside of your home folder, create two folders named ```.mytb-data``` and ```.mytb-logs```.
4. The Project_MQTT folder should be in the same folder as the Project_Docker folder with the following setup.
![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/24P13.png)
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
    ![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/TBpage.png)
7. Open the DHT11 Demo Device by selecting it from the menu on the left. Navigate to the Latest Telemetry tab to see the latest telemetry.
    ![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/latest_telemetry.png)
8.  Create a project in Firebase then add a field in the database titled ```temperature``` and initialized the corresponding field to zero.
9. Created a ```Firebase node```, connected it to a ```Message Type Switch``` node, and added ```Post telemetry``` as the link label.
    ![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/nodes.png)
10. Realtime database updates will appear in ThingsBoard and publish temperature and humidity data.
    ![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/realtime_db.png)