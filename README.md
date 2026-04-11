# PowerBarConfigurator

## 📖 Overview

**PowerBarConfigurator** is a WPF desktop application designed to monitor, control, and configure a multi-outlet power bar device powered by an STM32 microcontroller over Modbus (RTU via serial).

The application provides real-time insights into electrical metrics (current, voltage, power), allows outlet control, supports data logging and visualization, and enables firmware flashing via DFU mode.

## ✨ Features

Some of the features PowerBarConfigurator provides are:

* 🔌 Device Connectivity
* ⚡ Power Control
* 📊 Real-Time Graphing
* 🧾 Data Logging
* ⚙️ Configuration
* 📝 Activity Logging
* 🎨 Theming
* 🔄 Firmware Flashing

## 🏗️ Architecture

The application follows a modular service-based architecture:

### 🧩 Core Services

* **ConnectionService** - Handles Modbus communication and polling
* **PowerService** - Tracks outlet states and overall system power state
* **GraphService** - Processes ADC samples and computes RMS current
* **DataLoggingService** - Manages time-series logging and exports
* **ActivityLogService** - Central logging system for UI and debugging
* **FlashingService** - Handles firmware updates via DFU

## 📦 Requirements

* Windows OS
* .NET (WPF compatible version)
* STM32-based power bar device
* USB-to-Serial connection
* STM32 DFU support (for firmware flashing)

## 🚀 Getting Started

1. Clone the repository:

   ```bash
   git clone <repo-url>
   ```

2. Open the solution in Visual Studio

3. Build and run the application

4. Connect your device and click **Connect**

## 🧠 Usage Notes

* Ensure the correct voltage setting (120V / 240V) before connecting
* Do not disconnect the device during firmware flashing
* Logging and graphing require an active connection
* Current limits are capped at **20A max**

## 🤖 AI Disclosure

This project was developed with assistance from AI tools, including:

* ChatGPT-5 Thinking
* Google Gemini 3 Thinking
* Github Copilot Free

These tools were used for:

* Documentation writing
* Code cleanup and refactoring
* Assisting with integration and implementation details

All final code and design decisions were reviewed and validated by the developer.

## ⚖️ License

PowerBarConfiguration is licensed under the MIT License. Please see the [license file](https://github.com/Restoration-Hub/power-bar-software/blob/main/LICENSE.txt) for more information.

## 🙏 Acknowledgements

* [NModbus](https://github.com/NModbus/NModbus)
* [LiveCharts2](https://github.com/Live-Charts/LiveCharts2)
* [STM32 SharpCubeProgrammer](https://github.com/K-Society/KSociety.SharpCubeProgrammer)
* [MaterialDesignThemes](https://github.com/MaterialDesignInXAML/MaterialDesignInXamlToolkit)