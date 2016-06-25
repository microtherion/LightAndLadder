[KiCad](http://kicad-pcb.org) design of simple testbench for microcontrollers.

The resistor networks should be pairwise identical; I've used 680Ω for the LED resistors, with 
blue & green LEDs (note that the LEDs are connected to the closest pin, so top and bottom row are 
each connected to **both** resistor networks), and 1kΩ for the ladder resistors. 

![Schematic](https://github.com/microtherion/LightAndLadder/raw/master/LightLadder_Schematic.png)

So what is the "ladder" part good for? It's the world's most primitive analog computer, 
a.k.a a voltage divider that can be used to generate a wide 
range of fractions of VCC, according to the formula printed on the board:

![3D View](https://github.com/microtherion/LightAndLadder/raw/master/LightLadder_Board.png)

To generate a particular voltage, connect your analog input pin to one or several of the pins 
in the top row (next to the `+`) and one or several in the bottom row (next to `-`).

If VCC (applied to the `+` pin) is 5V, then

* `+1` / `-1` will generate `5V * (1 / (1+1)) = 2.5V` (as will `+2` / `-2` or `+4` / `-4`).
* `+1` / `-2` will generate `5V * (1 / (1+2)) = 1.6V`.
* `+2` / `-1` will generate `5V * (2 / (2+1)) = 3.2V`.
* `+1` / `-1,-2` will generate `5V * (1 / 1+1+2) = 1.25V`.

PCB available at [OSH Park](https://oshpark.com/projects/oy5yst8f)
