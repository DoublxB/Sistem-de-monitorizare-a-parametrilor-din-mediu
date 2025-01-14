Environmental Parameters Monitoring System

1.Introduction

    1.1.What was the idea behind it?

  The project is based on a question I’ve had for a long time(How do people collect weather data?), as we see data from such systems every day, particularly in weather forecasts. For this reason, I decided to create a system to monitor environmental parameters. Its functionality is undeniable, as this type of system is used daily for monitoring and preventing situations where normal thresholds are exceeded.

    1.2.WHAT DOES IT DO?

    
The system relies on a thermal sensor to collect various environmental data and display it on an LCD screen. Using a joystick and a button, we can control the system, allowing us to navigate through the data and adjust the threshold that alerts us when recommended values are exceeded. If these values are surpassed, an LED will signal the danger by changing its color.


    1.3.What is its purpose?

To display environmental data from its surroundings and allow users to manipulate thresholds to alert them in case of environmental danger, similar to large-scale systems that warn humanity in the event of a catastrophe.



2.General Description

## **2. BOM (Bill Of Materials)**

| **No.** | **Component/Module**             | **Quantity** | **Purchase Link / Datasheet**                          |
|---------|----------------------------------|--------------|--------------------------------------------------------|
| 1       | Arduino Uno R3                   | 1            |  |
| 2       | BMP280 Sensor (I2C/SPI)          | 1            | [Link - BMP280](https://www.optimusdigital.ro)         |
| 3       | 16x2 LCD with I2C                | 1            |                                                        |
| 4       | Joystick Module                  | 1            |                                                        |
| 5       | RGB LED (common anode/cathode)   | 1            |                                                        |
| 6       | Breadboard                       | 1            |                                                        |
| 7       | Jumper Wires                     | 20+          |                                                        |
| 8       | 220Ω Resistors                   | 3            |                                                        |

---

## **3. Detailed Hardware Functionality**

### **Modules and Components Used**

1. **Arduino Uno R3**  
   - Main microcontroller, managing all components.  
   - Operates at **5V** and provides analog, digital pins, and I2C/SPI interfaces.

2. **BMP280 Sensor**  
   - Measures **temperature** and **atmospheric pressure**.  
   - Communication via **I2C** (SDA and SCL connected to A4 and A5 pins).  
   - Power supply: **3.3V** (from the **3.3V pin** on Arduino Uno).

3. **Joystick Module**  
   - Provides two analog channels for movement (X and Y) and a digital button:  
     - **X** -> Pin **A0** (analog).  
     - **Y** -> Pin **A1** (analog).  
     - **Button** -> Pin **D2** (digital).

4. **16x2 LCD with I2C**  
   - Displays data read from the **BMP280 sensor** (temperature and pressure).  
   - Uses the **I2C interface** (pins **A4 (SDA)** and **A5 (SCL)**).  
   - Power supply: **5V** (from the **5V pin** on Arduino Uno).

5. **RGB LED (common anode/cathode)**  
   - Controls system status based on threshold settings:  
     - **Red**: Alert.  
     - **Green**: Normal values.  
    
   - Pins used for **PWM control**:  
     - **R (Red)** -> Pin **D3**.  
     - **G (Green)** -> Pin **D4**.  
     
   - **220Ω resistors** are used for LED protection.

---

### **Interfaces and Connections**

- **I2C**: Used for **BMP280** and **16x2 LCD**.  
  - **SDA** -> Pin **A4**.  
  - **SCL** -> Pin **A5**.  

- **Analog**:  
  - **Joystick X** -> Pin **A0**.  
  - **Joystick Y** -> Pin **A1**.  

- **Digital**:  
  - **Joystick Button** -> Pin **D2**.  
  - **RGB LED**:  
    - **R** -> Pin **D3**.  
    - **G** -> Pin **D4**.  
    - **B** -> Pin **D5**.  

---

### **Power Consumption Calculation**

| **Component**         | **Current Consumption (mA)** | **Voltage (V)** |
|------------------------|-----------------------------|-----------------|
| Arduino Uno            | ~50 mA                      | 5V              |
| BMP280                 | ~1.5 mA                     | 3.3V            |
| 16x2 LCD (I2C)         | ~20 mA                      | 5V              |
| Joystick               | ~10 mA (average)            | 5V              |
| RGB LED                | ~20 mA per color            | 5V              |

**Estimated Total Consumption**: **100 - 150 mA** (depending on system status).

---

## **4. Pins Used for Each Component**

| **Component**         | **Arduino Uno Pins**          | **Purpose**                           |
|------------------------|------------------------------|---------------------------------------|
| **BMP280**            | A4 (SDA), A5 (SCL)           | I2C interface for communication.      |
| **16x2 LCD (I2C)**    | A4 (SDA), A5 (SCL)           | Shares I2C pins.                      |
| **Joystick (X/Y)**    | A0, A1                       | Analog channels for position.         |
| **Joystick (Button)** | D2                           | Digital pin for button state.         |
| **RGB LED**           | D3 (R), D4 (G), D5 (B)       | PWM control for RGB colors.           |

---



![image](https://github.com/user-attachments/assets/72cbba13-4bb7-445d-91a6-34021d3aa504)



4.Software Design

# 🌡️ 4.Software Design

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





