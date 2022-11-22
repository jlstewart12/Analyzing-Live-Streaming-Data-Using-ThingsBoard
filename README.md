# Analyzing Live Streaming Data Using ThingsBoard

## Project Structure
![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/24P11.png)
1. Navigate to the parent folder and run the ```docker-compose up``` comand.
2. Install the Paho MQTT Python client library locally by running ```pip install paho-mqtt``` in the terminal.
3. Inside of your home folder, create two folders named ```.mytb-data``` and ```.mytb-logs```.
4. The Project_MQTT folder should be in the same folder as the Project_Docker folder with the following setup.
![](https://github.com/jlstewart12/Analyzing-Live-Streaming-Data-Using-ThingsBoard/blob/main/images/24P13.png)
5. Values for temperature and humidity start appearing after running the ```TBPublish.py``` file in VS Code.
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