# PISO_SR
# The shift register, which allows parallel input (data is given separately to each flip flop and in a simultaneous manner) and produces a serial output is known as a Parallel-In Serial-Out shift register. The logic circuit given below shows a parallel-in-serial-out shift register. The circuit consists of four D flip-flops which are connected. The clock input is directly connected to all the flip-flops but the input data is connected individually to each flip-flop through a multiplexer at the input of every flip-flop. The output of the previous flip-flop and parallel data input are connected to the input of the MUX and the output of MUX is connected to the next flip-flop. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip-flop.
# Aim:
To stimulate and synthesis PISO SR using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
![image](https://github.com/RESMIRNAIR/PISO_SR/assets/154305926/f0f2d979-b298-4693-b5c8-8eea850936d4)
# Program:
```library IEEE;

use IEEE.STD_LOGIC_1164.ALL;

use IEEE.STD_LOGIC_ARITH.ALL;

use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity piso is

Port (clk,rst,load:in std_logic;

p_data: in std_logic_vector(3 downto 0);

s_out : out std_logic);

end piso;

architecture Behavioral of piso is

signal temp_reg: std_logic_vector(3 downto 0):=(others=>'0');

begin

process(clk,rst)

begin

if rst='1' then

temp_reg<=(others=>'0');

elsif rising_edge(clk) then

if load ='1' then

temp_reg<=p_data;

else

temp_reg <= temp_reg(2 downto 0) & '0';

end if

end if

end process

end Behavioral
```
# Output:
![WhatsApp Image 2024-05-11 at 22 05 04_e4371857](https://github.com/S-Mohankumar/PISO_SR/assets/163832108/88e4e120-36a5-4774-9e78-f7f7380f09f7)
# RESULT:
Thus the verilog program for PISO SR has been simulated and verified successfully.

