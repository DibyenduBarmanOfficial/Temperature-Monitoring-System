# Temperature-Monitoring-System
My Project in Microcontroller is Temperature Monitoring System using a 16X2 Liquid Crystal Display and LM35.

**The components used in the project are as follows:**

1. **Nucleo F401RE:** 
   - Description: Development board based on the STM32 microcontroller.
   - Purpose: Provides the platform for programming and controlling the temperature monitoring system.

2. **LM35:** 
   - Description: Analog temperature sensor.
   - Purpose: Measures the ambient temperature and provides the analog temperature value.

3. **16X2 Liquid Crystal Display (LCD):**
   - Description: Display module with two rows and 16 columns.
   - Purpose: Displays the temperature reading and other relevant information.

4. **Potentiometer:**
   - Description: Adjustable resistor.
   - Purpose: Used to control the contrast of the LCD display for better visibility.

5. **DigitalOut (Red LED):**
   - Description: Digital output pin connected to a red LED.
   - Purpose: Indicates high-temperature conditions by turning on the red LED.

6. **DigitalOut (Green LED):**
   - Description: Digital output pin connected to a green LED.
   - Purpose: Indicates normal temperature conditions by turning on the green LED.

7. **TextLCD Library:**
   - Description: Library for interfacing with text-based LCD displays.
   - Purpose: Provides convenient functions for controlling the LCD display and printing text.
  
----------------------------------------------------------------------------------------------------
** Code explanation: Temperature Monitoring System using a 16X2 Liquid Crystal Display (LCD) and LM35
----------------------------------------------------------------------------------------------------
1. **Include necessary libraries:**
   - The code begins by including the required libraries, such as "mbed.h" for the mbed platform and "TextLCD.h" for interfacing with the LCD display.

2. **Define the components:**
   - Next, the code defines the necessary components used in the system. This includes creating objects for the LM35 temperature sensor (AnalogIn), the red LED (DigitalOut), the green LED (DigitalOut), and the LCD display (TextLCD).

3. **Main function:**
   - The main function is where the temperature monitoring system logic resides.

4. **Temperature measurement:**
   - Inside the main function, a while loop is used to continuously monitor the temperature.
   - The LM35 sensor value is read using the LM35.read() function, which returns a value between 0 and 1 representing the analog input voltage.
   - The LM35 sensor value is then converted to millivolts by multiplying it with 3300.
   - The millivolt value is divided by 10 to obtain the temperature in degrees Celsius.

5. **Display temperature on LCD:**
   - The lcd.locate() function is used to set the cursor position on the LCD to the desired column and row.
   - The lcd.printf() function is used to print the temperature value on the LCD display with two decimal places.
   - The lcd.putc() function is used to print the degree symbol (°) and the letter 'C' for Celsius.

6. **LED indication:**
   - Based on the temperature reading, the code checks if the temperature is greater than or equal to 25 degrees Celsius.
   - If the temperature is above 25 degrees Celsius, the red LED is turned on by setting RedLed = 1 and the green LED is turned off by setting GreenLed = 0.
   - If the temperature is below 25 degrees Celsius, the red LED is turned off by setting RedLed = 0 and the green LED is turned on by setting GreenLed = 1.

7. **Delay and LCD clearing:**
   - The code includes a wait(2) function to introduce a delay of 2 seconds between temperature readings.
   - After the delay, the lcd.cls() function is used to clear the LCD display, preparing it for the next temperature reading.

8. **Loop:**
   - The code continues to execute the while loop, continuously monitoring the temperature and updating the display and LED indication.

In summary, the code reads the temperature from the LM35 sensor, displays it on the LCD, and provides visual indication through the red and green LEDs based on the temperature threshold of 25 degrees Celsius. The system continuously repeats this process, providing real-time temperature monitoring on the LCD display.

---------------------------------------------------------------------------------------------------
** Project Report: Temperature Monitoring System using a 16X2 Liquid Crystal Display (LCD) and LM35         
---------------------------------------------------------------------------------------------------

**1. Introduction**
The Temperature Monitoring System is a project that utilizes a 16X2 Liquid Crystal Display (LCD) and an LM35 temperature sensor to monitor and display real-time temperature readings. This system provides a convenient way to keep track of temperature variations in various applications, such as home automation, industrial processes, and environmental monitoring.

**2. Components Used**
- Nucleo F401RE development board: It serves as the microcontroller platform for the project.
- LM35 temperature sensor: It is an analog temperature sensor that provides accurate temperature measurements.
- 16X2 Liquid Crystal Display (LCD): It is used to display the temperature readings.
- Potentiometer: It is used to adjust the contrast of the LCD display.
- Connecting wires: They are used to establish connections between the components.
- Breadboard: It provides a platform for prototyping and connecting the components.

**3. Working Principle**
The Temperature Monitoring System works as follows:

- The LM35 temperature sensor is connected to an analog input pin of the Nucleo F401RE development board.
- The LCD is connected to the Nucleo board using the appropriate GPIO pins.
- The system continuously reads the temperature value from the LM35 sensor using the AnalogIn function.
- The raw sensor value is converted to millivolts and then divided by 10 to obtain the temperature in degrees Celsius.
- The temperature reading is displayed on the LCD using the TextLCD library. The LCD is capable of displaying up to 16 characters per line and 2 lines.
- The system compares the temperature value with a predefined threshold (in this case, 25 degrees Celsius).
- If the temperature exceeds the threshold, a red LED is turned on to indicate a high temperature condition. If the temperature is below the threshold, a green LED is turned on to indicate a normal temperature condition.
- The system repeats the temperature measurement and display process at regular intervals, providing real-time temperature monitoring.

**4. Conclusion**
The Temperature Monitoring System using a 16X2 Liquid Crystal Display and LM35 provides an effective solution for monitoring temperature in real-time. The system offers accurate temperature readings and visual indication through LEDs, making it suitable for various applications. By utilizing the LM35 sensor and the 16X2 LCD, the project demonstrates the integration of analog and digital components to create a functional temperature monitoring system.

**5. Future Enhancements**
- Implementing additional sensors to monitor other environmental parameters such as humidity or pressure.
- Adding data logging capabilities to record temperature readings over time.
- Incorporating wireless communication to enable remote monitoring and control.
- Developing a user interface for settings adjustment and data visualization.

Overall, the Temperature Monitoring System serves as a foundation for expanding the functionality and applicability of temperature monitoring in diverse scenarios.
