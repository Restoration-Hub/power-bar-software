# PowerBarConfigurator Software Application

## Overview

**PowerBarConfigurator** is a WPF desktop application designed to monitor, control, and configure a multi-outlet power bar device powered by an STM32 microcontroller over Modbus (RTU via serial).

The application provides real-time insights into electrical metrics (current, voltage, power), allows outlet control, supports data logging and visualization, and enables firmware flashing via DFU mode.

## Features

### 🔌 Device Connectivity

* Automatic detection of STM32 device over available serial ports
* Modbus RTU communication using NModbus
* Connection state tracking (Disconnected / Connecting / Connected)

### ⚡ Power Control

* Toggle individual outlets
* Turn all outlets ON/OFF
* Real-time outlet state monitoring

### 📊 Real-Time Graphing

* Live power usage graphs per outlet or combined
* RMS current calculations from ADC samples
* Smooth real-time updates using LiveCharts

### 🧾 Data Logging

* Log current, voltage, and power over time
* Filter by individual outlet or all outlets
* Export logs to CSV
* UI-friendly live log stream

### ⚙️ Configuration

* Set amperage or wattage limits per outlet or globally
* Automatic conversion between watts and amps
* Input validation and safety limits

### 📝 Activity Logging

* Centralized logging system
* Timestamped events
* Exportable to CSV

### 🎨 Theming

* Light and Dark modes
* Persisted user preferences

### 🔄 Firmware Flashing

* DFU mode support
* Firmware flashing via STM32 CubeProgrammer API
* Progress tracking and logging

## Architecture

The application follows a modular service-based architecture:

### Core Services

* **ConnectionService** - Handles Modbus communication and polling
* **PowerService** - Tracks outlet states and overall system power state
* **GraphService** - Processes ADC samples and computes RMS current
* **DataLoggingService** - Manages time-series logging and exports
* **ActivityLogService** - Central logging system for UI and debugging
* **FlashingService** - Handles firmware updates via DFU

### UI Structure

* WPF UserControls for each page:

  * Home
  * Graphs
  * Data Logging
  * Configuration
  * Settings
  * About

* Custom controls:

  * InfoCard
  * MultiValueInfoCard

## Requirements

* Windows OS
* .NET (WPF compatible version)
* STM32-based power bar device
* USB-to-Serial connection
* STM32 DFU support (for firmware flashing)

## Getting Started

1. Clone the repository:

   ```bash
   git clone <repo-url>
   ```

2. Open the solution in Visual Studio

3. Build and run the application

4. Connect your device and click **Connect**

## Usage Notes

* Ensure the correct voltage setting (120V / 240V) before connecting
* Do not disconnect the device during firmware flashing
* Logging and graphing require an active connection
* Current limits are capped at **20A max**

## Project Structure

```
PowerBarConfigurator/
|
|-- Core/
|   |-- Services/
|   |-- Models/
|
|-- Controls/
|
|-- Pages/
|
|-- Styles/
|
|-- Themes/
|
|-- App.xaml / MainWindow.xaml
```

## AI Disclosure

This project was developed with assistance from AI tools, including:

* ChatGPT
* Google Gemini
* Github Copilot

These tools were used for:

* Documentation writing
* Code cleanup and refactoring
* Assisting with integration and implementation details

All final code and design decisions were reviewed and validated by the developer.

## License

MIT License

## Author

Aviaee Inc.

## Acknowledgements

* NModbus
* LiveCharts2
* STM32 SharpCubeProgrammer
* MaterialDesignTheme