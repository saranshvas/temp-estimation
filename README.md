# Development of a Device for Estimation of Ambient Temperature by Measuring Ultrasonic Propagation Velocity in Air
Saransh<sup>1,</sup><sup>2</sup><sup>*</sup>, Nitin Dhiman<sup>2,</sup><sup>3</sup>, and P.K. Dubey<sup>2,</sup><sup>3</sup>

¹ Department of Electronics Engineering, J.C. Bose University of Science and Technology, YMCA Faridabad, India

² Pressure, Vacuum and Ultrasonic Metrology, Division of Physico-Mechanical Metrology, CSIR-National Physical Laboratory, New Delhi, India

³ Academy of Scientific and Innovative Research (AcSIR), Ghaziabad, India

\* Corresponding Author; e-mail: saransh.vas@gmail.com


# 🏛️ Overview

This project presents a low-cost, contactless system for ambient temperature estimation developed at CSIR-NPL, New Delhi, under Prof. P.K. Dubey.

The system measures ultrasonic time-of-flight (TOF) with an HC-SR04 sensor and an ATmega16A microcontroller, calculates the ultrasonic propagation velocity in air, and estimates temperature with high precision (±0.4 °C). Results are displayed in real-time via a 16x2 LCD, demonstrating repeatable and reliable measurements suitable for laboratory and industrial applications.

Publication: In proceedings of International Conference on Ultrasonics and Materials Science for Advanced Technology (ICUMSAT-2025) held on 21-23 Jan 2026, Chennai, India.


# Citation
If you use this code, data, or methodology in academic or research work, please cite: https://www.researchgate.net/publication/400065300_Development_of_a_Device_for_Estimation_of_Ambient_Temperature_by_Measuring_Ultrasonic_Propagation_Velocity_in_Air


# 🎯 Objectives

1. Design a contactless, robust temperature estimation device.
 
2. Achieve high-precision measurements using ultrasonic TOF.

3. Implement signal processing to minimize measurement jitter.

4. Provide a low-cost, reproducible platform for educational and research applications.


# How to Use

1. Compile the code using CodeVisionAVR for ATmega16A.
2. Connect HC-SR04:
   - TRIG → PD0
   - ECHO → PD1
3. Place a flat reflector at 100 cm from the sensor.
4. Power the system and observe velocity and temperature on the LCD.


# ⚙️ Hardware Components

| Component         | Model / Specs           | Purpose                                |
| ----------------- | ----------------------- | -------------------------------------- |
| Microcontroller   | ATmega16A               | Timing measurement & control           |
| Ultrasonic Sensor | HC-SR04                 | Pulse emission and echo detection      |
| Reflector         | 100 cm calibrated plate | Fixed acoustic path                    |
| Display           | 16x2 LCD                | Real-time temperature output           |
| Miscellaneous     | PCB + jumper wires      | Signal conditioning & mechanical setup |


# 🔬 Methodology

Ultrasonic Pulse Emission: HC-SR04 emits a 10 µs pulse toward a fixed 100 cm reflector.

Time-of-Flight Measurement: ATmega16A measures round-trip time digitally.

Velocity Calculation:

       c = 2d / t ​

where 
c is the velocity of sound in air in m/s

d = reflector distance in m, 

t = TOF in sec

Temperature Estimation:

        c = 331.4 + 0.606 T

where 
where, c is the velocity of sound in air in m/s, 331.4 m/s is the velocity of sound at 0°C, 0.606 is the temperature coefficient, indicating how sound speed increases per degree rise in temperature, T is the ambient temperature in °C.

Signal Processing:
    
   1. 200-sample averaging to reduce random jitter

   2. 10 ms inter-sample delay to prevent residual echo interference

Display: Real-time temperature output on 16x2 LCD.

 
# 📈 Key Results

1. High-Precision Temperature Estimation: ±0.4 °C uncertainty achieved using ultrasonic propagation velocity.

2. Effective Signal Processing: Averaging and timing synchronization minimized environmental noise and sensor fluctuations.

3. Robust Embedded Implementation: Stable, repeatable measurements via ATmega16A + HC-SR04 + reflector.

4. Practical Applicability: Non-contact, low-cost, reliable ambient temperature estimation suitable for lab and industrial use.

5. Foundation for Future Innovations: Framework for advanced ultrasonic sensing in environmental monitoring, assistive technology, and precision instrumentation.

6. Real-World Impact: Reduces manual errors and enhances safety and efficiency in sensitive environments.


# 🛠️ Features

1. Contactless temperature measurement

2. Microcontroller-based digital TOF processing

3. Reproducible PCB setup

4. Averaging for jitter reduction

5. Real-time LCD display

6. Open-source code for educational and research use
