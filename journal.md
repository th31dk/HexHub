# Notebook Information
This project will use Fallout's USB hub guide. Fallout is a program by Hack Club and this project will be for this program

# Notebook Entries
## April 22nd, 2026 - Tuesday
Today, I'll be starting the tutorial for the USB hub. I'll probably make it take an input of USB A and split it into 4 USB C ports because my PC only has 2 USB ports and I often find myself needing more. 

Originally, I thought of using a USB-A as upstream, but I think that using USB-C as upstream is better because it matches. I'm not sure if it really matters, but it feels better. 

Unfortunately, I couldn't get much done today, but I did get part of my schematic done. I hope to get started on the actual PCB tomorrow!

![image](/assets/schematic_1.png)

## April 27th, 2026 - Monday
I finished the schematic! I spent a while making sure it looks neat. 

![image](/assets/schematic_2.png)

Next, I need to move on to the PCB. I want to design a case for it in the future, so I will make sure to include three M3 slots. Also, If you haven't seen my old projects, which you should definitely look at, I like hexagons.  So, I will make this hub out of hexagons.

However, as you may have noticed, hexagons only have 6 sides, and I only have 5 ports. Thinking of something to put there, I realized that my PC barely outputs any power out of the USB ports, so why not inject power? This should be relatively simple, just add another upstream USB port and don't wire up the data. 

Tada!

![image](/assets/powerinjection_1.png)

Also, while we're at it, lets just add a LED. Since my favorite color is purple, I'll make it a purple led.

It's getting quite late today, so I'll continue this tomorrow. 