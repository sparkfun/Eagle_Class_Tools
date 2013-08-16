# Create a Project

We'll start by making a new **project folder** for our design. In the control panel, under the "Projects" tree, right click on the directory where you want the project to live (by default EAGLE creates an "eagle" directory in your home folder), and select **"New Project"**.

-> [![How to create a project folder](https://dlnmh9ip6v2uc.cloudfront.net/assets/8/0/3/2/4/51f82d95757b7f9a1c923eb3.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/8/0/3/2/4/51f82d95757b7f9a1c923eb3.png) <-

Give the newly created, red project folder a descriptive name. How about "Bare Bones Arduino".

-> [![Project folder created](https://dlnmh9ip6v2uc.cloudfront.net/assets/b/d/6/e/c/51f82f5b757b7fb61cad2df8.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/b/d/6/e/c/51f82f5b757b7fb61cad2df8.png) <-

Project folders are like any regular file system folder, except they have a special file named "eagle.epf" within. The EPF file links your schematic and board design together, and also stores any settings you may have set especially for a project.

### Create a Schematic

The project folder will house both our schematic and board design files (and eventually our gerber files too). To begin the design process, we need to lay out a schematic[*](#asterisk).

To add a schematic to a project folder, right-click the folder, hover over **"New"** and select **"Schematic"**.

-> [![Creating a new schematic](https://dlnmh9ip6v2uc.cloudfront.net/assets/0/3/7/6/9/51f833f8757b7f371c50b50e.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/0/3/7/6/9/51f833f8757b7f371c50b50e.png) <-

A new, blank window should immediately pop up. Welcome to the schematic editor! 

---

<a name="asterisk">*</a>: It's not a requirement, but good design practice says that you should lay out your schematic before designing a PCB. The schematic exists as a reference for your board design. When the schematic and board are linked together, changes made in one design are reflected in another.

# Adding Parts to the Schematic

Overall schematic design is a two step process. First, you have to add all of the parts you're

You can intermix the steps -- add a few parts, wire a few parts, then add some more -- but since we've already got a [reference design]() we'll just add everything in one swoop.

### Using the ADD Tool -- <img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/3/1/b/0/7/5203cfa5757b7fef1a36c04a.png">

The ADD tool is what you'll use to place every single component on the schematic. It's a library navigator, where you can expand specific libraries, and look at the parts it holds. You can further expand parts with multiple packages, to find an exact component. With a part selected on the left side, the view on the right half should update to show both the schematic symbol of the part and its package, as well as a short description.

-> [![An example of navigating the ADD tool](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/b/2/1/b/f/5203d359757b7f8e1e389650.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/b/2/1/b/f/5203d359757b7f8e1e389650.png) <-

The ADD tool also has search functionality -- very helpful when you have to navigate through dozens of libraries to find a part. The search is totally literal, so don't misspell stuff! You can add wildcards to your search by placing an asterisk (\*) before and/or after your search term. For example if you search for *atmega328* you should find a single part/package combo in the SparkFun-DigitalIC library, but if you search *\*atmega328\** (note asterisks before and after), you'll discover two more versions of the IC (because they're actually named "ATMEGA328*P*"). You'll probably want to get accustomed to always adding an asterisk before and after your search term.

-> [![Searching the ADD tool. Wildcards!](https://dlnmh9ip6v2uc.cloudfront.net/assets/9/3/c/f/f/5203d4b5757b7f227ced6884.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/9/3/c/f/f/5203d4b5757b7f227ced6884.png) <-

To actually add a part from a library either select the part you want and click "OK", or double-click your part.

### Step 1: Add a Frame

The frame isn't a critical component for what will be the final PCB layout, but it keeps your schematic looking clean and organized. The frame we want should be in the SparkFun-Aesthetics library, and it's named **FRAME-LETTER**. Find that by either searching or navigating and add it to your schematic.

After selecting the part you want to add, it'll "glow" and start hovering around following your mouse cursor. To place the part, left-click (once!). Let's place the frame so its bottom-left corner runs right over our origin (the small dotted cross, in a static spot on the schematic).

-> [![Frame added](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/d/8/a/b/8/5203d92d757b7fcb7a88858c.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/d/8/a/b/8/5203d92d757b7fcb7a88858c.png) <-

After placing a part, the add tool will assume you want to add another. In this case a new frame should start following your cursor. To get out of the add-mode either hit escape (ESC) twice or just select a different tool.

### Step 2: Save (And Save Often)

Right now your schematic is an untitled temporary file living in the ether. If you go back and look at your control panel, your "Bare Bones Arduino" project folder should still be empty. To save either go to *File > Save*, or just click the blue floppy disk icon (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/e/a/f/1/b/5203da49757b7fc731edc867.png">). Name your schematic something descripting. How about "**BareBonesArduino.sch**" (SCH is the file format for all EAGLE schematics).

As a bonus, after saving, your frame title should update accordingly (you may have to move around the screen, or go to *View > Redraw*).

### Step 3: Adding the Power Input

Next we'll add four different parts all devoted to our voltage supply input. Use the add tool for these parts:

<center><table border=1 cellpadding=5>
<tr align="center"><th>Part Description</th><th>Library</th><th>Exact Part Name</th><th>Quantity</th></tr>
<tr align="center"><td><a href="https://www.sparkfun.com/products/119">5.5mm Barrel Jack (PTH)</a></td><td>SparkFun-Connectors</td><td>POWER_JACKPTH</td><td>1</td></tr>
<tr align="center"><td><a href="https://www.sparkfun.com/products/8375">0.1&micro;F Ceramic Capacitor</a></td><td>SparkFun-Capacitors</td><td>CAPPTH</td><td>1</td></tr>
<tr align="center"><td>Voltage Supply Symbol</td><td>SparkFun-Aesthetics</td><td>VCC</td><td>1</td></tr>
<tr align="center"><td>Ground Symbol</td><td>SparkFun-Aesthetics</td><td>GND</td><td>2</td></tr>
</table></center><br>

All of these parts will go in the top-left of the schematic frame. Arrange like this:

-> [![Power circuitry placed](https://dlnmh9ip6v2uc.cloudfront.net/assets/a/6/f/7/a/5203e92e757b7fc17b3d34d1.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/a/6/f/7/a/5203e92e757b7fc17b3d34d1.png) <-

If you need to move parts around, use the MOVE tool (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/2/9/0/d/e/5203de36757b7f6b28e50ad6.png">). Left-click once on a part to pick it up (your mouse should be hovering over the part's red "+" origin). Then left click again when it's where it needs to be.

### Step 4: Microprocessor and Supporting Circuitry

Next we'll add the main component of the design -- the ATmega328 microprocessor -- as well as some components to support it. Here are the parts we'll add:

<center><table border=1 cellpadding=5>
<tr align="center"><th>Part Description</th><th>Library</th><th>Exact Part Name</th><th>Quantity</th></tr>
<tr align="center"><td><a href="https://www.sparkfun.com/products/9061">ATmega328P (PTH)</a></td><td>SparkFun-DigitalIC</td><td>ATMEGA328P_PDIP</td><td>1</td></tr>
<tr align="center"><td><a href="https://www.sparkfun.com/products/10969">&frac14;W Resistors</a></td><td>SparkFun-Resistors</td><td>RESISTORPTH-1/4W</td><td>4</td></tr>
<tr align="center"><td><a href="https://www.sparkfun.com/products/9881">5mm LEDs</a></td><td>SparkFun-LED</td><td>LED5MM</td><td>3</td></tr>
<tr align="center"><td><a href="https://www.sparkfun.com/products/8375">0.1&micro;F Ceramic Capacitor</a></td><td>SparkFun-Capacitors</td><td>CAPPTH</td><td>1</td></tr>
<tr align="center"><td>Voltage Supply Symbol</td><td>SparkFun-Aesthetics</td><td>VCC</td><td>2</td></tr>
<tr align="center"><td>Ground Symbol</td><td>SparkFun-Aesthetics</td><td>GND</td><td>4</td></tr>
</table></center><br>

To rotate parts as your placing them, either select one of the four options on the rotate toolbar (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/c/e/0/3/2/5203e83d757b7fbf2b2b734d.png"</img>), or right click before placing the part. Place your microcontroller in the center of the frame, then add the other parts around that like so:

-> [![Microcontroller circuit added](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/b/4/0/c/b/5203f0ce757b7fbf2278b59a.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/b/4/0/c/b/5203f0ce757b7fbf2278b59a.png) <-

### Step 5: Adding the Connectors

Three connectors will finish off our design. One 8-pin connector to break out the analog pins, a 6-pin serial programming header, and a 2x3-pin ICSP programming header. Here are the three parts to add for this step:

<center><table border=1 cellpadding=5>
<tr align="center"><th>Part Description</th><th>Library</th><th>Exact Part Name</th><th>Quantity</th></tr>
<tr align="center"><td>8-Pin 0.1" Header</td><td>SparkFun-Connectors</td><td>M081X08</td><td>1</td></tr>
<tr align="center"><td>2x3 AVR Programming Header</td><td>SparkFun-Connectors</td><td>AVR_SPI_PRG_6PTH</td><td>1</td></tr>
<tr align="center"><td>6-Pin Serial Programming Header</td><td>SparkFun-Connectors</td><td>ARDUINO_SERIAL_PROGRAMPTH</td><td>1</td></tr>
<tr align="center"><td>Voltage Supply Symbol</td><td>SparkFun-Aesthetics</td><td>VCC</td><td>2</td></tr>
<tr align="center"><td>Ground Symbol</td><td>SparkFun-Aesthetics</td><td>GND</td><td>2</td></tr>
</table></center><br>

Finally! Here's what your schematic should look like with every part added:

-> [![Schematic with all parts added](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/4/9/2/a/1/5203f34c757b7f5e26864cd8.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/4/9/2/a/1/5203f34c757b7f5e26864cd8.png) <-

Next we'll <strike>wire</strike> net them all together.

# Wiring Up the Schematic

With all of the parts added to our schematic, it's time to wire them together. There's one major caveat here before we start: even though we're *wiring* parts on the schematic, we not going to use the WIRE (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/c/e/4/4/7/5203f995757b7f5d1eb06947.png">) tool to connect them together. Instead, we'll use the NET (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/b/e/e/9/4/5203f995757b7ff21d9d2ed7.png">) tool. The WIRE tool would be better-named as a line-drawing tool, NET does a better job of connecting components. 

-> [![Use NET not WIRE](https://dlnmh9ip6v2uc.cloudfront.net/r/400-400/assets/8/4/9/b/d/5203f942757b7fcc2bcb6ef2.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/8/4/9/b/d/5203f942757b7fcc2bcb6ef2.png) <-

### Using the NET Tool

To use the NET tool, hover over the very end of a pin (as close as possible, zoom in if you have to), and left-click once to start a wire. Now a green line should be following your mouse cursor around. To terminate the net, left-click on another pin, or an another net.

-> [![Routing GIF](https://dlnmh9ip6v2uc.cloudfront.net/assets/d/1/b/d/e/5203fd3f757b7fec1e7b81a7.gif)](https://dlnmh9ip6v2uc.cloudfront.net/assets/d/1/b/d/e/5203fd3f757b7fec1e7b81a7.gif) <-

The hard part, sometimes, is identifying which part on a circuit symbol is actually a pin. Usually they're recognizable by a thin, horizontal, red line off to the side of a part. Sometimes (not always) they're labeled with a pin number. Make sure you click on the very end of the pin when you start or finish a net route.

### Route the Power Input Circuit

Start back in the upper left, and route the power input circuit like so:

-> [![Power circuit wired up](https://dlnmh9ip6v2uc.cloudfront.net/r/400-400/assets/d/a/e/6/8/5204000a757b7f8e2d3b6d30.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/d/a/e/6/8/5204000a757b7f8e2d3b6d30.png) <-

Whenever a net splits in two directions a **junction node** is created. This signifies that all three intersecting nets *are* connected. If two nets cross, but there's not a junction, those nets *are not* connected.

### Route the ATmega328 Circuit

Next we'll route the ATmega328 to its supporting circuitry. There's LEDs, a connector, resistor, capacitor and VCC/GND symbols to route to:

-> [![Wiring the ATmega circuit](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/5/1/5/5/4/52040152757b7f42164688d4.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/5/1/5/5/4/52040152757b7f42164688d4.png) <-

Don't forget to add nets between the LEDs, resistors, and GND symbols!

### Making Named, Labeled Net Stubs

The remaining nets we have to make are not going to be as easy to cleanly route. For example, we need to connect the TXO pin on JP2 to the ATmega's RXD pin, all the way on the other side. You could do it, but it may end up looking a little ugly. Instead, we'll make net "stubs" and give them unique names to connect them.

We'll start by adding net stubs to each of the six pins on the serial connector. Begin by starting a net at a pin, just as you've been doing. Terminate the net by left-clicking a few grid-lengths over to the right of the pin. Then, instead of routing to another pin, just hit ESC to finish the route. When you're done, it should look like this:

-> [![Net stubs added to connector pins](https://dlnmh9ip6v2uc.cloudfront.net/assets/1/0/9/b/2/520403df757b7f52261a70c9.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/1/0/9/b/2/520403df757b7f52261a70c9.png) <-

Next, we'll use the NAME (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/7/a/8/f/7/5204043d757b7f2a22794ff2.png">) tool to name each of the six nets. With the NAME tool selected, clicking on a net should open a new dialog. Start by naming the net connected to the top, GND pin. Delete the auto-generated name (e.g. N$14), and replace it with "GND" (sans the quotation marks). This should result in a warning dialog, asking you if you want to connect this net to all of the other nets named "GND" (that would be every net connected to a GND symbol). Thanks for looking out for us EAGLE, but in this case *Yes* we do want to connect GND to GND.

After naming a net, you should use the LABEL (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/7/6/7/e/a/52040571757b7f852a55619e.png">) tool to add a label. With the LABEL tool selected, left-click on the net you just named. This should spawn a piece of text that says "GND", left-click again to place the label down right on top of your net.

Follow that same order of operations for the remaining five net stubs. In the end, they should look like this (note the net connected to the TXO pin is named "RX", and a "TX" net connects to RXI -- that's on purpose):

-> [![Net stubs named and labeled](https://dlnmh9ip6v2uc.cloudfront.net/assets/0/f/a/7/b/52040644757b7fe37c0e7eb3.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/0/f/a/7/b/52040644757b7fe37c0e7eb3.png) <-

VCC should be the only other net that warns you that you'll be connecting to other nets named "VCC" (anything connected to a VCC voltage node). For the other named nets, we'll need to create this same stub somewhere else. Where exactly? Well, we need to add a "RX" and "TX" net on the ATmega328, and a "DTR" nearby as well:

-> [![Naming and labeling RX, TX, and DTR](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/7/0/7/8/6/520407b6757b7fbc483a5576.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/7/0/7/8/6/520407b6757b7fbc483a5576.png) <-

Even though there's no green net connecting these pins, every net with the *same, exact* name is actually connected.

We need to do a lot of the same to connect the 2x3 programming header to the ATmega328. First, wire up the connector like so (naming/labeling MOSI, MISO, SCK, and RESET):

-> [![ICSP connecter wired](https://dlnmh9ip6v2uc.cloudfront.net/assets/4/f/a/3/1/5204086b757b7f191d9ae71b.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/4/f/a/3/1/5204086b757b7f191d9ae71b.png) <-

Then, back to the ATmega328, add the same four named/labeled nets:

-> [![ATmega328 SPI pins named/labeled](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/5/8/a/c/6/520409f2757b7f4d23f5fd6f.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/5/8/a/c/6/520409f2757b7f4d23f5fd6f.png) <-

Phew -- you're done. Get excited, it's about time to lay out a PCB! When your schematic is done, it should look a little something like this:

-> [![Final schematic](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/a/c/0/a/c/52040a3b757b7f04237ab526.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/a/c/0/a/c/52040a3b757b7f04237ab526.png) <-

### Tips and Tricks: Verifying Connections

The SHOW (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/9/1/f/b/c/52040f2f757b7f127bc3e13a.png">) tool is very useful for verifying that pins across your schematic are connected correctly. If you use SHOW on a net, it and everything else it's connected to should light up. If you're dubious of the fact that two like-named nets are connected, give the SHOW tool a try. SHOWing a net connected to GND, for example, should result in a lot of GND nets lighting up.

-> [![SHOWing a GND trace](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/6/c/e/6/2/52040ea7757b7f42162b3e74.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/6/c/e/6/2/52040ea7757b7f42162b3e74.png) <-

As an alternative to show, you can temporarily MOVE a part a part to make sure nets are connected to it. Use MOVE to pick a part up, and the nets connected to it should bend and adjust to remain so. Just make sure you hit ESC to *not* move the part (or UNDO if you accidentally move it).

-> [![Moving a part to verify a connection](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/b/b/8/3/3/5204102b757b7f1d7b39aab5.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/b/b/8/3/3/5204102b757b7f1d7b39aab5.png) <-

-> *If all the nets connected to a part MOVE with it, all connections are good.* <-

If a net isn't moving along with the part, it's not connected to the pin correctly. Double check to make sure you routed to the very end of the pin, and not a bit further:

-> [![Poorly routed net](https://dlnmh9ip6v2uc.cloudfront.net/r/600-600/assets/0/1/9/8/2/5203fcf6757b7f1d4f77a9e9.png)](https://dlnmh9ip6v2uc.cloudfront.net/assets/0/1/9/8/2/5203fcf6757b7f1d4f77a9e9.png) <-

If you've got any nets like above, DELETE (<img src="https://dlnmh9ip6v2uc.cloudfront.net/assets/5/4/d/c/d/520410b9757b7f237ca2a740.png">) it, and try re-netting.

# Tips and Tricks

### Adding Text

### Group Moving

### Adding Values

### Copy/Paste

### Smashing