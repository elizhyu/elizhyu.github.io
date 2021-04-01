---
layout: page
permalink: /projects/hybrid-electric-go-kart/
title: Hybrid Electric Go-Kart
subtitle: Hybrid electric vehicle designed and fabricated from bare chassis
---

![/img/projects/hybrid-electric-go-kart/header.png](/img/projects/hybrid-electric-go-kart/header.png)

# Summary

The goal of the project was to develop a detailed design and an action plan, through performing research on existing electric vehicle systems, developing a procurement plan for electric vehicle components, designing and fabricating custom electric vehicle components, and constructing a hybrid electric vehicle.

### Members and Roles

- Eli Yu - Circuit design and electrical system integration
- James Thompson - Mechanical system design and fabrication
- Ke Liu - Microcontroller system and automation
- Lucas Ye - Battery testing and validation

<hr />

# Revival

As the project was based on an old two-seat go-kart chassis for salvage, several salvage operations were required before any new modification.

- The metal parts of the go-kart(mostly the back frame) were de-rusted to maintain structural integrity.
- The flat tires were patched and resealed to prevent leakage after re-inflation.
- The broken brake padel and brake lines are fixed as the mechanical last resort for all electrical systems failure.
- The hydaulic front brakes are bleeded and refilled with DOT3 brake fluid.

<hr />

# Electrical Design

### Control Panel

The control panel consists of 1 E-Stop button, 3 two-position switches, 1 three-position switch, and 4 LED indicators(2 of them currently not in used).
<br>
From top to bottom, the switches are used to turn on and off the BMS, DC step-down converter, motor controller, and to choose the motor direction. The top right green LED is used to indicate the power status of BMS, and the bottom right green LED is used to indicate the power status of DC step-down converter. The left side red and orange LEDs are not in used.

![/img/projects/hybrid-electric-go-kart/control-panel.png](/img/projects/hybrid-electric-go-kart/control-panel.png)

### Battery Management System

The BMS is connected to the control panel through Connector #2, and the power exchange between BMS and DC step-down module is through the Power Connector.
<br>
The charging station circuit controls the charging with a single flip-switch, through the pilot signal circuitry and J1772 plug. The AC power from the charging station is then converted into 48V DC power through the AC-DC converter.
<br>
The ‘Octopus’ Harness is an acrylic shielded high voltage 48V power bus with 4 anderson connectors connected together with a voltage gage for monitoring. The 4 anderson connectors put together the BMS output, charging station regulated output, gas engine alternator output, and the motor controller power input.

![/img/projects/hybrid-electric-go-kart/bms.png](/img/projects/hybrid-electric-go-kart/bms.png)

### Motor Controller

The motor controller is controlled by the control panel via its connection through Connector #4 and Connector #3.

![/img/projects/hybrid-electric-go-kart/motor-controller.png](/img/projects/hybrid-electric-go-kart/motor-controller.png)

### Gas Engine Control System

The gas engine control system is relatively more isolated, while only taking the 48V and 12V power from the rest of the system. More detailed explanation can be found in Microcontroller System.

![/img/projects/hybrid-electric-go-kart/gas-engine.png](/img/projects/hybrid-electric-go-kart/gas-engine.png)

<hr />

# Mechanical Design

### Specs

**Gas Engine:**

- Features and Specs
    - 6.5 HP
    - electric start
    - low oil safety shut-off
    - max RPM: 3400
    - output shaft: 3/4 in
- Modifications
    - Removal of original key start swtich
    - Addition of engine start and stop control by the computer
    - Addition of a servo controlling the throttle

<a href="/img/projects/hybrid-electric-go-kart/power-core-1212.jpg"><img src="/img/projects/hybrid-electric-go-kart/power-core-1212.jpg" alt="Power Core 1212" class="lazyload" style="vertical-align:top; width:20%; float:right;"></a>

**Alternator**

- Features and Specs
    - **Power Core 1212** - 48V Permanent Magnet Generator
    - based on standard General Motors alternator
    - max operating RPM: 1700
    - max output power: 77 amps at 50 V

<br>

<a href="/img/projects/hybrid-electric-go-kart/gunset-assembly.jpg"><img src="/img/projects/hybrid-electric-go-kart/gunset-assembly.jpg" alt="Gunset Assembly" class="lazyload" style="vertical-align:top; width:20%; float:right;"></a>

### Gunset Assembly

