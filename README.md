# Quack40

I wanted to build a keyboard from scratch, to get a better understanding of QMK, 3d
printing and FreeCAD. So i designed my own personal 40% keyboard with FreeCAD,
3d printed the case and plate, handwired the mcu and switches and programmed
the firmware. This is the result: 

![quck40](/assets/quck40.png)


The size and plate was inspired by the QAZ keyboard. 

# Build process

## Design

Design of the layout is made with: 
https://www.keyboard-layout-editor.com

```
["Q","W","E","R","T","Y","U","I","O",{w:1.25},"P"],
[{c:"#acfcbe",w:1.25},"A","S","D","F",{c:"#cccccc"},"G","H",{c:"#acfcbe"},"J","K","L","Enter"],
[{c:"#cccccc",w:1.75},"Z","X","C","V","B","N","M","<\n.",{w:1.5},">\n."],
[{w:1.25},"Ctrl",{w:1.25},"Gui",{w:1.25},"Alt",{w:2.75},"Space",{w:1.25},"Alt",{w:1.25},"Fn1",{w:1.25},"Fn2"]
```

[kle](/assets/spacebar.json)

![plate](/assets/spacebar.png)

For the matrix i use https://kbfirmware.com/. The tool itself is outdated, but still usefull to get a idea how to setup the wireing.

![wireing](/assets/wireing.jpg)

This how i planned to connect to the mcu. 
![mcu](/assets/MCUConnections.png)

But i made a mixed up row1 and row2 and i was to lazy soldering it correctly, so
i justed modify keybord.json to fix this:

```
  "matrix_pins": {
        "cols": ["GP0", "GP1", "GP2", "GP3", "GP4", "GP5", "GP6", "GP7", "GP8", "GP9"],
        "rows": ["GP28", "GP29", "GP27", "GP26"]
    },
```

The provided source and firmware contains the planned way/code.

## Soldering

There is a guide on https://docs.qmk.fm/hand_wire how to perepare the cables.

![wireing](/assets/wireing_plate.png)

# Firmware

Vial-QMK 


[firware](/firmware/quack40_vial.uf2)

[source](/source/)

