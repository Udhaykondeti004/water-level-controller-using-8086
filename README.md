# water-level-controller-using-8086

## Introduction
Water is a precious resource and its conservation is important for 
sustainable development. Water storage tanks are commonly used in 
domestic households to store water for daily use. The water level in 
these tanks needs to be monitored and controlled to prevent overflow 
and to ensure that there is always enough water in the tank. This can be 
done manually, but it is inconvenient and time-consuming. Therefore, 
an automatic water level controller is needed.
To ensure the availability of water while avoiding wastage, it is 
necessary to monitor and control the water level in these tanks. 
Traditionally, this has been done manually by periodically checking the 
tank and adjusting the water flow accordingly. However, this method 
is not only inconvenient but also prone to human error, leading to 
potential overflows or water shortages.
To address these challenges, an automatic water level controller 
is a practical solution. This device uses various technologies and 
sensors to accurately measure the water level in the tank and regulate 
the inflow and outflow of water accordingly. By automating the 
process, it eliminates the need for constant manual monitoring, saving 
time and effort for users.
The automatic water level controller operates based on preset 
parameters, such as desired maximum and minimum water levels. 
When the water level reaches the upper threshold, the controller 
activates a mechanism to stop the inflow of water, preventing overflow. 
Similarly, when the water level drops below the lower threshold, the 
controller triggers the inflow to maintain an adequate supply.
Besides preventing wastage and ensuring a constant water supply, 
an automatic water level controller offers additional benefits. It 
optimizes the use of water resources, conserving this precious 
commodity and promoting sustainable practices. It also reduces the risk 
of damage to property caused by overflowing water and helps prevent 
waterborne diseases by ensuring the availability of clean water.
Overall, the implementation of automatic water level controllers 
in domestic households promotes efficient water management, 
enhances convenience, and contributes to sustainable development. By 
harnessing technology to automate the monitoring and control of water 
levels, we can conserve this vital resource while meeting our daily 
water needs.

## Working on Project

### Powering on the Processor:
- Connect the power supply to the 8086 processor-based system.
- Ensure that the power supply is compatible with the processor 
and provides the required voltage and current.
- Turn on the power supply to provide power to the entire system, 
including the processor.

### Water Level Sensing:
- The project uses a sensor connected to the sensor port (0301h) 
to measure the water level in the tank.
- The sensor provides an analog signal that represents the water 
level.
- The 8086 processor reads the analog signal by inputting from 
the sensor port using the `in al, dx` instruction.
- The value read from the sensor port is stored in the AL register 
for further processing.

### Water Level Comparison:
- The project sets a threshold value (e.g., 20) as the reference 
water level.
- After reading the water level value from the sensor, the code 
compares it with the threshold using the `cmp al, 20` 
instructions.
- If the water level is below or equal to the threshold, it is 
considered low. Otherwise, it is considered high.

### Controlling the Pump Motor:
- The project uses the control port (0300h) to control the pump 
motor.
- To turn on the pump motor, the code sets the control port in DX 
and the on value (01h) in AL.
- It then outputs the on value to the control port using the `out dx, 
al` instruction.
- This activates the pump motor, allowing it to pump water.
- Conversely, to turn off the pump motor, the code sets the control 
port in DX and the off value (00h) in AL.
- It outputs the off value to the control port, deactivating the pump 
motor.

### Water Level Monitoring Loop:
- The project uses a loop to continuously monitor the water level 
and control the pump motor.
- The number of readings to take is determined by the CX 
register, which is initially set to 5.
- The code uses the BX register as a counter to keep track of the 
current reading.
- Inside the loop, the code reads the water level, compares it with 
the threshold, and controls the pump motor accordingly.
- After each iteration, the counter is incremented, and the code 
checks if the desired number of readings has been reached.
- If not, the loop continues. Otherwise, the program exits the loop 
and proceeds to termination.

### Project Termination:
- To terminate the program, the code uses the `int 21h` instruction 
with the AH register set to 4Ch.
- This triggers a software interrupt (INT 21h) that signals the end 
of the program execution.
- After termination, the processor stops executing the program, 
and control is returned to the operating system or higher-level 
software.