All hybrid power related components are integrated into a single removable package, with the engine and the alternator mounted to a 1/8 inch thick aluminum plate. All engine controlling circuits are also mounted to the plate, including a 5V-12V relay to enable the control of engine starter by computer ,and connected to the rest of the electrical system through connectors. Two relays are utilized to isolate the alternator from the rest of the system while on battery-only mode and when the engine just starts up before reaching the operating speed of alternator to provide sufficient voltage and current. When the relays are closed, the engine-alternator combination would supply power to the rest of the system to either charge the battery with too low voltage level or boost the power output to the motor.

<br>

<a href="/img/projects/hybrid-electric-go-kart/batteries.jpg"><img src="/img/projects/hybrid-electric-go-kart/batteries.jpg" alt="BMS Rendered" class="lazyload" style="vertical-align:top; width:20%; float:right;"></a>

### Batteries

Two 48V batteries each with 48 cells are mounted into a specifically welded steel frame and then mounted to the car frame.

<br>


### Electronics

<a href="/img/projects/hybrid-electric-go-kart/bms-rendered.png"><img src="/img/projects/hybrid-electric-go-kart/bms-rendered.png" alt="BMS Rendered" class="lazyload" style="vertical-align:top; width:20%; float:right;"></a>

The BMS circuit is enclosed in a dust-proof plastic box with connectors on the walls. The box is screwed down to the bottom of the rear top car basket frame.

The high power circuits including the **Curtis 1510** motor controller, AC-DC converter for charging, 48V-12V DC-DC converter, and the **KILOVAC EV200** 48V mootor controller relays are mounted to a single aluminum plate, and then mounted to the rear bottom car frame.


<br>

<a href="/img/projects/hybrid-electric-go-kart/J1772.png"><img src="/img/projects/hybrid-electric-go-kart/J1772.png" alt="J1772" class="lazyload" style="vertical-align:top; width:20%; float:right;"></a>

### J1772 Charging Port

The standard J1772 charging plug port is mounted on a 3D-printed plated on the side of the car basket frame behind driver's seat.

<br>

<a href="/img/projects/hybrid-electric-go-kart/EJ4-4001.png"><img src="/img/projects/hybrid-electric-go-kart/EJ4-4001.png" alt="EJ4-4001" class="lazyload" style="vertical-align:top; width:20%; float:right;"></a>

### Electric Driving Motor

The electric motor used is **EJ4-4001** 48-volt DC, shunt-wound, reversible traction motor in a golf cart motor-axle assembly. The motor is capable of providing a maxium of 3.2 HP.

<br>

---

# Mechanical Manufacture and Procedures

- replace the orginal axle frame with fabricated axle frame to fit the golf cart motor-axle assembly
- install 8 in wheel spacers on rear axle to improve stability
- fabricate various mounting panels and brackets
- connect the rear drum brakes on the golf cart axle to the hand brake
- mount throttle rheostat to the underside of cargo basket frame behind driver's seat and feed throttle wires to the pedal
- mount brake rheostat for regenerative braking to front floor panel and connect to brake padel

---

# Microcontroller System

### CAN Bus Monitor

A Sparkfun arduino CAN Bus shield is used to monitor CAN Bus data flow. Battery voltage data is filtered out to indicate when hybrid system needs to engage.

{% highlight C linenos %}
#include <Canbus.h>
#include <defaults.h>
#include <global.h>
#include <mcp2515.h>
#include <mcp2515_defs.h>
#include <SoftwareSerial.h>

char buffer[456];

//***************************** Setup *****************************

SoftwareSerial mySerial(3,6);   // pin 6 = TX, pin 3 = RX

void setup() {
    mySerial.begin(9600);   // set up LCD serial port for 9600 baud
    delay(500);             // wait for display to boot up
    Serial.begin(9600);     // for debug use
    Serial.println("CAN Read - Testing receival of CAN Bus message");
    delay(1000);

    if(Canbus.init(CANSPEED_500))   // Initialize MCP2515 CAN controller at the specified speed
        Serial.println("CAN Init ok");
    else
        Serial.println("Can't init CAN");
    
    delay(1000);
}

void loop() {
    tCAN message;

    if(mcp2515_check_message()) {
        Serial.print("check message ");
        if(mcp2515_get_message(&message)) {
            Serial.print("ID: ");
            Serial.print(message.id, HEX);
        }
    }
}
{% endhighlight %}

### LCD Display

A small LCD display is mounted to the dashboard to display battery voltage, current, and error messages.

