# Adc_program_for_TGS_822
![Ioc diagram for thr project](https://github.com/user-attachments/assets/7192b5ef-7f82-46a3-afaa-2a1fd2f5b5d3)
![Result graph](https://github.com/user-attachments/assets/938f6e4a-b30f-4552-b93d-9e942b70a35d)


# MQ-135 Gas Sensor Interface with STM32

This project demonstrates how to interface an MQ-135 gas sensor with an STM32 microcontroller to measure air quality and detect various gases (NH₃, NOx, alcohol, benzene, smoke, CO₂).

## Features
- Reads analog voltage from MQ-135 sensor
- Converts voltage to PPM (parts per million) concentration
- Outputs data via UART (115200 baud)
- Configurable for different STM32 boards

## Hardware Requirements
- STM32 microcontroller (tested with STM32F4 series)
- MQ-135 gas sensor
- 20kΩ load resistor (RL)
- 5V power supply for sensor
- USB-to-TTL converter for UART monitoring (optional)

## Pin Configuration
- **PA0**: Analog input from MQ-135 sensor
- **USART2**: TX (PA2) and RX (PA3) for serial communication

## Software Requirements
- STM32CubeIDE
- STM32CubeMX (for configuration)
- Terminal program (Putty, Tera Term, etc.) for serial monitoring

## Installation
1. Clone this repository
2. Open the project in STM32CubeIDE
3. Build the project
4. Flash to your STM32 board

## Configuration
The project was created using STM32CubeMX with these settings:
- System Clock: 84 MHz (using HSI and PLL)
- ADC1: Channel 0, 12-bit resolution
- USART2: 115200 baud, 8-bit data, no parity
- All unused pins are disabled

## Calibration
For accurate measurements:
1. Place the sensor in clean air (100ppm NH₃)
2. Measure the sensor resistance (R0)
3. Update the `R0` constant in the code
4. Adjust `A` and `B` constants for your target gas (default is acetone)

## Usage
After flashing:
1. Connect a terminal program to USART2 (115200 baud)
2. The system will output:
   ```
   Voltage: x.xx V, PPM: x.xx
   ```
   every second

## Customization
To modify the behavior, edit the main while loop in `main.c`. You can:
- Change the sampling rate by adjusting the `HAL_Delay()` value
- Add threshold detection for alarms
- Implement different gas concentration calculations
- Add additional sensors

## Supported STM32 Boards
The code can be adapted for any STM32 board with:
- At least 1 ADC channel
- UART capability
- STM32Cube HAL support

Tested with:
- STM32F401RE
- STM32F407VG
- STM32F103C8 (Blue Pill)

## Project Structure
- `Core/Src/main.c`: Main application code
- `Core/Inc/main.h`: Configuration defines
- `STM32F4...ioc`: STM32CubeMX configuration file

## Notes
- Only the essential pins (highlighted green in the .ioc file) are enabled
- All unused peripherals are disabled to minimize code size
- The project was created with STM32CubeIDE v1.11.0

## License
This project is licensed under the terms of the MIT license.
# MQ-135 Gas Sensor Interface with STM32

This project demonstrates how to interface an MQ-135 gas sensor with an STM32 microcontroller to measure air quality and detect various gases (NH₃, NOx, alcohol, benzene, smoke, CO₂).

## Features
- Reads analog voltage from MQ-135 sensor
- Converts voltage to PPM (parts per million) concentration
- Outputs data via UART (115200 baud)
- Configurable for different STM32 boards

## Hardware Requirements
- STM32 microcontroller (tested with STM32F4 series)
- MQ-135 gas sensor
- 20kΩ load resistor (RL)
- 5V power supply for sensor
- USB-to-TTL converter for UART monitoring (optional)

## Pin Configuration
- **PA0**: Analog input from MQ-135 sensor
- **USART2**: TX (PA2) and RX (PA3) for serial communication

## Software Requirements
- STM32CubeIDE
- STM32CubeMX (for configuration)
- Terminal program (Putty, Tera Term, etc.) for serial monitoring

## Installation
1. Clone this repository
2. Open the project in STM32CubeIDE
3. Build the project
4. Flash to your STM32 board

## Configuration
The project was created using STM32CubeMX with these settings:
- System Clock: 84 MHz (using HSI and PLL)
- ADC1: Channel 0, 12-bit resolution
- USART2: 115200 baud, 8-bit data, no parity
- All unused pins are disabled

## Calibration
For accurate measurements:
1. Place the sensor in clean air (100ppm NH₃)
2. Measure the sensor resistance (R0)
3. Update the `R0` constant in the code
4. Adjust `A` and `B` constants for your target gas (default is acetone)

## Usage
After flashing:
1. Connect a terminal program to USART2 (115200 baud)
2. The system will output:
   ```
   Voltage: x.xx V, PPM: x.xx
   ```
   every second

## Customization
To modify the behavior, edit the main while loop in `main.c`. You can:
- Change the sampling rate by adjusting the `HAL_Delay()` value
- Add threshold detection for alarms
- Implement different gas concentration calculations
- Add additional sensors

## Supported STM32 Boards
The code can be adapted for any STM32 board with:
- At least 1 ADC channel
- UART capability
- STM32Cube HAL support

Tested with:
- STM32F401RE
- STM32F407VG
- STM32F103C8 (Blue Pill)

## Project Structure
- `Core/Src/main.c`: Main application code
- `Core/Inc/main.h`: Configuration defines
- `STM32F4...ioc`: STM32CubeMX configuration file

## Notes
- Only the essential pins (highlighted green in the .ioc file) are enabled
- All unused peripherals are disabled to minimize code size
- The project was created with STM32CubeIDE v1.11.0

## License
This project is licensed under the terms of the MIT license.

## For more information :
- contact : prathamesh.mane22@spit.ac.in
