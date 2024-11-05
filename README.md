# Project Title: **AC Switching (Dimmer)**

##  Introduction

This project presents an AC switching (dimmer) circuit designed to control the power delivered to an AC load, enabling adjustable brightness in lighting or variable speed in AC motors. The circuit is built with a 4N25 optocoupler, MOC3021 triac driver, and BTA16-600B triac, which together provide phase-controlled switching and electrical isolation. This setup allows for safe control of high-voltage AC loads through low-voltage control signals.

<p align="center">
    <img src="https://github.com/thynavy/AC_Switching_Dimmer/blob/main/Dimmer.png" />
    <br />
    <strong>Figure 1: The AC Switching (Dimmer) Module</strong>
</p>

##  Components Overview

1. **4N25 Optocoupler:** The 4N25 optocoupler electrically isolates the low-voltage control circuit from the high-voltage AC side, safeguarding sensitive components.
2. **MOC3021 Triac Driver:** The MOC3021 is an optoisolated triac driver that enables phase-angle control. By varying the phase angle of the AC signal, this component helps control power delivery to the load, achieving dimming functionality.
3. **BTA16-600B Triac:** The BTA16-600B triac is a high-power switching component that handles large AC currents. It is triggered by the MOC3021 and provides robust control for the AC load, such as lights or motors.

##  Design Documentation

###  Circuit Design

1. **Schematic Overview:** The schematic features the 4N25 optocoupler connected to the control circuit, ensuring isolation. The MOC3021 triac driver is then used to trigger the BTA16-600B triac in response to phase-angle control signals. This arrangement allows for precise control over the AC waveform delivered to the load.
  [Dimmer Schematic (PDF)](https://github.com/thynavy/AC_Switching_Dimmer/blob/main/Schematic.pdf)
3. **Phase Control Mechanism:**
   - The phase-angle control technique allows the circuit to adjust power by varying the point in the AC cycle where the triac is triggered. This approach modulates the average voltage delivered to the load.
   - The MOC3021 is triggered at different points in the AC cycle, controlling when the BTA16-600B triac conducts. The earlier the triac is triggered within each AC cycle, the higher the power delivered to the load.   
4. **Component Ratings:**   
   -  **4N25:** Rated for isolation up to 5kV, ensuring safe separation between control and AC load sides.
   - **MOC3021:** Designed to handle 400V, with adequate isolation for AC applications.
   - **BTA16-600B:** Rated for 16A and 600V, providing sufficient capacity for high-power AC loads.

###  PCB Layout

The PCB layout is designed to separate high-voltage and low-voltage sections, adhering to best practices for safety and electromagnetic compatibility (EMC). Key considerations include:
- **Isolation Zones:** Clear separation between the low-voltage control side (optocoupler and triac driver) and the high-voltage AC side (main triac and load).
- **Thermal Management:** Adequate spacing and thermal relief for the BTA16-600B triac to dissipate heat during operation.

###  Applications

This dimmer circuit can be used in various scenarios such as:
- **Lighting Control:** Adjusting brightness in AC lighting systems for energy savings and ambiance control.
- **Motor Speed Control:** Modulating speed in AC fan or motor applications.
- **Temperature Regulation:** Controlling heating elements by adjusting the power delivered to resistive loads.

##  Getting Started

###  Hardware Setup

1. **Connect the AC Load:** Attach the AC load (e.g., lamp or motor) to the output terminals of the BTA16-600B triac.
2. **Microcontroller Control:** Connect the low-voltage control circuit (e.g., Arduino or microcontroller) to the 4N25 optocoupler.
3. **Isolation and Grounding:**
   - Ensure that there is clear isolation between the low-voltage control circuit and the high-voltage AC components.
   - Verify grounding for safety and stability.

###  Software Control

1. **Phase Control Algorithm:** Write a control algorithm to vary the phase angle by triggering the 4N25 optocoupler at different points in the AC cycle.
2. **Adjusting Power Output:** Use pulse-width modulation (PWM) or a timer to adjust the triggering phase angle in each AC cycle to modulate the power delivered to the load.

##  Usage Guidelines

1. **Load Limitations:** Ensure that the load does not exceed the BTA16-600B triac’s maximum current rating (16A). Exceeding this may result in overheating or damage.
2. **Testing the Circuit:** Test the circuit with a lower voltage or a small resistive load before applying it to full AC mains power to verify functionality and safety.
3. **Monitoring Temperature:** Regularly monitor the temperature of the BTA16-600B triac. Consider using a heat sink if high power loads are used for prolonged periods.

##  Safety Precautions

_**Warning: This circuit involves high-voltage AC power, which can be dangerous or fatal if mishandled. Follow these safety guidelines strictly.**_

1. Circuit Isolation:

   - Maintain strict separation between the low-voltage (control) side and high-voltage (AC load) side of the circuit. The 4N25 and MOC3021 are optoisolators that help ensure this isolation, but physical separation on the PCB is essential.

2. Protective Equipment:

   - Always wear protective equipment (e.g., insulated gloves, safety glasses) when working with high-voltage AC circuits.

3. Proper Enclosure:

   - Enclose the circuit in a non-conductive box to prevent accidental contact with high-voltage components.

4. Testing Precautions:

   - When testing, use an isolation transformer to reduce the risk of electrical shock and avoid working alone.

5. Heat Management:

   - High-power loads can cause the triac to generate substantial heat. Ensure adequate ventilation and consider adding a heat sink if necessary.

6. Emergency Preparedness:

   - Keep an accessible power cutoff switch nearby and make sure you know how to safely disconnect the circuit in an emergency.




