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

# 🌡️ Environmental Monitoring System with Visual and Audio Alerts

A real-time environmental monitoring system using the **BMP280** sensor to measure temperature and pressure, providing visual and audio feedback through an **LCD display**, **RGB LED**, and a **buzzer**. User interaction is enabled via a **joystick** and a dedicated button to toggle audio alerts.

---

## 🛠️ **Development Environment**

- **IDE:** Visual Studio Code  
- **Framework:** PlatformIO  
- **Libraries:**  
  - **Arduino** (Core functionalities)  
  - **LiquidCrystal_I2C** (LCD control)  
  - **Wire** (I2C communication)  
  - **Adafruit BMP280 Library** (Sensor integration)

---

## 🎯 **Planned Functionalities**

1. **Real-Time Monitoring:**  
   Continuous tracking of temperature and pressure using the **BMP280 sensor**.
   

3. **Dynamic LCD Display:**  
   Real-time visualization of sensor data on a **16x2 I2C LCD**.
   Visualization of the maximum and minimum temperatures since the system startup.


5. **Visual Alerts via RGB LED:**  
   - **Red** → Temperature exceeds the threshold.  
   - **Green** → Temperature is within a safe range.

6. **Interactive Control:**  
   - Navigate between screens using a **joystick**.  
   - Adjust the temperature threshold in real-time.
   - The ability to change the threshold.
   - Smart Thinking:The LCD returns to the home screen after 30 seconds of inactivity.


7. **Data Logging:**  
   - Sensor data is transmitted via **Serial (USART)** for debugging.
   - Storing the maximum and minimum data.


## 💾 **Setup**



![image](https://github.com/user-attachments/assets/37b1ca96-ec28-43f9-bc4a-99d512282ca9)
![image](https://github.com/user-attachments/assets/a69890b5-6c6a-4691-b3b1-c3d6252aa094)





