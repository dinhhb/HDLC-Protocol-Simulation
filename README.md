# HDLC Protocol Simulation

This project simulates the High-Level Data Link Control (HDLC) protocol by creating, sending, and receiving HDLC frames. HDLC is a bit-oriented protocol used to facilitate communication between devices over a serial communication channel.

## Prerequisites

Make sure you have the following installed on your system:

- `gcc` compiler: to compile the C code
- Terminal or Command Prompt: to execute the compiled program

## Getting Started

1. Clone this repository to your local machine or download the source code files.

2. Compile the C code using the following command:

    ```sh
    gcc -o main main.c
    ```

3. Run the compiled program:

    ```sh
    ./main packet.txt
    ```

## How It Works

The program follows these main steps:

1. **Reading the Packet**: The program reads a packet from the `packet.txt` file. The packet is a sequence of hexadecimal bytes representing data.

2. **Creating the HDLC Frame**: The program creates an HDLC frame from the packet data. The frame consists of an address field, control field, information field, FCS (Frame Check Sequence), and flag fields.

3. **Sending HDLC Frame**: The simulated function `send_hdlc_frame` outputs the contents of the HDLC frame to the console, simulating the process of sending the frame.

4. **Receiving HDLC Frame**: The program prompts the user to input a received HDLC frame in hexadecimal format. It then checks the frame for validity, extracts the information field, and computes the FCS. If the FCS in the frame matches the computed FCS, the frame is considered valid; otherwise, it's considered invalid.

## Usage Examples

Here are some example input scenarios and expected outputs:

- **Correct Frame**: `7EFF03127D5E7D5E34567871467E` (Valid frame)
- **Wrong FCS Value**: `7EFF03127D5E7D5E34567875767E` (Invalid frame)
- **Missing Flag Field**: `FF03127D5E7D5E34567871467E`
- **Missing Address Field**: `7E03127D5E7D5E34567871467E`
- **Invalid Buffer Length**: `7EFF03127D5E7D5E3456787467E`

## Acknowledgments

This project is created for educational purposes and demonstrates the basic concepts of the HDLC protocol simulation.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
