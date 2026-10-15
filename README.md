# STM32-Based Programmable Metronome System

This project is a programmable metronome system designed using the **STM32F401VE** microcontroller and simulated in the Proteus environment. Based on the BPM (Beats Per Minute) value set by the user, Timer interrupts are generated, and a rhythmic sound output is obtained through the speaker using a PWM signal.

## 🚀 Key Features

* **Interrupt-Driven Architecture:** The system performs timing operations using hardware timer units instead of continuous polling or delay functions. This ensures a low CPU load and real-time operation.
* **Precise Timing:** Rhythm timing is calculated using the Timer unit ($T = 60 / BPM$). 
* **Sound Generation via PWM:** Timer PWM channels are used to drive the speaker output. The generated 20kHz square wave signal has been verified via the oscilloscope.
* **LCD Display:** A 16x2 character LCD (in 4-bit mode) is integrated so the user can instantly monitor the current BPM value and system status.
* **Software Debounce:** A software debounce filter is applied to button inputs to prevent false triggering caused by mechanical bouncing.

## 📊 Simulation View

The oscilloscope square wave (PWM) output of the system running on Proteus:

![Proteus Oscilloscope Output](simulasyon.png)

## 🛠️ Hardware and Software Used

* **Microcontroller:** STM32F401VE (ARM Cortex-M4)
* **Development Environment:** STM32CubeIDE (HAL Libraries)
* **Simulation:** Proteus 8 Professional
* **Peripherals:** 16x2 LCD Display, Speaker, Push Buttons

## ⚙️ Pin Configuration

| Component | Pin | Function | Description |
| :--- | :--- | :--- | :--- |
| Audio Output (Speaker) | PA8 | TIM1_CH1 (PWM) | Metronome rhythm sound (20kHz) |
| Speed Up Button | PA0 | GPIO_EXTI0 | Increases the BPM value by +5. |
| Speed Down Button | PA2 | GPIO_EXTI2 | Decreases the BPM value by -5. |
| Start/Stop Button | PA5 | GPIO_EXTI5 | Activates/Deactivates the metronome. |
| LCD Control/Data | PC0-PC5| GPIO_Output | 16x2 Character LCD connections. |


