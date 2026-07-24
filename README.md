# Ben-Eater-6502-PCB
My custom PCB designed to run Ben Eater's 6502 breadboard CPU with original memory map and wiring.

Why i made it:  
This PCB was primarily made because i didnt want to wire up my breadboard by hand, again. I wanted it to be portable with no loose wires, and easier to handle. I also wanted to stop having to go back and re-watch all the videos to figure out what was wrong when something did end up not working. So in the end i made 3 versions of this pcb soon to be more, each taking around a week or less.

<img width="2690" height="1816" alt="PCB_V3" src="https://github.com/user-attachments/assets/95eacfac-a85e-4015-809b-3fd6e15fa2bf" />

What does it feature:  
The PCB has 8 SDIP Sockets for the 8 core components, these components are enough for complex programs like WOZMON and msBASIC
(w65c02 CPU, at28c256 ROM, cy62256 RAM, w65c22 VIA, 74hc00 or 74ls00 NAND, w65c51 ACIA, 1Mhz oscillator, 1.8432Mhz oscillator)
It has breakout ports for the CPU such as bus control, interupts, cpu halting, etc.
It also has nessesary ports like the DATA and ADDRESS bus, for adding new components such as extra 6522 VIAs, or VRAM.
and the most recent addition is the ACIA pins to add RS232 interface, which i ended up using a built in max3232 USB to rs232 cord, because the max232 I got in Ben Eaters kit kepted overheating when I powered up the board in the wrong order.
and of course it has the 6522 A and B ports.

What will i add in the future:  
I plan on creating a new PCB adding the Motorola 6845 crt controller and other decode logic for VGA interface.
I also want to create a plastic housing/protective case for better portabilty, and just asthetics.

I've taken huge insperation by Ben Eater and getting me hooked on retro hardware and understanding how CPU's and other electronics work. I love his videos and hope he continues with more, thank you if you've enjoyed taking a look at this PCB, and if you would like for me to continue.
