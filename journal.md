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

## May 2nd, 2026 - Saturday
ALright, let's start converting the mesh to a solid body file. I saw that fusion 360 could convert meshes to solid bodies pretty well, so I wanted to try that first. 

Unfortunately, Fusion360 did not work, even after 30+ minutes of trying to convert. It degraded the model a lot when I tried to simplify the mesh. 

Then, I moved onto FreeCAD. FreeCAD seemed better, but the mesh was too complicated. I saw that people would simplify it in MeshLab before importing into FreeCAD, but MeshLab just ruined the quality more than Fusion360 did. 

As a last ditch effort, I tried to export out of EasyEDA again, but it didn't work. I contacted customer support. While I was waiting, I wondered if I could import from their desktop client. I think their desktop client runs more client sided than their web version, so I was hoping that it would automatically download their models onto my PC or something. 

Drumroll please!

IT WORKED! I imported it into SolidWorks, and it looked amazing!

Next, I want to finish the bottom case of the hub. I made the walls of it 2mm because I wanted it to be sturdy, but still thin. After sketching, I extruded it to approximately where it would be. 

![image](/assets/bottomCase_1.png)

I then imported the new PCB model. I thought it looked pretty good, so I extruded the walls. However, I quickly realized I need to cut holes for the USB ports and the cable.

![image](/assets/assembly_1.png)

I also realized that I need to split the case in half, otherwise, I won't be able to put the PCB inside. 

![image](/assets/bottomCase_2.png)

Unfortunately, the USB port wasn't fully aligned with this hole, so I had to go back and re edit the PCB.

When I was placing the components, I eyeballed the center of each side and just put the USB port there. However, I was very wrong. I originally wanted to use trigonometry to find the exact coordinates. This ended up taking too much time and my brain power so I went back to eyeballing it. I would find the midpoint of a line and move the USB to there. Then, I would rebuild the copper pour and it would leave an imprint of where the feet were. Then I would slowly tune the coordinates of the port so that it would be as close to the edge as possible and still match up with the angle of the imprints. Once I found those coordinates, I would just mirror those coordinates to all 4 of the unaligned USB ports. 

Now, since I moved the ports, I have to reroute basically everything, so I spent a solid hour rerouting until...

![image](/assets/PCB_5.png)

Okay, we're done with the PCB, hopefully forever. Let's keep designing the case. 

![image](/assets/assembly_2.png)

It fits! I went ahead and modeled the rest of the holes. 

Now, before I model the top part, I wanted to model the acrylic top. At first, I thought I had to do a special drawing thing for it, but I just need to sketch it out and export as a DXF. I extruded it to 1/8th inch like the acrylic I was gonna use for it.

![image](/assets/topCase_1.png)

Then, I modeled the standoffs, screws, and nuts for the case. The smallest standoff I could find was a M3*6+6 standoff, so I decided to use that. This means my case needs to be around 6mm thick at the bottom. 

![image](/assets/assembly_3.png)

For the nuts, I just cut out a hole at the bottom so that they could fit in. 

![image](/assets/assembly_4.png)

Well, that's all I really did today, I wanna try and finish the project tomorrow and maybe submit over the weekday. 