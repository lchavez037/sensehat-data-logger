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

```python FILENAME``` is used to give the CSV file a name. Name is given within the main program of the script.
```python WRITE_FREQUENCY``` is used to indicate how many logs to store until writing to the CSV file.
```python TEMP``` is used to append ```python get_temperature()``` in Celsius into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python TEMP_H``` is used to append ```python get_temperature_from_humidity()``` from the humidity sensor in Celsius into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python TEMP_P``` is used to append ```python get_temperature_from_pressure()``` from the pressure sensor in Celsius into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python HUMIDITY``` is used to append ```python get_humidity()``` in percentage of relative humidity into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python PRESSURE``` is used to append ```python get_pressure()``` in Millibars of pressure into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python ORIENTATION``` is used to append ```python get_orientation()``` to get the pitch, roll, and yaw in degrees into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python ACCELERATION``` is used to append ```python get_accelerometer_raw()``` to get the raw x, y and z axis accelerometer data into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python MAG``` is used to append ```python get_compass_raw()``` to get the raw x, y and z axis magnetometer data into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python GYRO``` is used to append ```python get_gyroscope_raw()``` to get the raw x, y and z axis gyroscope data into the CSV file if set to ```python True```. Deactivate by setting to ```python False```
```python DELAY``` is used to indicate how many seconds to pause between recording of logs.