{% highlight C linenos %}
void LCD_print() {
    mySerial.write(254);    // move cursor to beginning of first linenos
    mySerial.write(128);

    mySerial.write("                    "); // clear display
    mySerial.write("                    ");

    mySerial.write(254);    // move cursor to beginning of first linenos
    mySerial.write(128);

    mySerial.write("Hello, world!");
}
{% endhighlight %}

### Gas Engine Control

The ignition and stall of the gas engine are controlled by the microcontroller. Once the 'ignition' port of gas engine is connected to 12V, the engine starts. Once the 'stall' ported is grounded, the engine stops. Since gas engine and alternator operates at high voltage, a relay is utilized in the control system. The gas engine RPM is controlled by a servo motor to privde desired 48V output.

**Code to drive relay**

{% highlight C linenos %}
int in1 = 7;
void setup() {
    pinMode(in1, OUTPUT);
    digitalWrite(in1, HIGH);
}

void loop() {
    digitalWrite(in1, LOW);
    delay(3000);
    digitalWrite(in1, HIGH);
    delay(3000);
}
{% endhighlight %}

**Code to drive servo**

{% highlight C linenos %}
#include <Servo.h>

Servo servo_gas;    // Declare Servo

void setup() {
    servo_gas.attach(10);
}

void loop() {
    servo_gas.write(30);    // initial 0 deg
    delay(1500);

    servo_gas.write(150);   // 180 deg
    delay(1500);
}
{% endhighlight %}

---

# Testings and Validation

### Weight Test

A racing vehicle weight is placed under the wheels to measure the actual weight of the finished vehicle.

**Weight Estimation**

<table>
    <tr>
        <th>quantity</th>
        <th>item</th>
        <th>weight (lbs.)</th>
    </tr>
    <tr>
        <td>1</td>
        <td>motor</td>
        <td>35</td>
    </tr>
    <tr>
        <td>1</td>
        <td>alternator</td>
        <td>14</td>
    </tr>
    <tr>
        <td>2</td>
        <td>battery</td>
        <td>140</td>
    </tr>
    <tr>
        <td>1</td>
        <td>frame</td>
        <td>380</td>
    </tr>
    <tr>
        <td>1</td>
        <td>BMS circuit</td>
        <td>20</td>
    </tr>
    <tr>
        <td>1</td>
        <td>electric motor/rear axle assembly</td>
        <td>80</td>
    </tr>
    <tr>
        <td>1</td>
        <td>electronic control board</td>
        <td>30</td>
    </tr>
    <tr>
        <td colspan="2"><b>Total</b></td>
        <td><u>699</u></td>
    </tr>
</table>

**Test Result**

The weight is measued <u>662.5 lbs</u>, with percentage difference of <u>5.22%</u> between real case and estimation.

![Weight Test](/img/projects/hybrid-electric-go-kart/weight-test.jpg)

### Speed Test

The original golf cart motor-axle assembly has a designed speed of <u>20 MPH</u>, but considering the increased wheel size on our go-kart of <u>22 in</u> diameter compared to the gold cart's <u>18 in</u> diameter, a <u>22%</u> increase is expected leading to an estimated max speed of about <u>25 MPH</u>.

**Test Result**

The speed test is performed by testing the time taken for the vehicle to pass a certain distance after fully speeded up. During the test, it takes <u>7.07 seconds</u> to pass <u>200 ft</u> of distance, which results in the actual speed at <u>19.3 MPH</u>.

$$
\begin{aligned}
V = \frac{200 ft \div 5280feet/mile}{7.07 s \div 60 s/min \div 60 min/h} = 19.2876 mph
\end{aligned}
$$

### Battery Validation Bench Test

A General Electric electric vehicle charging station is used in lab to test charge the vehicle battery.

![Bench Test Charging](/img/projects/hybrid-electric-go-kart/bench-charge.jpg)


After fully charged, the throttle is held floored to test discharge the vehicle battery.

<a href="/img/projects/hybrid-electric-go-kart/bench-discharge-photo.png"><img src="/img/projects/hybrid-electric-go-kart/bench-discharge-photo.png" alt="Bench Test Discharging" class="lazyload" style="vertical-align:top; width:20%; float:right;"></a>

![Bench Test discharging](/img/projects/hybrid-electric-go-kart/bench-discharge.jpg)

### Field Battery Charging Test

The vehicle is driven to a public parking lot, and then tested with a standard GE charging station (with J1772 plug) for commercial electric vehicles. The charging is successful, with a fast charging rate to charge up the battery by 1 full volt from 47 V to 48 V in <u>~850 seconds (14 minutes)</u>.

