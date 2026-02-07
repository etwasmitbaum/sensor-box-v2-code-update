# My Sensor Box V2 Software Updates

Original version see [here](https://www.printables.com/model/1079858-3d-printer-emission-sensor-array-sensorbox-v2) for more info.

My own Sensorbox with merged code of these repositories:
https://github.com/turgu1/sensor-box-v2-code-update
https://www.printables.com/model/1436008-3d-printer-emission-sensor-array-sensorbox-v2-code

### Code versions

There are now three versions of the software available here:

- The Standalone Version (`sensor-box standalone.yaml`)
- The Home Assistant Version (`sensor-box ha.yaml`)
- The MQTT Version (`sensor-box mqtt.yaml`)

Please note that the MQTT Version is not ready yet. 

## (2025-02-17)

### Code cleanup

The lambda functions have been reformatted to be in line with C / C++ usage

### Button clicks management and Pages selection

A new click has been added to permit page selection. There are now 4 click durations:
Brightness = 1ms - 490ms
Switching pages = 500ms - 2000ms
Wifi toggle = 2200ms - 5000ms
Saving baseline = 5100ms - 7500ms

### Added Pressure of bmp280

The bmp280 pressure sensor has been added on the top line of the first page.

### Graphics support

To permit proper access to the temperature and humidity sensors by the graph add-on, two template sensors have been added. The lambda producing those sensors' state are now responsible for selecting the first sensor that returns a valid value. The first page is now using those sensors to display the current temperature and level of relative humidity.

### secrets.yaml

Added `secrets.yaml` support. Please use the `secrets.yaml.example`, copy it to secrets.yaml and update it with your values.
