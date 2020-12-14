---
layout: page
permalink: /projects/hybrid-electric-go-kart/
title: Hybrid Electric Go-Kart
subtitle: Hybrid electric vehicle designed and fabricated from chasis
---

![/img/projects/hybrid-electric-go-kart/header.png](/img/projects/hybrid-electric-go-kart/header.png)

# Summary

The goal of the project was to develop a detailed design and an action plan, through performing research on existing electric vehicle systems, developing a procurement plan for electric vehicle components, designing and fabricating custom electric vehicle components, and constructing a hybrid electric vehicle.

## Members and Roles

- Eli Yu - Circuit design and electrical system integration
- James Thompson - Mechanical system design and fabrication
- Ke Liu - Microcontroller system and automation
- Lucas Ye - Battery testing and validation

<hr />

# Revival

As the project was based on an old two-seat go-kart chasis for salvage, several salvage operations were required before any new modification.

- The metal parts of the go-kart(mostly the back frame) were de-rusted to maintain structural integrity.
- The flat tires were patched and resealed to prevent leakage after re-inflation.
- The broken brake padel and brake lines are fixed as the mechanical last resort for all electrical systems failure.

<hr />

# Electrical Design

## Control Panel

The control panel consists of 1 E-Stop button, 3 two-position switches, 1 three-position switch, and 4 LED indicators(2 of them currently not in used).
<br>
From top to bottom, the switches are used to turn on and off the BMS, DC step-down converter, motor controller, and to choose the motor direction. The top right green LED is used to indicate the power status of BMS, and the bottom right green LED is used to indicate the power status of DC step-down converter. The left side red and orange LEDs are not in used.

![/img/projects/hybrid-electric-go-kart/control-panel.png](/img/projects/hybrid-electric-go-kart/control-panel.png)

## Battery Management System

The BMS is connected to the control panel through Connector #2, and the power exchange between BMS and DC step-down module is through the Power Connector.
<br>
The charging station circuit controls the charging with a single flip-switch, through the pilot signal circuitry and J1772 plug. The AC power from the charging station is then converted into 48V DC power through the AC-DC converter.
<br>
The ‘Octopus’ Harness is an acrylic shielded high voltage 48V power bus with 4 anderson connectors connected together with a voltage gage for monitoring. The 4 anderson connectors put together the BMS output, charging station regulated output, gas engine alternator output, and the motor controller power input.

![/img/projects/hybrid-electric-go-kart/bms.png](/img/projects/hybrid-electric-go-kart/bms.png)

## Motor Controller

The motor controller is controlled by the control panel via its connection through Connector #4 and Connector #3.

![/img/projects/hybrid-electric-go-kart/motor-controller.png](/img/projects/hybrid-electric-go-kart/motor-controller.png)

## Gas Engine Control System

The gas engine control system is relatively more isolated, while only taking the 48V and 12V power from the rest of the system. More detailed explanation can be found in Microcontroller System.

![/img/projects/hybrid-electric-go-kart/gas-engine.png](/img/projects/hybrid-electric-go-kart/gas-engine.png)

<hr />

# Mechanical Design

