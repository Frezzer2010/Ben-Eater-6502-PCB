VGA CRT Ben-Eater-6502-PCB
My custom PCB designed to run Ben Eater's 6502 breadboard CPU with original memory map and wiring, this time with a 31x24 VGA display, and ps2 keyboard input.

!!! Disclaimer before I upload the V4 pcb and schem i made a grave mistake and reversed the CHR ROM address bits and the color bits so i had to manually scratch out the traces for that and re solder that, and i had to completly mangle the character rom data to show the tiles correctly, and becasue i used a 4 layered board i couldnt scratch out the traces for the CHR ROM... 
so yea, always double check your double check. or you'll regret it.

Why i made it:  
This PCB was primarily made because i didnt want to wire up my breadboard by hand... again. I wanted it to be portable with no loose wires, and easier to handle. I also wanted to stop having to go back and re-watch all the videos to figure out what was wrong when something did end up not working. So in the end i made 3 versions of this pcb soon to be more, each taking around a week or less.

This is the old V3 PCB:
<img width="2690" height="1816" alt="PCB_V3" src="https://github.com/user-attachments/assets/95eacfac-a85e-4015-809b-3fd6e15fa2bf" />

What does it feature:  
The CPU side of the PCB has 8 SDIP Sockets for the 8 core components, these components are enough for complex programs like WOZMON and msBASIC
(w65c02 CPU, at28c256 ROM, cy62256 RAM, w65c22 VIA, 74hc00 or 74ls00 NAND, w65c51 ACIA, 1Mhz oscillator, 1.8432Mhz oscillator)
It has breakout ports for the CPU such as bus control, interupts, cpu halting, etc.
It also has nessesary ports like the DATA and ADDRESS bus, for adding new components such as extra 6522 VIAs, or VRAM.
and the most recent addition is the ACIA pins to add RS232 interface, which i ended up using a built in max3232 USB to rs232 cord, because the max232 I got in Ben Eaters kit kepted overheating when I powered up the board and the rs232 cord in the wrong order.
and of course it has the 6522 A and B ports.

V4 PCB:

This is a remake i made of the 1991 Yoshi game for the Gameboy and Nes:
<img width="2369" height="1067" alt="20261116_112937" src="https://github.com/user-attachments/assets/0ee2198a-1c96-4060-b6c8-e2bcb6cd01e6" />


V4 Additions:
This PCB adds the VGA output in a 31x24 screen, the system actually uses a 32x24 screen but the 32nd column is cut off the screen for some reason. most likely poor code...
This PCB also adds a ps2 keyboard interface the same one used in Ben Eaters videos, take a look at his video to see how it works.
The VGA system is entirely my creation and here is how it works: the CPU is able to write to the VRAM through a retro 7134 Dual ported ram, so i can avoid scary timing diagrams for dual use ram,
and the VGA side of the system is this: the 6845 is like the loop that scans through your VRAM allowing the VRAM to output the character data by row through the raster pins, and after getting the 8bits it goes through a parallel in serial out to take the row and output each pixel, the pixel is also effected by a character sized color meaning that the whole is either going to be off (always black) or on (the color), the screen tile map memory map is located at $4000-$4300 and matching that the color map is 4400-4700 so a tile at 4000 gets the color at 4400.
the colors are 8bit 332 color meaning its 3 bits for red, 3 bits for green, and 2 bits for blue, and blue gets 2 bits because we cannot see as many distinctions between shades in blue.

I also added a buzzer to play simple sounds just like in ben's video, and used port b's 7th bit, and the keyboard takes up all of port a so only port b 0-6 is available for i/o use. 

I've taken huge inspiration from Ben Eater, MattBatWings, and Sabastian Lague for getting me hooked on retro hardware and understanding how CPU's and other electronics work. I love these guy's videos and hope they continue with more, thank you if you've enjoyed taking a look at this PCB.
