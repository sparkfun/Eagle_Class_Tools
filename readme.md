Note: to delete previous settings delete "Cadsoft" folder in "C:\Users\jim.lindblom\AppData\Roaming"

### Download and Install Eagle

Link: [http://www.cadsoftusa.com/download-eagle/?language=en](http://www.cadsoftusa.com/download-eagle/?language=en)

File Name: eagle-win-6.4.0.exe (Windows), eagle-mac-6.4.0.zip (Mac)

1. Run WinZip Self-Extractor.
2. Setup (Wait about a minute).
3. Next on Welcome Screen.
4. Yes to license agreement.
5. Decide destination directory, Click Next
6. Click next to start copying files. Wait a minute.
7. Select "Run as Freeware". Click Next.
	* Freeware limitations? !!! TODO
8. Click Finish.

### Run Eagle for First Time

Click "Yes" to any/all directory creations

### Setting Up the Control Panel

1. Overview about each tree.
	* Click on an example in each tree, and show how information panel changes.
	* Explain green dots.
2. Show "Directories" Dialog
	* Options > Directories
	* Point Libraries to our library folder (.../Eagle Class Files/lbrClass). In addition to current directory.
	* Point Scripts to our folder (.../Eagle Class Files/scrClass). In addition to current directory.
	* Show how lbrClass and scrClass directories are added to tree view.
3. Set Libraries to USE NONE from default folder. Make sure lbrClass folder is used.
	* Explain why we won't be using default libraries. Too overwhelming.
	* Right-click **Libraries** tree, click **Use None**.
	* Should make all green dots go away.
	* Talk a bit more about library. Expand and look at parts. This is a good place to explain symbiosis between board and package.
4. Create a New Project
	* Right click "eagle" folder. Select **New Project**. Title folder "Bare Bones Arduino".
	* Explain difference between regular folder, and project folder.
	* Explain green dot again.
5. Create a Schematic in Project
	* Right click project folder. Select **New > Schematic**.
	* Schematic editor should open

### Schematic: Add tool. Moving around the frame. Adding a frame.

1. Explain the Schematic Editor View
	* Explain **toolbar**. We'll talk more in-depth about each tool as we encounter it.
	* Every tool can also be accessed from Draw, View, Tools menu.
2. Add a frame.
	* Click "Add" button (looks like And gate, with black arrow over it). Also found under **Edit** menu.
	* Explain what add tool does.
	* Should only be one library -- spk1 -- in add view. **Ask if people see more/not spk1.**
	* Expand spk1. Select **FRAME-LETTER**. Either double-click it, or select and click OK.
	* Frame will "Glow" and follow mouse around. Move mouse over dotted cross (origin) and **LEFT CLICK** to place the frame. 
	* Another frame will follow mouse around. We don't want to place another, so **Hit ESC**.
	* Hit ESC again to get out of add view
3. Explain grid/origin
	* Set the grid with "Grid" tool (icon under open). Also under View menu.
	* Show where mouse coordinates are displayed.
4. Explain how to navigate with mouse around schematic.
	* Middle mouse button zooms in/out
	* Hold middle mouse down, and drag mouse to move around screen.
	* If student doesn't have a mouse, view tools become useful. Show where zoom in/out, zoom to fit, and zoom select are.
5. Save schematic -- file name bareBonesArduino.sch
	* After saving, you can hit "Redraw". The title will be added to the frame. Date wil be updated.

### Add Power Input Circuitry. Making the first wires. Moving parts.

1. Add POWER_JACKPTH
	* Explain why different footprints for jack.
	* Add to top left of frame.
	* Hit ESC, ESC to get out
	* Explain value and name parameters.
2. Add Capacitor
	* CAP > CAPPTH
	* Place near the jack. ESC, ESC
3. Add two Ground Nodes
	* One below jack. One below cap.
4. Add one VCC node
	* Above cap.
5. Net VCC
	* Explain why use "Net" tool, and not "Wire"
	* Explain how the net tool works.
	* Start at a "Pin" (explain how to recognize pins, different parts have different amounts of pins), and finish at another pin.
	* Wire from barrel Jack + to top of cap.
	* Can also start on net. Always need to finish at a pin (or else hit ESC).
	* Wire from net bend to VCC pin.
	* When connecting more than two pins to a net, a Warning dialog will pop up. Usually, you'll have meant to merge the pins to one net, so click Yes.
	* A node junction should be created when creating a three-way junction.
6. Net GND
	* to pins to route on barrel jack to GND node
	* Route bottom fo cap to GND
7. Explain the MOVE tool
	* Moving a part is a good way to check if nets are connected.

### Create a Board File. Setup environment by running script.

1. Click the "Generate/switch to Board" tool. Under the File menu.
	* If board is being created, it'll ask if you want to. Click Yes.
2. New Board should be created with the parts we've added.
3. Explain the ratsnest wires.
4. Run script file -- spk.scr
	* May need to navigate to script directory (Eagle Class Files/scrClass)
	* This should turn background black. Explain why we like to differentiate. Show how this can be adjusted.
5. Save board. And go back to schematic. 

### Add ATmega328

1. Add: AVR-MEGA8-PPTH
	* Place it in the center of schematic
2. Bring board back up. Show that ATmega was added there as well.
3. Don't close board! Explain why don't close board! Explain green dots.

### Adding resistors. Group Move. Value tool. Rotating parts.

1. Add three resistors (RESISTORAXIAL-0.3)
	* One vertical near reset pin.
	* Three to lower-right portion of sheet
	* ESC ESC
	* Show how names are being auto-incremented. 
	* Add values to resistors. 10k on reset, 220 on LEDs.
	* We also need to go back and **value capacitor**(0.1uF)
2. Add three LEDs (LED5MM)
	* Place them below the resistors
3. Need to group move LEDs.
	* Group LEDs
	* Select Move tool
	* Point out status bar text directions.
	* Hold ctrl+right click to move group.
	* Move group of LEDs on top of resistor.
4. Add a capacitor (CAPPTH)
	* We want cap to go horizontally.
	* Right click once to rotate cap 90&deg;.
	* Can also use rotation (quadrant) tools top left.
	* Place cap to left/bottom of reset resistor. Pins even with reset pin.
	* Value cap at 0.1uF
5. Add 6-pin connector (FTDI_BASICPTH)
	* Place in bottom left
6. Add 8-pin connector (M081X08)
	* **Flip the part** by middle clicking.
	* Place in top-right of frame.
7. Add AVR programmer (AVR_SPI_PRG_6PTH)
	* Place below AVR
8. Add 5 GNDs
	* One for AVR
	* One for ISP
	* Three for LEDs
9. Add 3 VCCs
	* One for AVR
	* One for reset pull-up
	* One for ISP

### Wire up the remaining parts -- Naming nets

1. Reinforce using NET tool!
2. Start on LEDs. Same as before. Go from AVR to LED (PB0, PB1, PB2). LED to resistor. resistor to GND.\
3. Wire up VCC and GND on AVR
	* Make sure nodes appear!
3. Wire up reset circuit
	* Resest pin to resistor and capacitor
	* Resistor pulled up to 3.3V
	* Wire to nowhere (about three grid spaces) on other end of cap.
4. Name your first net
	* Name net DTR
	* Use label tool to add name to net.
5. Wire up serial header.
	* Make six nets. Name all accordingly. Label each net.
	* Can label before naming.
	* Nets that are already named will ask if you want to make the connection. Good sign. Click yes.
6. Label RX and TX on AVR 
	* Use **Show tool** to show that pins are connected.
7. Wire up ISP connector
8. Make MISO, MOSI, SCK, RESET nets on AVR
9. Add connections to A0-A5 and VCC, GND on 8-pin header
10. Make same (analog) connections on AVR.

TA DA!

### Arrange parts on board. Fit dimensions layer.

1. Switch to board editor
	* DON'T CLOSE SCHEMATIC!
2. All parts should have been added to editor as well.
3. Explain visible layers: dimensions, via, tsilk, tdoc, ratsnest.
4. Move ATmega328 to middle of board.
	* Have to click part origin to move it.
	* Use right click to rotate
	* Note on how airwires remain attached.
5. Arranging parts is all about making our routing easier. Try to criss-cross airwires as rarely as possible.
6. Move 8-pin analog header to right of IC.'
	* Show how much more difficult it'll be if rotated incorrectly.
7. More LEDs, arrange resistors nearby.
	* Explain why the green dots can't overlap (it's copper!)
8. Place ISP header.
	* Overlaps are inevitable.
9. Place serial 6-pin header.
10. Move DTR cap near serial header.
11. Move pull-up resistor between DTR and reset pin.
12. Add barrel jack and decoupling cap to top left of board.
	* Explain barrel jack's tDoc layer.
13. Adjust dimension layer lines to better fit our board.
14. Can group move entire board to align bottom left with origin.
15. Contest to have smallest, routed board?

### Start Routing

1. Explain top and bottom layers.

### Auto-router

###