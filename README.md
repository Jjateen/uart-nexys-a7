# UART Implementation on Nexys A7-100T

This project demonstrates the implementation of a Universal Asynchronous Receiver-Transmitter (UART) on the Nexys A7-100T FPGA board. It includes source files, constraints, and IP configurations to design, synthesize, and implement the UART interface using Xilinx Vivado.

## Overview
The Universal Asynchronous Receiver-Transmitter (UART) is a serial communication protocol used for transmitting and receiving data between electronic devices. This project implements a UART module with FIFO buffers and provides all necessary files to deploy the design on the Nexys A7-100T FPGA.

## How to Use
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Jjateen/uart-nexys-a7.git
   cd uart-nexys-a7
   ```

2. **Open the Project in Vivado**:
   - Launch Xilinx Vivado and navigate to the project folder.
   - Open the `.xpr` project file under the `uart_a7` directory.

3. **Run Tcl Commands**:
   To automate various steps in Vivado, you can use the following Tcl commands:

   - **Launch a clean build**:
     ```tcl
     reset_run synth_1 impl_1
     ```

   - **Run Linter**:
     ```tcl
     report_drc -name drc_report
     ```

   - **Run Synthesis**:
     ```tcl
     launch_runs synth_1
     wait_on_run synth_1
     ```

   - **Run Implementation**:
     ```tcl
     launch_runs impl_1
     wait_on_run impl_1
     ```

   - **Generate Bitstream**:
     ```tcl
     launch_runs impl_1
     wait_on_run impl_1
     write_bitstream -force uart_a7.bit
     ```

   - **Export Hardware**:
     ```tcl
     write_hw_platform -fixed -include_bitstream -force uart_a7.xsa
     ```

4. **Program the FPGA**:
   - Use the Digilent USB cable to program the Nexys A7-100T FPGA with the generated `.bit` file.
