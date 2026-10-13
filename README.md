# Interactive Mechatronic Conveyor System 

A mechatronic project for a rapid prototyping course at LTH focused on integrating mechanical components, sensors, and software structure to create a fully functional, thematic and interactive experience (my group's theme being: You are the boss of a Shark Factory producing Shrimp Chips). The project involved the complete mechatronic product development cycle from CAD modeling to final electronic assembly, all within a strict timeframe.

## Mechanical Design & Manufacturing
The physical structure and moving parts were designed from scratch in Creo and subsequently 3D-printed:
*   **Custom Conveyor Belt:** Designed and assembled a fully functional conveyor belt consisting of 50+ individually 3D-printed interlocking links.

| Fresh from the printer | Put together |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/5576fd5c-7b1c-40ad-8484-19fa9ae6bd10" width="400"> | <img src="https://github.com/user-attachments/assets/2a97e071-684f-4276-bd87-427a49610178" width="400"> |

*   **Transmission & Amplifier:** Engineered custom cogs, a secure motor mount, and a conical amplifier housing unit to amplify the output of the audio player.
*   **Structural Housing:** Built a dual-level cuboid chassis, cleanly separating the user-visible factory layer from the underlying electronic control area.

| Inside the factory | Some more 3D-prints |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/dcc98b7b-6d04-452b-89d6-b0cc3d5f5a2e" width="400"> | <img src="https://github.com/user-attachments/assets/3b594433-05d4-43f5-90f6-e8e8826e6ff2"  width="400"> |

## Electronics & Power Architecture
The system is controlled by an Arduino Uno, driving multiple actuators and interactive elements:
*   **Actuation:** A DC motor controlled via a Cytron driver using PWM signals powers the conveyor belt, while a servo motor pops out a hidden panic button. 
*   **Power Management:** To ensure system stability and eliminate electrical noise from the motors, the logic board and the high-current actuators are powered by two completely isolated power sources.
*   **Audio-Visual Feedback:** Integrated an RGB LED strip and a DFPlayer Mini MP3 module to provide dynamic, real-time feedback based on the factory's operational state, dictated by the users input choice. 

## Software Architecture
The embedded C++ code is designed for robust, continuous operation without freezing or missing user inputs:
*   **State Machine Design:** The main loop utilizes a finite state machine to safely transition between different interactive scenarios (such as, normal production, strike, panic mode).
*   **Non-Interrupting Execution:** Replaced all standard delay functions with millis-based timers, to ensure the microcontroller remains fully responsive to user input picked up by the sensors, while concurrently managing the sound and light outputs.
*   **Hardware Debouncing:** Implemented a debounce filter to eliminate high-frequency noise from the physical buttons, providing flawless state transitions by ensuring someone is really pressing the button. 

## Results & Demo
The final system performed as expected during the live demonstration, successfully handling concurrent tasks (motor control, audio, lighting, and sensor input) without any logical blocking or power drops. 

[Demo video from an early stage of the project](https://drive.google.com/file/d/1YMHVF0lZewXSyK2voq_vUxEnQRn3MMQe/view?usp=sharing)



