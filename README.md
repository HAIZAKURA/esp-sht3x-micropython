# esp-sht3x-micropython
[![Author](https://img.shields.io/badge/Author-HAIZAKURA-b68469?style=flat-square)](https://nya.run)

[![License](https://img.shields.io/github/license/HAIZAKURA/esp-sht3x-micropython?style=flat-square)](./LICENSE)

A SHT3x (SHT30/31/35) Lib for esp8266/esp32 with MicroPython.

If you are using pyboard or another board, please modify the usage of `Pin` and `I2C` in `sht3x.py` .

## Usage

```python
from sht3x import SHT3x_Sensor

sht3x_sensor = SHT3x_Sensor(freq = 100000, sdapin=5, sclpin=4)
measure_data = sht3x_sensor.read_temp_humd()
# measure_data = [22.9759, 73.8277]
# The default decimal place is 4 digits
temp = measure_data[0]
humd = measure_data[1]

print('Temp:', temp)
# Temp: 22.9759
print('Humd:', humd)
# Humd: 73.8277
```

## Notice

The default temperature is Celsius. If you need Fahrenheit, please change it in `sht3x.py` .

Just uncomment the following code.

```python
# temperature = (315.0 * float(temperature_raw) / 65535.0) - 49
```

And comment the following code.

```python
temperature = (175.0 * float(temperature_raw) / 65535.0) - 45
```

The `build/sh3x.mpy` is a compiled bytecode file, and **only can be used in `MicroPython v1.12+` **.

## Author

**esp-sht3x-micropython** © [HAIZAKURA](https://nya.run), Released under the [MIT](./LICENSE) License.

> [Personal Website](https://nya.run) · GitHub [@HAIZAKURA](https://github.com/HAIZAKURA) · Twitter [@haizakura_0v0](https://twitter.com/haizakura_0v0) · Telegram [@haizakura](https://t.me/haizakura)