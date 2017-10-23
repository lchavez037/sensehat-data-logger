# Raspberry Pi SenseHat Data Logger

Python script for the [Raspberry Pi](https://www.raspberrypi.org/) [Sense Hat](https://www.raspberrypi.org/products/sense-hat/) to log data from the various sensor avialable from the add-on board. Outputs a CSV file with headers and time stamps.

## Hardware:

Tested with a [Raspberry Pi 2](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/) and [Raspberry Pi 3](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/).

[Sense Hat](https://www.raspberrypi.org/products/sense-hat/) add-on board for Raspberry Pi.

## Set Up

Install the Sense Hat package using the following command in the terminal:

`sudo apt-get install sense-hat`

## Python Script

The following imports are used:

```python
from datetime import datetime
from sense_hat import SenseHat
from time import sleep
from threading import Thread
```

By changing the following variables you are able to control the type of data you are collecting and how often to collect.

```python
FILENAME = ""
WRITE_FREQUENCY = 2
TEMP = True
TEMP_H=True
TEMP_P=True
HUMIDITY=True
PRESSURE=True
ORIENTATION=True
ACCELERATION=True
MAG=True
GYRO=True
DELAY=5
```

**FILENAME** is used to give the CSV file a name. Name is given within the main program of the script.

**WRITE_FREQUENCY** is used to indicate how many logs to store until writing to the CSV file.

**TEMP** is used to append **get_temperature()** in Celsius into the CSV file if set to **True**. Deactivate by setting to **False**.

**TEMP_H** is used to append **get_temperature_from_humidity()** from the humidity sensor in Celsius into the CSV file if set to **True**. Deactivate by setting to **False**.

**TEMP_P** is used to append **get_temperature_from_pressure()** from the pressure sensor in Celsius into the CSV file if set to **True**. Deactivate by setting to **False**.

**HUMIDITY** is used to append **get_humidity()** in percentage of relative humidity into the CSV file if set to **True**. Deactivate by setting to **False**.

**PRESSURE** is used to append **get_pressure()** in Millibars of pressure into the CSV file if set to **True**. Deactivate by setting to **False**.

**ORIENTATION** is used to append **get_orientation()** to get the pitch, roll, and yaw in degrees into the CSV file if set to **True**. Deactivate by setting to **False**.

**ACCELERATION** is used to append **get_accelerometer_raw()** to get the raw x, y and z axis accelerometer data into the CSV file if set to **True**. Deactivate by setting to **False**.

**MAG** is used to append **get_compass_raw()** to get the raw x, y and z axis magnetometer data into the CSV file if set to **True**. Deactivate by setting to **False**.

**GYRO** is used to append **get_gyroscope_raw()** to get the raw x, y and z axis gyroscope data into the CSV file if set to **True**. Deactivate by setting to **False**.

**DELAY** is used to indicate how many seconds to pause between recording of logs.

