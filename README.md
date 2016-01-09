Arctic-2014-thermal
===================
For the Eagle files, they are made with Eagle 6.5 FREE. The parts can all be purchased 
from sparkfun except the MLX90614-ACC.

https://www.sparkfun.com/wish_lists/73940

IR Sensor: 35deg FOV
http://www.futureelectronics.com/en/technologies/semiconductors/analog/sensors/temperature/Pages/7012690-MLX90614ESF-ACC-000-TU.aspx?IM=0

IR Sensor: 10deg FOV
http://www.futureelectronics.com/en/technologies/semiconductors/analog/sensors/temperature/Pages/4099248-MLX90614ESF-ACF-000-TU.aspx?IM=0


The code that runs on Whistler is in the code directoy under the "whistler_option" folder. There is also python code that does some of the pre-processing of the data, and splits the data files up. This code is incomplete however and dose not fully process the data. 

I attempted to speed up the code by running a different digital write library, but that did not change much. Instead of running the different library (which is mostly stable and seems fine) the serial speed was changed from 9600 baud to 57600 baud. This took the loop time from ~20ms to ~3ms. As a happy medium an interval of 5ms was added to ensure a constant data collection rate. This rate will vary between 5ms and 6ms, with an average around 5.1ms (the 6ms is due to the occasional loop that takes slightly longer to run.) It might be possible to get the delay down below the 3ms range with the digitalWriteFast library, but there is no real need for that at this point.
