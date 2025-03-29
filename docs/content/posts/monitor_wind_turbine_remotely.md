+++
title = '📡 Monitor the wind turbine remotely'
date = 2024-01-16T08:05:00Z
draft = false
categories = [ "Full day workshop", "Afternoon workshop" ]
summary = "Using radio to broadcast the measured voltage to a remote microcontroller"
+++

---

# Introduction

## Aims
In this part of the activity we will:
* Transmit our recorded voltage as a radio signal using the micro:bit
* Receive our radio signal using a seperate micro:bit
* Plot that value on the computer

## Learning outcomes

| Learning outcome |                                                                 |
| ---------------- | --------------------------------------------------------------- |
| Code             | Understand the power of built in code features and libraries    |
| Radio waves      | Understand how these are transmitted and received               |
| Visualisation    | How to visualise a value on a computer and export a data series |
---

# Preperation

## Equipment required

| Equipment item                                   | Quantity |
| ------------------------------------------------ | :------: |
| Custom wind turbine kit (you just assembled it!) |    1     |
| Extra micro:bit                                  |    1     |

## Tools required

| Tool      | Quantity |
| --------- | :------: |
| Laptop/PC |    1     |

---

# Transmitting the measured voltage as a radio signal

## Using two microbits

We will be using two microbits. 

* **Micro:bit A** will send a radio signal (with the voltage measurement). It is attached to the wind turbine.
* **Micro:bit B** will receive a radio signal (with the voltage measurement). It is attached to your computer.

The radio signal can be transmitted up to 70 meters.

[![Pic](/images/monitor_wind_turbine_remotely/microbit_radio_sender_receiver_v1.png)](/images/monitor_wind_turbine_remotely/microbit_radio_sender_receiver_v1.png)

## Programming Micro:bit A

> :elephant: Reminder: **Micro:bit A** will send a radio signal (with the voltage measurement). It is attached to the wind turbine.

Go to [micro:bit make code](https://makecode.microbit.org) and start a new program

Enter this code. You will need to use:
* Pins
* Variables
* Serial
* Radio

> :warning: Pick your own radio group from 0-255. Both micro:bits need to use the same group. It must not be the same as anyone else's in the room.

[![Pic](/images/monitor_wind_turbine_remotely/code_radio_send_voltage_v2.png)](/images/monitor_wind_turbine_remotely/code_radio_send_voltage_v2.png)

## Download it to your microbit

You will need to:
* Insert your usb lead
* Connect your device (as shown in the image below)

[![Pic](/images/using_microcontroller_to_monitor_velocity/connect_device_v1.png)](/images/using_microcontroller_to_monitor_velocity/connect_device_v1.png)

## Run the program

You should see:
* A big square shown on the microbit display

You can now unplug the micro:bit from the usb lead. 

Connect the battery to the micro:bit. It should show the same image on its display without being connected to the computer

> :satellite: You're now continuously transmitting the voltage value as a radio signal!

[![Pic](/images/monitor_wind_turbine_remotely/microbit_A_transmit_v1.jpg)](/images/monitor_wind_turbine_remotely/microbit_A_transmit_v1.jpg)

---

# Receiving the measured voltage as a radio signal

## Programming Micro:bit B

> :elephant: Reminder: **Micro:bit B** will receive a radio signal (with the voltage measurement). It is attached to your computer.

Go to [micro:bit make code](https://makecode.microbit.org) and start a new program

Enter this code. You will need to use:
* Serial
* Radio

> :warning: Use the same radio group as for **Micro:bit A**

[![Pic](/images/monitor_wind_turbine_remotely/code_radio_receive_voltage_v2.png)](/images/monitor_wind_turbine_remotely/code_radio_receive_voltage_v2.png)

## Download it to your microbit

You will need to:
* Insert your usb lead
* Connect your device (as shown in the image below)

[![Pic](/images/using_microcontroller_to_monitor_velocity/connect_device_v1.png)](/images/using_microcontroller_to_monitor_velocity/connect_device_v1.png)

## Run the program

Go to *show data - device*

You should see:
* A small square shown on the microbit display
* When you rotate the shaft of the wind turbine clockwise, then **Micro:bit A** reads the analogue input and transmits it to **Micro:bit B** as a radio signal
* **Micro:bit B** transmits this as serial data (along the usb cable) to the computer

[![Pic](/images/monitor_wind_turbine_remotely/serial_data_received_radio_v1.png)](/images/monitor_wind_turbine_remotely/serial_data_received_radio_v1.png)

> :tada: You're now continuously transmitting and receiving the voltage value as a radio signal!

---

# Test it with the wind turbine blades

Next steps:

* Install the wind turbine flat blades
* Hold the wind turbine in front of a fan
* Check the voltage value is plotted on a computer when the wind turbine turns