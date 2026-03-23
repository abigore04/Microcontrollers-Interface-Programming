# Microcontrollers: Interface and Programming

A collection of my lab works for **Microcontrollers: Interface & Programming**, focused on the **STM32 Nucleo-F401RE** platform using **STM32CubeMX**, **STM32CubeIDE**, and the **HAL library**.

This repository documents my progress through hands-on microcontroller labs, covering GPIO control, timers and interrupts, low-power modes, RTC-based wake-up, UART communication, and STM32-Arduino interfacing.

---

## Overview

The goal of this repository is to keep all completed course labs in one place and show practical work with embedded systems, including both firmware implementation and hardware testing.

The labs included so far focus on:

- basic GPIO output control
- LED blinking and timing
- timer-based interrupt handling
- low-power operation using **Sleep**, **Stop**, and **Standby** modes
- current measurement and battery life estimation
- RTC wake-up configuration
- UART communication between **STM32** and **Arduino**
- serial logging to PC in CSV-style format

---

## Hardware / Tools Used

- **STM32 Nucleo-F401RE**
- **STM32CubeMX**
- **STM32CubeIDE**
- **C / HAL library**
- **Arduino Uno**
- breadboard, LED, resistor, buzzer, push button
- oscilloscope / measurement tools

---

## Labs Included

### Lab 1 — Flashing LED
A basic GPIO lab where an external LED is connected to the STM32 board and toggled with a visible delay.

**Main ideas:**
- GPIO output configuration in CubeMX
- HAL-based pin toggling
- understanding port/pin mapping
- observing waveform behavior on the oscilloscope

---

### Lab 2 — Battery Life Estimation with Sleep Mode
A low-power lab where a buzzer is activated periodically while the MCU spends most of the time in **Sleep mode**.

**Main ideas:**
- replacing busy-wait delays with **TIM2 interrupts**
- using `__WFI()` for low-power waiting
- measuring active and idle current
- estimating average current and battery lifetime

---

### Lab 3A — Stop Mode
A lab demonstrating **Stop mode** and how the STM32 can wake from an interrupt while still preserving memory.

**Main ideas:**
- wake-up from the on-board user button
- entering Stop mode with HAL power functions
- suspending and resuming SysTick
- restoring the system clock after wake-up
- showing memory retention with a wake counter

---

### Lab 3B — Standby Mode
A lab demonstrating **Standby mode**, where the MCU consumes less power but restarts from reset after wake-up.

**Main ideas:**
- dedicated wake-up pin usage
- difference between Stop and Standby behavior
- standby flags and wake-up flags
- proving that execution state and volatile memory are lost

---

### Lab 4 — UART Communication with Arduino
A communication-based lab where STM32 remains in low power most of the time, wakes periodically, requests button press data from an Arduino, and logs it to the PC.

**Main ideas:**
- UART communication between STM32 and Arduino
- RTC wake-up every 10 seconds
- timestamped CSV logging
- USART1 for Arduino communication
- USART2 for PC serial output
- Stop mode + RTC-based periodic wake-up

---

## What This Repository Shows

This repository reflects my practical work in embedded systems and microcontroller programming, especially:

- configuring peripherals in CubeMX
- writing embedded firmware in C
- working with interrupts and callbacks
- applying low-power design principles
- testing with real hardware
- combining software behavior with electrical measurements
