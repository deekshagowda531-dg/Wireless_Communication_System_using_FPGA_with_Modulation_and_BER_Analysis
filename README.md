Project: FPGA-Based LoRa Wireless Communication System with BER Analysis

Platform: Major Project, Dept. of Electronics & Communication Engineering, VCET Puttur

Project Overview
Purpose: An end-to-end wireless data link that transmits predefined binary data over LoRa and measures how reliably it arrives, using Bit Error Rate (BER) analysis.
Core Workflow: The transmitter FPGA generates and packetizes data and sends it to a LoRa transceiver over SPI. The receiver FPGA reads the received data back over SPI, compares it with the known data, and shows the BER on an LCD.
Key Features
Packet-Based Transmission: Predefined binary data is generated in Verilog HDL and formatted into packets.
LoRa Wireless Link: SX1278 transceivers perform LoRa modulation and transmission at 433 MHz.
Receiver-Side BER Calculation: The receiver FPGA compares received data bit by bit with the transmitted data to count errors.
FSM-Controlled Operation: Finite State Machines sequence both the transmission and reception operations.
Live LCD Output: The receiver shows the received data and the BER result.
Hardware & Software Components
Controllers: Two Spartan-3 FPGA boards, one as transmitter and one as receiver.
Transceivers: Two SX1278 LoRa modules, interfaced to the FPGAs through SPI.
Indicators & Interfaces: LCD display on the receiver, LEDs and antennas.
Software Stack: Verilog HDL, with design, simulation and synthesis in Xilinx ISE Design Suite.
System Architecture & Working Principle
Step 1 (Data Generation): The transmitter FPGA generates predefined binary data and forms packets.
Step 2 (SPI Transfer): The packets are written from the FPGA to the SX1278 over SPI.
Step 3 (Transmission): The SX1278 performs LoRa modulation and transmits wirelessly at 433 MHz.
Step 4 (Reception): The second SX1278 receives the signal, demodulates it and stores the data in its FIFO.
Step 5 (Comparison & Display): The receiver FPGA reads the FIFO over SPI, compares it with the predefined data, calculates BER, and shows the result on the LCD.
Key Results & Metrics
Error-Free Reception: The transmitted data 00000010 was received as 00000010, giving BER 0/8.
Error Detection: In a test with an error, 00000010 was received as 00000110, and the system correctly reported BER 1/8.
BER Scope: The BER measures recovered application-payload bit errors after LoRa demodulation, not the internal physical-layer BER of the transceiver.
Applications
Practical FPGA-based platform for wireless data transmission and performance evaluation.
Educational tool for learning Verilog HDL, SPI interfacing, FSM design and LoRa communication.
Base for IoT, remote monitoring and long-range wireless link testing.
Future Enhancements
System Expansion: Support additional modulation and communication configurations.
Performance Testing: Run systematic BER vs SNR measurements and study the effects of fading, interference and distance.
Reliability: Improve packet synchronization and error handling, and test longer transmissions with more data.
Monitoring Interface: Build a more advanced real-time interface for communication parameters.
FPGA Optimization: Optimize resource use and timing for higher-speed communication.
