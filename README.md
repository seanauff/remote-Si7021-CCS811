# Archive notice

I don't use this anymore; instead using esphome. You can view my esphome configs here: https://github.com/seanauff/esphome-devices

# Air quality monitor

Use an ESP8266 to read Si7021 and CCS811 sensors and send data via MQTT in JSON format.

## Instructions

### Download code

#### Using Git

Clone the repo:

```shell
git clone https://github.com/seanauff/remote-Si7021-CCS811.git
```

#### Or download the zip

Click "Clone or download", "Download ZIP", and extract to folder of your choice.

### Create secrets file

Create a copy of the `secrets_example.h` file and name it `secrets.h`. Add your secrets to the newly created `secrets.h` file, keeping the double quotes:

* `SECRET_WIFI_SSID` SSID of the wireless network to connect to
* `SECRET_WIFI_PASSWORD` Wifi password, if needed
* `SECRET_MQTT_SERVER` IP Address of your MQTT broker

### Choose WiFi type

If using a WiFi network with no password, go to the `remote_Si7021_CCS811.ino` file and uncomment the line in the `setup_wifi()` function. Comment out the `WiFi.begin(WIFI_SSID, WIFI_PASSWORD);` line.

### Flash board

Upload the code to your board of choice.

### Verify it's working

Use the serial monitor to verify that the connection to WiFi and your MQTT broker is successful, and that sensor readings are being published.

### Connect to the MQTT broker with another client

An example telegraf config is provided.