<a href="/img/projects/hybrid-electric-go-kart/field-charge-photo.png"><img src="/img/projects/hybrid-electric-go-kart/field-charge-photo.png" alt="Field Test Charging" class="lazyload" style="vertical-align:top; width:40%; float:right;"></a>

![Field Test Charging](/img/projects/hybrid-electric-go-kart/field-charge.jpg)

### Drive Cycle Test

The drive cycle test is performed in a public parking lot to simulate typical city driving with flat and sloped roads.

The driving cycle test estimation calculation is done according to the measurement of the parking garage shown below.

<a href="/img/projects/hybrid-electric-go-kart/drive-cycle-up.jpg"><img src="/img/projects/hybrid-electric-go-kart/drive-cycle-up.jpg" alt="Drive Cycle Up" class="lazyload" style="vertical-align:top; width:49%;"></a>
<a href="/img/projects/hybrid-electric-go-kart/drive-cycle-down.jpg"><img src="/img/projects/hybrid-electric-go-kart/drive-cycle-down.jpg" alt="Drive Cycle Down" class="lazyload" style="vertical-align:top; width:49%;"></a>

The total distance on Flat Surface: <u>1000.36 m</u>
<br>
The total distance on $$3^{\circ}$$ Gradient Surface: <u>338.33 m</u>
<br>
The total distance on $$-3^{\circ}$$ Gradient Surface: <u>246.89 m</u>

The speed of the vehicle measured is 19.2876 mph, which is 8.6223 m/s.
<br>
Hence, the time taken to travel on different surfgaces can be calcualted:

Time on Flat Surface: $$\frac{1000.36 m}{8.6223 m/s}=\underline{116.02 s}$$
<br>
Time on $$3^{\circ}$$ Gradient Surface: $$\frac{338.33 m}{8.6223 m/s}=\underline{39.24 s}$$
<br>
Time on $$-3^{\circ}$$ Gradient Surface: $$\frac{246.89 m}{8.6223 m/s}=\underline{28.63 s}$$

<img src="/img/projects/hybrid-electric-go-kart/drive-cycle-cal1.jpg" alt="Drive Cycle Calculation 1" class="lazyload" style="vertical-align:top; width:33%;">
<img src="/img/projects/hybrid-electric-go-kart/drive-cycle-cal2.jpg" alt="Drive Cycle Calculation 2" class="lazyload" style="vertical-align:top; width:33%;">
<img src="/img/projects/hybrid-electric-go-kart/drive-cycle-cal3.jpg" alt="Drive Cycle Calculation 3" class="lazyload" style="vertical-align:top; width:33%;">

Thus, through the average power on different surfaces calcuated above, the Total Energy Consumed would be:

$$E_{total}=0.71 kW\times 116.02 s + 4.65 kW\times 39.24 s - 3.23 kW \times 28.63 s = \underline{172.37 kJ}$$

During actual test, the throttle is released on down slopes, and no energy regenration, so the actual energy consumption estimation is:

$$E_{total}=0.71 kW\times 116.02 s + 4.65 kW\times 39.24 s = \underline{264.84 kJ}$$

In real field test, the voltage of battery goes down through time like below:

![Field Test Drive Cycle Discharge](/img/projects/hybrid-electric-go-kart/field-discharge.jpg)

Through the integration of voltage times current over time, the actual energy consumption is <b><u>200.403 kJ</u></b>, which is <u>24.33%</u> different from theoretical value.

### First Road Test

<div style="position:relative;padding-bottom:56.25%;"> <!-- 16:9 ratio, 75% for 4:3 -->
 <iframe style="width:100%;height:100%;position:absolute;left:0px;top:0px;" frameborder="0" width="100%" height="100%" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen src="https://www.youtube.com/embed/DZhD1u15GrI">
</iframe>
</div>
<!--
<video width="100%" height="100%" controls>
  <source src="/img/projects/hybrid-electric-go-kart/drive-test.mp4" type="video/mp4">
</video>
-->
<br>

### Grip and Structure Integrity Test

<!--
<video width="100%" height="100%" controls>
  <source src="/img/projects/hybrid-electric-go-kart/grip-test.mp4" type="video/mp4">
</video>
-->
<div style="position:relative;padding-bottom:56.25%;"> <!-- 16:9 ratio, 75% for 4:3 -->
 <iframe style="width:100%;height:100%;position:absolute;left:0px;top:0px;" frameborder="0" width="100%" height="100%" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen src="https://www.youtube.com/embed/N4e_TS6dAOI">
</iframe>
</div>