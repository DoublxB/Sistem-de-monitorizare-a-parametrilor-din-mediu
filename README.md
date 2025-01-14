Environmental Parameters Monitoring System

1.Introduction

    1.1.What was the idea behind it?

  The project is based on a question I’ve had for a long time(How do people collect weather data?), as we see data from such systems every day, particularly in weather forecasts. For this reason, I decided to create a system to monitor environmental parameters. Its functionality is undeniable, as this type of system is used daily for monitoring and preventing situations where normal thresholds are exceeded.

    1.2.WHAT DOES IT DO?

    
The system relies on a thermal sensor to collect various environmental data and display it on an LCD screen. Using a joystick and a button, we can control the system, allowing us to navigate through the data and adjust the threshold that alerts us when recommended values are exceeded. If these values are surpassed, an LED will signal the danger by changing its color.


    1.3.What is its purpose?

To display environmental data from its surroundings and allow users to manipulate thresholds to alert them in case of environmental danger, similar to large-scale systems that warn humanity in the event of a catastrophe.



2.General Description

4.Software Design

IDE:
Visual Studio Code, PlatformIO

Libraries:
Arduino (Core functionalities)
LiquidCrystal_I2C (LCD display control)
Wire (I2C communication)


Planned Functionalities:
Real-Time Monitoring:
Continuously monitor and capture real-time temperature and pressure readings using the BMP280 sensor for dynamic environmental assessment.

Dynamic LCD Display:
Display real-time sensor data on a 16x2 I2C LCD, providing clear visualization of temperature and pressure metrics.

Proximity Alerts via RGB LED:

The RGB LED provides instant visual feedback:
Red → Temperature exceeds the defined threshold.
Green → Temperature is within the safe range.
Interactive User Control:

A joystick allows seamless navigation between different display screens.
Enables intuitive adjustment of the temperature threshold for alert customization.
Auditory Alerts:

A buzzer emits sound alerts when the temperature exceeds the threshold.
A dedicated button toggles the buzzer on/off, allowing user-controlled feedback.
Data Logging:

Transmits real-time temperature and pressure data via Serial (USART) for debugging and analytical purposes.
Key Features of the Code
Sensor Integration:
The BMP280 sensor is initialized and continuously reads temperature and pressure data.

Dynamic Visual Feedback:
The LCD I2C displays real-time data, and the RGB LED changes color based on the current temperature.

User Interaction:
A joystick allows users to navigate between screens and adjust the temperature threshold interactively.

Auditory Feedback:
A buzzer provides audio alerts when the temperature exceeds the set threshold, with the option to toggle the alert via a button.

Inactivity Timeout:
After 30 seconds of inactivity, the system automatically returns to the welcome screen.

Serial Debugging:
Data from the sensor is sent to the Serial Monitor for debugging.



