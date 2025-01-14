

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



