# DHT11 Python library - Odroid C1+

This simple class can be used for reading temperature and humidity values from DHT11 sensor on Odroid C1+.

```
I modified https://github.com/szazo/DHT11_Python/tree/master/dht11
```

# Installation

To install, just run following:

```
pip install odroid-wiringpi
python3 setup.py install
```

# Usage

1. Instantiate the `DHT11` class with the pin number as constructor parameter.
2. Call `read()` method, which will return `DHT11Result` object with actual values and error code.

For example:

```python
import odroid_wiringpi as wpi
import odroid_dht11 as dht11

wpi.wiringPiSetup()

# read data using pin 7
instance = dht11.DHT11(pin = 7)
result = instance.read()

if result.is_valid():
    print("Temperature: %-2d C" % result.temperature)
    print("Humidity: %-2d %%" % result.humidity)
else:
    print("Error: %d" % result.error_code)
```

For working example, see `test.py` (you probably need to adjust pin for your configuration)

# License

This project is licensed under the terms of the MIT license.
