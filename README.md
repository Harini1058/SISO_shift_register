# SISO_shift_register
# AIM:

To implement SISO Shift Register using verilog and validating their functionality using their functional tables

# SOFTWARE REQUIRED:

Quartus prime

# THEORY

SISO shift Register

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

<img width="787" height="262" alt="Screenshot 2025-12-16 002434" src="https://github.com/user-attachments/assets/3289fc7f-3f39-4345-9f74-3630ab144d38" />


Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next. Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

# Procedure

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register. 

3.Shift the contents of the register one position to the right (or left). 

4.Output the shifted bit from the last stage of the register 


5.Repeat steps 2-4 for each bit you want to input and shift.

# PROGRAM

# Developed by:HARINI G
# RegisterNumber:25015377

module shift_register(clk, rst, q);
    input clk;
    input rst;
    output [3:0] q;
    reg [3:0] q;

    always @(posedge clk or posedge rst)
    begin
        if (rst) begin
            q <= 4'b0000;      
        end
        else begin
            q[0] <= q[3];      
            q[1] <= q[0];
            q[2] <= q[1];
            q[3] <= q[2];
        end
    end
endmodule

# RTL LOGIC FOR SISO Shift Register

<img width="1312" height="643" alt="Screenshot 2025-12-15 230948" src="https://github.com/user-attachments/assets/7bf5a1e7-bd1a-44a4-bed7-f9a1312803ca" />


# TIMING DIGRAMS FOR SISO Shift Register

![WhatsApp Image 2025-12-16 at 06 24 29_6dab2c85](https://github.com/user-attachments/assets/9675e8b3-3cc3-466a-815c-c4f6b8c8dab0)

# RESULTS

SISO Shift Register using verilog and validating their functionality using their functional tables has successful execution of the program.
