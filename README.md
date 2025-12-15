# srflipflop
# DEVELOPED BY:BUSHPIKA C 
# REG NO :25007434
# AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

# SOFTWARE REQUIRED:

Quartus prime

# THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

<img width="727" height="401" alt="image" src="https://github.com/user-attachments/assets/5aaf5d78-d41f-40b0-88b6-345b261660a8" />

This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

<img width="800" height="426" alt="image" src="https://github.com/user-attachments/assets/4613b1db-2bb7-4181-bd2c-95c9725b8821" />

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

<img width="676" height="567" alt="image" src="https://github.com/user-attachments/assets/c1fc3a03-5981-4788-a480-7f3261023305" />
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="537" height="277" alt="image" src="https://github.com/user-attachments/assets/c09b5e99-367c-45d9-a6a9-d0905898524f" />
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

Procedure

# PROGRAM

```
module sr_ff (
    input  wire clk, rst, S, R,
    output reg  Q
);
    always @(posedge clk) begin
        if (rst)
            Q <= 1'b0;         // Reset
        else begin
            case ({S,R})
                2'b00: Q <= Q;     // No change
                2'b01: Q <= 1'b0;  // Reset
                2'b10: Q <= 1'b1;  // Set
                2'b11: Q <= 1'bx;  // Invalid
            endcase
        end
    end
endmodule


```
# RTL LOGIC FOR FLIP FLOPS:
<img width="1920" height="1080" alt="Screenshot 2025-12-15 110143" src="https://github.com/user-attachments/assets/a732f6ba-e8af-4236-96e9-ef177ba1f8dd" />



# TIMING DIGRAMS FOR FLIP FLOPS:
<img width="1920" height="1080" alt="Screenshot 2025-12-15 111948" src="https://github.com/user-attachments/assets/b6ad7049-27ca-443f-ac74-c61d2b8af106" />


# RESULTS
Thus the program has been executed successfully.
