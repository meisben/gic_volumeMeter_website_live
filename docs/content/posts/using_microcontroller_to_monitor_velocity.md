+++
title = '📈 Using a microcontroller to record velocity'
date = 2024-01-17T08:05:00Z
draft = false
categories = [ "Full day workshop", "Afternoon workshop" ]
summary = "Using a special type of computer to chart the velocity"
+++

---

# Introduction

## Aims
In this part of the activity we will:
* Add a voltage divider and understand how it works
* Record voltage using a microcontroller
* Visualise the voltage on a computer screen as a chart

## Learning outcomes

| Learning outcome |                                                 |
| ---------------- | ----------------------------------------------- |
| Electronics      | Understand how to use a breadboard              |
| Electronics      | Understand, create and use a voltage divder     |
| Mechatronics     | Read an analogue signal using a microcontroller |
---

# Preperation

## Equipment required

| Equipment item                                   | Quantity |
| ------------------------------------------------ | :------: |
| Custom wind turbine kit (you just assembled it!) |    1     |

## Tools required

| Tool       | Quantity |
| ---------- | :------: |
| Multimeter |    1     |

---

# Why use a voltage divider? 

## Feeding a voltage into a microcontroller

The microbit can [measure an analogue voltage input of up to 3.3 volts.](https://makecode.microbit.org/reference/pins/analog-read-pin)

Our voltage is higher than 3.3 volts so we will need to reduce it! If we don't we will damage the microbit.

## What is a voltage divider

A voltage divider helps us to reduce (step down) a voltage to a lower level.

It's a type of electronic circuit that looks like this. 

[![Pic](/images/using_microcontroller_to_monitor_velocity/voltage_divider.png)](/images/using_microcontroller_to_monitor_velocity/voltage_divider.png)


We can use an easy formula or [calculator](https://ohmslawcalculator.com/voltage-divider-calculator) to find the values of resistors that we should use in the voltage divider.

Try that now. If the maximum voltage from the wind turbine is 5 volts. Use the calculator to find which resistor values we will need to use in the voltage divider. One of the resistors values must be 330 Ohms.

# Let's create the voltage divider

## First make sure you have connected to the positive and negative voltage of the motor terminals

Position your crocodile clips onto your motor terminals.

Connect the other end into your wago connectors

## Understanding the breadboard

The breadboard lets us easily create electronic circuits. 

We can stick wires into the breadboard

All of the columns of holes of the breadboard are connected together with metal strips.

This means any wires we place in the same columnn are connected together.

[![Pic](/images/using_microcontroller_to_monitor_velocity/breadboard_connections_v1.1.png)](/images/using_microcontroller_to_monitor_velocity/breadboard_connections_v1.1.png)

## Creating our voltage divider in the breadboard

Create the voltage divider. The image below shows you how to do that!

You will have to cut some wires (jumpers) to the right length. 

You will need to use the wago electrical connectors and the crocodile clips.

[![Pic](/images/using_microcontroller_to_monitor_velocity/wind_turbine_voltage_reading_multi_v2.png)](/images/using_microcontroller_to_monitor_velocity/wind_turbine_voltage_reading_multi_v2.png)


## Check you voltage divider with a multimeter

Use the multimeter to measure your voltage divider.

Turn the wind turbine shaft with you fingers. 

You should find that the reading is postiive and does not exceed 2 volts. If this is not true please seek help from a mentor.

> :warning: Do not go past this step until you have shared your setup with a mentor. It's possible to damage the microbit if there's too much voltage.


# Readimg the analogue input with the microbit

## Connect the output from the voltage divider to the microbit

Following the circuit diagram shown in the image below

You will need to use the wago electrical connectors and the crocodile clips.

[![Pic](/images/using_microcontroller_to_monitor_velocity/wind_turbine_voltage_reading_microbit_v1.png)](/images/using_microcontroller_to_monitor_velocity/wind_turbine_voltage_reading_microbit_v1.png)

## Create your program

Go to [micro:bit make code](https://makecode.microbit.org) and start a new program

Enter this code. You will need to use:
* Pins
* Variables
* Serial

[![Pic](/images/using_microcontroller_to_monitor_velocity/code_voltage_serial_measurement_v1.png)](/images/using_microcontroller_to_monitor_velocity/code_voltage_serial_measurement_v1.png)

## Download it to your microbit

You will need to:
* Insert your usb lead
* Connect your device (as shown in the image below)

[![Pic](/images/using_microcontroller_to_monitor_velocity/connect_device_v1.png)](/images/using_microcontroller_to_monitor_velocity/connect_device_v1.png)

## Run the program

Go to *show data - device*

You should see:
* A heart shown on the microbit display
* When you rotate the shaft of the wind turbine clockwise, then the microbit reads the analogue input
* It transmits this as serial data (along the usb cable) to the computer

[![Pic](/images/using_microcontroller_to_monitor_velocity/serial_data_v1.png)](/images/using_microcontroller_to_monitor_velocity/serial_data_v1.png)

# Convert it to a voltage

Currently the microbit [reads a voltage from 0 to 3.3V and maps it to a number from 0-1023](https://makecode.microbit.org/reference/pins/analog-read-pin).

[![Pic](/images/using_microcontroller_to_monitor_velocity/read_analogue_v1.png)](/images/using_microcontroller_to_monitor_velocity/read_analogue_v1.png)

To convert this back to a voltage it's easy we just need to use this simple formula

[![Pic](/images/using_microcontroller_to_monitor_velocity/equation_convert_pinval_voltage_v1.png)](/images/using_microcontroller_to_monitor_velocity/equation_convert_pinval_voltage_v1.png)

We need to multiply again by 2 because of the voltage divider (which reduces the voltage by half)

[![Pic](/images/using_microcontroller_to_monitor_velocity/equation_convert_pinval_voltage_x2_v1.png)](/images/using_microcontroller_to_monitor_velocity/equation_convert_pinval_voltage_x2_v1.png)

# Adjust the program

Let's adjust the program to reflect this

[![Pic](/images/using_microcontroller_to_monitor_velocity/code_voltage_serial_measurement_volts_v1.png)](/images/using_microcontroller_to_monitor_velocity/code_voltage_serial_measurement_volts_v1.png)


We should see the serial values now appear in volts

[![Pic](/images/using_microcontroller_to_monitor_velocity/serial_data__voltsv1.png)](/images/using_microcontroller_to_monitor_velocity/serial_data__voltsv1.png)