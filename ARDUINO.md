# How to read pressure and temperature with Arduino
We use the following sensors to readut Pressure, Temperature and Relative Humidity
- Pressure : three analog differential pressure sensors by Festo, model PTE-P10R-S6-B-2.5K
  https://ftp.festo.com/public/PNEUMATIC/SOFTWARE_SERVICE/DataSheet/IT_IT/571480.pdf
  each one measures the pressure difference between gas inside one MDT chamber and atmosphere
- Temperature and Relative Humidity : one digital DHT22 sensor (AM2302 type)
  ( see https://www.kandrsmith.org/RJS/Misc/Hygrometers/calib_many.html for more info)

Both are readout with one Arduino Uno board, using the Arduino Sketch in

~/arduino/sketch_read_pressure

The bord dumps the readings to the computer through a serial port every 2 seconds

To see the readings open a terminal and execute the script:

students@mdtlabnucl:~$ source arduino/Arduino_reader.sh

you will see rows with 6 values, with a new row appearing every 2 sec, e.g.:

1244	2.32	1.03	1.84	19.40	59.80	

1246	2.31	1.03	1.83	19.40	59.90	

1248	2.32	1.03	1.83	19.40	59.90	

The meaning of the 6 values is:
-  1: time in seconds from the last reset of the Arduino board
-  2,3,4: absolute pressure in bar (1.00 = atmosferic pressure)
-  5: temperature in C
-  6: relative humidity in % 
 




