# Project_Template

## Team Name: 
Bitstream Bandits

## Team Members:
- Bobby Downey
- Alex Clunan

## Project Title:
Radio Encryption

## Project Description:
We are implementing encrypted radio communication between two FPGA SoCs. A software defined radio (SDR) will be connected to each SoC, each SoC wil send and receive encrypted data from the other. Each SoC will be able to encrypt and decrypt messages that it sends/receives.

## Key Objectives:
- Design of a custom IP block that accelerates the AES encryption algorithm
- Interfacing with the IP block on the PYNQ board using the Python Overlay class via Visual Studio’s RemoteSSH extension
- Using Python radio libraries, interface with the radio module to transmit the encrypted messages from keyboard input to a receiver radio
- Have the computer with the receiver radio ensure that the encrypted message was transmitted successfully by decrypting and displaying the message
- Expand this model to allow for real-time 2-way communication where two computers can transmit and receive messages via keyboard input in real time, encrypted using AES on two PYQN boards
- If time permits, expand this to audio communication using ADCs to sample input from microphones and transmit the encrypted audio


## Technology Stack:
(List the hardware platform, software tools, language(s), etc. you plan to use)
- Verilog HDL in Xilinx 
- Python in Visual Studio Code
- HC-12 Radio

## Expected Outcomes:
(Describe what you expect to deliver at the end of the project)
This project will consist of several interconnected components, including logic and signal processing modules for AES encryption, radio communication modules in Python, and modules for interfacing between the FPGA SoCs and the SDR. The AES encryption module will be a custom IP block designed for the FPGA that we will use to accelerate the encryption and decryption processes. This block will handle AES cipher operations in hardware, minimizing latency compared to software implementations. Signal processing and communication between the two FPGAs will be driven by Python SDR modules. These SDR modules will be used for transmission and reception of radio signals. Publicly accessible reference code for the HC-12 will be used for transmission and reception of the encrypted data. Links to the articles used in research for this configuration are shown below. We will connect the PYNQ Z-1 to the HC-12 via a UART connection and pinouts. This will allow the SoC to configure and send signals to the HC-12. The intended process is as follows: receive input data ⇒ send data to PL to be encrypted ⇒ PL returns encrypted data ⇒ PYNQ board sends encrypted data to HC-12 ⇒ HC-12 sends encrypted radio signal => Second HC-12 receives encrypted data ⇒ Second HC-12 sends encrypted data to second PYNQ board via UART ⇒ PYNQ receives encrypted data and sends it to the PL for decryption ⇒ PL decrypts data and sends it back to the processor ⇒ data is displayed on the python terminal. The encryption key is pre-shared between devices.

## Tasks:
(Describe the tasks that need to be completed. Assign students to tasks)
- Design of a custom IP block that accelerates the AES encryption algorithm (Alex)
- Interfacing with the IP block on the PYNQ board using the Python Overlay class via Visual Studio’s RemoteSSH extension (Alex and Bobby)
- Using Python radio libraries, interface with the radio module to transmit the encrypted messages from keyboard input to a receiver radio (Bobby)
- Have the computer with the receiver radio ensure that the encrypted message was transmitted successfully by decrypting and displaying the message (Bobby)
- Expand this model to allow for real-time 2-way communication where two computers can transmit and receive messages via keyboard input in real time, encrypted using AES on two PYQN boards (Alex and Bobby)
- If time permits, expand this to audio communication using ADCs to sample input from microphones and transmit the encrypted audio (Alex and Bobby)

## Timeline:
(Provide a timeline or milestones for the project)
- Having AES IP block generated (April 10, 2025)
- Ensure that two-way radio communication is successful without encryption (April 13, 2025)
- Complete working two-way encrypted communication (April 29, 2025)
