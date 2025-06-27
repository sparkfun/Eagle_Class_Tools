# Introduction

Printed circuit boards (PCBs) are the backbone of every electronic gizmo out there. They're not flashy like those microprocessors, or abundant like resistors, but they're essential to making all components in a circuit connect together just right.

We LOVE designing PCBs here at SparkFun. It's a love that we want to spread. It's a skill that benefits electronics enthusiasts of every caliber. Through this and a series of tutorials, we'll explain how to design a PCB using EAGLE -- the same software we use to design all of our PCBs.

-> [![alt text](https://cdn.sparkfun.com/r/600-600/assets/2/d/1/2/b/51f829f4757b7fa81c1345d7.png)](https://cdn.sparkfun.com/assets/2/d/1/2/b/51f829f4757b7fa81c1345d7.png) <-

This first tutorial goes over how to install the software, and custom-tailor its interface and support files.

### Why EAGLE?

EAGLE is one of many PCB CAD softwares out there. So you might ask: "What makes EAGLE so special?" We're fond of EAGLE for a few reasons in particular:

* **Cross-platform** -- EAGLE can run on anything: Windows, Mac, even Linux. This is a feature not too many other PCB design softwares can boast.
* **Lightweight** --  EAGLE is about as svelte as PCB design software gets. It requires anywhere from 50-200MB of disk space (compared to the 10+GB more advanced tools might require). The installer is about 25MB. So you can go from download to install to making a PCB in minutes.
* **Free/Low-Cost** -- The freeware version of EAGLE provides enough utility to design almost any PCB in the SparkFun catalog. An upgrade to the next license tier (if you want to make a profit off your design) costs at least two orders of magnitude less than most high-end tools.
* **Community support** -- For those reasons, and others, EAGLE has become one of the go-to tools for PCB design in the hobbyist community. Whether you want to study the design of an Arduino board, or import a popular sensor into your design somebody has probably already made it in EAGLE and shared it.

Of course, EAGLE has its drawbacks too. More powerful (also read: "expensive") PCB designers out there might have a better autorouter, or useful tools like simulators, programmers, and 3D viewers. For us though, EAGLE has everything we need to design simple-to-intermediate PCBs. It's an excellent place to start if you've never designed a PCB before.

### Recommended Reading

Here are a few tutorial and concepts you may want to familiarize yourself with, before dropping down into this rabbit hole:

* [PCB Basics](tutorials/7)
* [How to Read a Schematic?](tutorials/91)
* [Voltage, Current, Resistance, and Ohm's Law](tutorials/27)

# Download, Install, Run

EAGLE is available on Cadsoft's (the developer company) [download page](http://www.cadsoftusa.com/download-eagle/). Grab the most recent version that matches your operating system (the software is available for Windows, Mac and Linux). It's a relatively light download -- about 45MB.

EAGLE installs just like any old program, it'll self extract and then present you with a series of dialogs to configure the installation.

### Licensing EAGLE

One of our favorite things about EAGLE is that it can be used for **free**! There are a [few limitations](http://www.cadsoftusa.com/download-eagle/freeware/) to be aware of when using the free version:

* Your PCB design is limited to a maximum size of 100 x 80mm (3.94 x 3.15in). Even with those restrictiosn 12.4 in<sup>2</sup> is a huge amount of PCB real estate. Even if you're designing a big 'ol [Arduino shield](tutorials/40) (usually measuring around 2.1 x 2.7 in<sup>2</sup>), you'll still be well under the maximum size.
* Only a two signal layers allowed. If you need more layers check into the Hobbyist or Standard licenses.
* Can't make multiple sheets in your schematic editor.
* Limited to email or [forum](http://www.cadsoftusa.com/forums/?language=en) support.
* For **non-profit** use only. If you're going to go out and sell your design, maybe check into the "Light" version of the software.

Those limitations still make EAGLE an amazing piece of software. Engineers here at SparkFun could design 99% of our boards using the freeware version, if not for that pesky non-profit stipulation. You still have access to all phases of the EAGLE software, including the Autorouter.

If, for any reason, you need to upgrade your license there are a [variety of options](http://www.cadsoftusa.com/shop/pricing/?language=en) out there. Most licenses are still incredibly low priced (in comparing to the other stuff out there).

### Exploring the Control Panel

The first time you open up EAGLE, you should be presented with the **Control Panel** view. The Control Panel is the "homebase" for Eagle, it links together all of the other modules in the software.

-> [![Control Panel Overview](https://cdn.sparkfun.com/r/600-600/assets/7/3/6/0/7/51f6c679ce395f756e000000.png)](https://cdn.sparkfun.com/assets/7/3/6/0/7/51f6c679ce395f756e000000.png) <-

You can explore the six separate trees in the control panel: Libraries, Design Rules, User Language Programs (ULPs), Scripts, CAM Jobs, and Projects. If you select a file in a tree, information about it will appear in the right-hand portion of the window. This is a great way to explore parts in libraries, project designs (EAGLE comes with some fun examples), or to get a good overview of what a certain script's funciton is.

-> [![Exploring the Control Panel View](https://cdn.sparkfun.com/r/600-600/assets/7/2/c/b/9/51f6c788ce395fff6e000005.png)](https://cdn.sparkfun.com/assets/7/2/c/b/9/51f6c788ce395fff6e000005.png) <-

# Using the SparkFun Libraries

Included with EAGLE is an impressively long list of part libraries, which you can explore in the Control Panel view. There are hundreds of libraries in here, some devoted to specific parts like resistors, or NPN transistors, others are devoted to specific manufacturers. This is an amazing resource! But it can also be a bit overwhelming. Even if you just want to add a simple through-hole electrolytic capacitor, there are dozens of libraries and parts to sort through to find the right thing.

Instead of using the hundreds of default libraries, you can use the [SparkFun EAGLE Libraries](https://github.com/sparkfun/SparkFun-Eagle-Libraries). Our libraries are like a curated version of the default libraries included with Eagle. They're filtered down to only include the parts that we've used in designs ourselves. And they're constantly updated with new parts we've found.

Here's how you can opt to use the SparkFun libraries instead of the default ones:

### Step 1: Download the SparkFun Libraries

The most recent version of the libraries can be found on [the GitHub repository](https://github.com/sparkfun/SparkFun-Eagle-Libraries). For more help using GitHub, check out our [Using GitHub](tutorials/11) tutorial. Basically, all you'll need to do from the main repository page is **click "Download ZIP".**

-> [![Downloading from github](https://cdn.sparkfun.com/r/600-600/assets/5/9/a/9/c/51f6d74fce395f5c67000006.png)](https://cdn.sparkfun.com/assets/5/9/a/9/c/51f6d74fce395f5c67000006.png) <-

Save the ZIP file somewhere handy. And extract the folder. Don't forget where it is!

### Step 2: Updating the Directories Window

Back to the EAGLE Control Panel window now. Go to the **"Options" menu** and then **select "Directories"**. This is a list of computer directories where EAGLE looks when it populates all six objects in the tree view...including libraries.

-> [![Opening the directories dialog](https://cdn.sparkfun.com/r/600-600/assets/7/3/a/7/0/51f6d989ce395fd16d000004.png)](https://cdn.sparkfun.com/assets/7/3/a/7/0/51f6d989ce395fd16d000004.png) <-

In the "Libraries" box is where we'll add a link to the directory where the SparkFun EAGLE libraries are stored. There are a few options here. Add a semicolon (;) after "$EAGLEDIR\lbr" and paste the SparkFun EAGLE Libraries directory location after that.

-> [![Adding the SparkFun EAGLE libraries directory](https://cdn.sparkfun.com/assets/f/6/e/3/6/51f6e9f3ce395f526e000002.png)](https://cdn.sparkfun.com/assets/f/6/e/3/6/51f6e9f3ce395f526e000002.png) <-

### Step 3: "Using" Libraries

Now, when you go back and look at the "Libraries" tree, there should be two folders included, one of which should be our SparkFun Eagle Libraries. The last step is to tell EAGLE that, for now at least, we don't want to use the default libraries. To do this, right click on the "lbr" folder, and select **"Use none"**.

-> [![Un-using the default libraries](https://cdn.sparkfun.com/assets/3/3/f/4/a/51f6ea91ce395f8269000004.png)](https://cdn.sparkfun.com/assets/3/3/f/4/a/51f6ea91ce395f8269000004.png) <-

Then, right-click on the "SparkFun-Eagle-Libraries-master" folder, and select **"Use all"**. Then check the libraries in each of the two folders. Next to them should be either a grey or green dot. A green dot next to a library means it's in use, a grey dot means it's not. Your libraries tree should look a little something like this:

-> [![Correctly set libraries tree. Default lbr's not active, SparkFun lbrs ready to go!](https://cdn.sparkfun.com/r/600-600/assets/6/e/b/b/f/51f6eb55ce395fee66000007.png)](https://cdn.sparkfun.com/assets/6/e/b/b/f/51f6eb55ce395fee66000007.png) <-

# Open a Project and Explore

EAGLE is packaged with a handful of nifty example PCB designs. Open one up by expanding the "Projects" tree. From there, under the "examples" folder open up the "arduino" project by double-clicking the red folder (or right-clicking and selecting "Open project"). Note that, in this view, project folders are red and regular folders are the standard yellow.

-> [![Opening a project](https://cdn.sparkfun.com/assets/f/7/9/3/0/51f7e46f757b7f6528767828.png)](https://cdn.sparkfun.com/assets/f/7/9/3/0/51f7e46f757b7f6528767828.png) <-
    
Opening the project should cause two more EAGLE windows to spawn: the board and schematic editors. These are the yin and the yang of EAGLE. They should be used together to create the finished product that is a functional PCB design.

-> [![Board and schematic view both open](https://cdn.sparkfun.com/r/600-600/assets/b/1/3/0/5/51f80387757b7fcd1cdd54c9.png)](https://cdn.sparkfun.com/assets/b/1/3/0/5/51f80387757b7fcd1cdd54c9.png) <-

-> *Schematic (left) and board editors both open. Click to embiggen.* <-

The **schematic editor** (on the left above) is a collection of red circuit symbols which are interconnected with green nets (or wires). A project's schematic is like the comments in a program's code. It helps tell the story of what the board design actually does, but it doesn't have much influence on the end product. Parts in a schematic aren't precisely measured, they're laid out and connected in a way that's easy to read, to help you and others understand what's going on with the board design.

The **board editor** is where the real magic happens. Here colorful layers overlap and intersect to create a precisely measured PCB design. Two copper layers -- red on top, blue on the bottom -- are strategically routed to make sure different signals don't intersect and short out. Yellow (by default, but usually green) circles called "vias" pass a signal from one side to the other. Bigger vias allow for through-hole parts to be inserted and soldered to the board. Other, currently hidden, layers expose copper to create pads for surface mount parts.

### Keep Both Windows Open!

Both of these windows work hand-in-hand. Any changes made to the schematic are automatically reflected in the board editor. Whenever you're modifying a design it's important to **keep both windows open at all times**.

If, for instance, you closed the board window of a design, but continued to modify a schematic. The changes you made to the schematic wouldn't be reflected in the board design. This is bad. The schematic and board design should always be consistent. It's really painful to backtrack any changes in an effort to bring back consistency. **Always keep both windows open**!

There are a few ways to tell if you don't have consistency between windows. First, there's a "dot" in the lower-right hand corner of both windows. If the dot is green, everything is groovy. If the dot is magenta, a window's probably closed that shouldn't be. Second, and more obvious, if you close either of the two windows a big, huge warning should pop up in the other:

-> [![Annotation severed warning. Eeep!](https://cdn.sparkfun.com/assets/2/0/c/0/f/51f7fefb757b7fda1c200df7.png)](https://cdn.sparkfun.com/assets/2/0/c/0/f/51f7fefb757b7fda1c200df7.png) <-

If you see that warning STOP doing anything, and get the other window back open. The easy way to get either a board or schematic window back open is by clicking the "Switch to board/schematic" icon -- <img src="https://cdn.sparkfun.com/assets/9/d/5/1/e/51f7ffa8757b7f9b1cbfa1d1.png"> / <img src="https://cdn.sparkfun.com/assets/a/9/a/d/1/51f7ffa8757b7fa71e5ccb8d.png"> (also found under the "File" menu).

### Navigating the View

This is a subject that's usually glazed over, but it's important to know how to navigate around both of these windows.

To move around within an editor window, a **mouse with a scroll wheel** comes in very handy. You can zoom in and out by rotating the wheel forward and backward. Pressing the wheel down, and moving the mouse allows you to drag the screen around.

If you're stuck without a three-button mouse, you'll have to resort to the view options to move around the editor views. All of these tools are located near the middle of the top toolbar, or under the "View" menu. The zoom in -- <img src="https://cdn.sparkfun.com/assets/6/d/a/f/a/51f7f84c757b7f6f1c062323.png"> -- and zoom out -- <img src="https://cdn.sparkfun.com/assets/7/5/d/2/e/51f7f84c757b7f531c9bc863.png"> -- tools are obviously handy. So is the "Zoom select" tool -- <img src="https://cdn.sparkfun.com/assets/1/9/a/9/9/51f7f84c757b7fa91c01d54e.png"> -- which alters the view to your selection. But really, if you're serious about using EAGLE...get a mouse!

# Configuring the UI

EAGLE's user interface is highly customizable. Anything from the background color, to layer colors, to key bindings can be modified to fit your preference. Better tailoring your interface can make designing a PCB much easier. On this page we'll talk about how we at SparkFun prefer to customize our UI. None of these steps are required. Customize your UI as you see fit. These are just the settings that we've grown accustomed to.

### Setting the Background Color

The first adjustment we always make to the UI is the background color of the board editor. The standard white background doesn't always meld very well with the array of colored layers required for board design. Instead, we usually opt for a black background.

To change the background color, go up to the "Options" menu and select "User interface".

Inside the "Layout" box you can set the background to black, white, or a specific color.

-> [![Adjusting the user interface](https://cdn.sparkfun.com/assets/4/2/6/b/4/51f7e72f757b7ff124594ec8.PNG)](https://cdn.sparkfun.com/assets/4/2/6/b/4/51f7e72f757b7ff124594ec8.PNG) <-

There are other options in this box to be explored, but you may want to hold off on adjusting most until you have more experience with the software.

### Adjusting the Grid

Another UI improvement we like to make in the board editor is turning the grid on. Dimensions and sizes are so important to the design of your PCB, having some visible reminders of size can be very helpful. To turn the grid view on, click the <img src="https://cdn.sparkfun.com/assets/f/4/e/b/3/51f7e841757b7f30250556f5.png"> icon near the top-left corner of the board window (or go to the "View" menu and select "Grid").

-> [![Adjusting the grid](https://cdn.sparkfun.com/assets/f/6/4/1/3/51f7e981757b7f41251f9ac7.png)](https://cdn.sparkfun.com/assets/f/6/4/1/3/51f7e981757b7f41251f9ac7.png) <-

Switch the "Display" radio button over to "On". We'll also make the grid a bit less fine by setting the "Size" to 100 mil and "Alt" to 50 mil.

### Running Scripts

Scripts are a much more streamlined way to quickly configure your interface. With one click of the button, you can automatically set up all of your colors and key binds. Script files can also be shared, and run by anyone. Running the SparkFun EAGLE script will get your UI to exactly match ours.

First, click [here](https://cdn.sparkfun.com/assets/5/2/6/e/e/51f7f30e757b7fc71c666640.zip) to download the script (in a zip folder). Unzip the "spk.scr" file to a location you'll remember.

Then you'll need to run the script. In the board window click on the <img src="https://cdn.sparkfun.com/assets/3/c/6/8/5/51f7ee2e757b7fbe1c83a90f.png"> (script) icon (or go to "File" then "Execute Script"). In the file browser, select the "spk.scr" file you just downloaded and unzipped.

This should automatically set up your color scheme to look a little something like this:

-> [![Board view after running script](https://cdn.sparkfun.com/r/600-600/assets/a/a/8/1/8/51f7f354757b7f391c9e2b52.png)](https://cdn.sparkfun.com/assets/a/a/8/1/8/51f7f354757b7f391c9e2b52.png) <-

This UI setup is presents a nice logical view of the layers. The important copper layers are very visible, but distinct (red on top, blue on bottom, green for vias), and the silkscreen is white as it is on most PCB designs.

All of these colored layers will make more sense as you continue to use and explore EAGLE. 
