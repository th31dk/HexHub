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

## April 28th, 2026 - Tuesday
Hey guys! Today, I started making the PCB!

I started today off by trying to draw out the cutout. No matter what I did, however, I could not draw a regular hexagon. After thinking for a while, I realized that I could just draw a hexagon in SolidWorks and export it as a DXF file. I tried it out, and then it worked!

Next, I wanted to look for a purple LED. I looked for one  with a lot of stock so it doesn't run out while I'm still making the PCB. I found one which I thought was a UV light because it's data sheet said that it could be used for anti bacterial uses. However, after looking at the data sheet for a few minutes, I found that it was just a deep purple. 

Moving on, I placed the LED at the center with it's resistor. I then placed all the resistors down.
![image](/assets/PCB_1.png)

Since it's now getting late, I'll stop for today and hopefully finish the PCB tomorrow!


## April 29th, 2026 - Wednesday
I'm almost done with the PCB!

Today I started by placing the rest of the components. 

I then routed the passive components. 

Then I routed the data lines. I learned that you need to route them at the same time. Although not mentioned in the tutorial, I remember that the data lines should be the same length, so I used the tuning tool in EasyEDA to make sure they were at the same length. I guess thats why router PCBs have the squiggly lines for the ethernet ports. 

Anyways, I decided to make a new board outline. It has smooth edges and 6 M3 holes. 

![image](/assets/PCB_2.png)

Finally, I started routing the 5V and ground lines. I learned that you should use a copper pour when you have a lot of components you need to supply power to. 

![image](/assets/PCB_3.png)

Tomorrow, I want to finish up the PCB and order it!

## April 30th, 2026 - Thursday
Hey guys! I finished up the PCB today!

I ran the DRC and it showed up with around 30 errors, so I had to reroute the whole PCB. The main error was that the USB-C ports were too close to the edge. 

Once I was done rerouting everything, the DRC came out as fine. So then, I asked some people to sanity check the PCB so that I was sure I didn't make any mistakes.

![image](/assets/PCB_4.png)

While they did that, I wanted to see a quote for my PCB, and I couldn't select economic PCBA for some reason, so I moved on.

When it came time to see my quote, I was guessing that it'd come out to around 13 dollars, but it was 56 DOLLARS. It probably has to do with me not selecting the economic PCBA. Anyways, I'll be back tomorrow when my PCB gets checked. 

## May 1st, 2026 - Friday
What's up guys! I got a bit of feedback today from the KiCAD discord server. So, turns out, I wired the power injection wrong. I either need to disconnect the power from my PC upstream or add a power mux IC. I think I'll just disconnect the power from my PC. Besides that, they said it was fine!

![image](/assets/schematic_3.png)

Anyways, I want to model the case next. Instead of a fully 3D printed case, I wanted to try something different this time. I want to use an acrylic top so I can see through to all the components. 

I have a feeling that standoffs in the middle will look good, so I will 6 standoffs for the holes.

Next, I want to model the USB C holes in the case, but I wanted to import the PCB from EasyEDA so that I could have a reference. Unfortunately, I couldn't export any of the components as a STEP file, so I could only export as a OBJ. This sucks because OBJ files are hollow meshes with a ton of ugly triangles. 

![image](/assets/objmesh_1.png)

I passed it through like 10 different softwares and I could still not convert it into a solid body. I think I'll just try to figure it out tomorrow.