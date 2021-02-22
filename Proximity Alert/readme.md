# Proximity Alert
The project is a simple system which detects if any object is nearby. Once it detects any object in the vicinity, it would take a picture and send that via a text message with a link to view the image ob the browser.

## Architecture

![Diagram](./content/architecture.png)

- The sensors would be connected to the device and the device would read the data from the sensors
- The device is an IoT Edge device that will contain modules to interact with the sensors and IoT Hub
- The device would detect any proximity and send the event along with the image (in Blob) to the IoT Hub
- The IoT Hub will forward the event to an Event Grid
- The Event Grid will route the event to a Topic for Proximity Alerts
- The Alert Handler will read the message from the topic and send an SMS with a link to the image
- Users can view the image through the link in the browser