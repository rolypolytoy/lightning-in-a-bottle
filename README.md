# Lightning In A Bottle

Lightning in a bottle is an open-source, low-cost charge sensitive amplifier with several improvements over all existing commercial designs.

It has a >2x lower cost, a 750x greater gain, >5x greater bandwidth, >50% lower cost, and sub-5 dB lower SNR, which is entirely offset by the reduction in noise caused by the greater degree of amplification it provides. It also uses standard +5V as its power source rather than the weird +-6V-13V supplies the Cremat module needs.

It also uses commercial off-the-shelf components and so can be more easily and cheaply scaled than the Cremat CR-113 and other modules, whose components are proprietary and who may not ship to every country in the world in a timely manner.

Components:
- LMH6629SD, an ultra-low noise Op-Amp
- TPS7A3301RGW for power regulation
- Several miscellaneous ceramic capacitors, SMD resistors, inductors, and other generic components.

Powered by +5V, it has an estimated rise time of well below 10nS and a decay time of around 10 microseconds, and displays the typical charge spike + comedown typical of op-amp integrator setups.

You can use a typical RC-CR pulse shaper or buy one from Cremat (might replace it soon but the CR-200-500ns arrived, so I don't need to make another one), but the specs of that are less important than the CSA setup. CSAs are better than transimpedance amplifiers for electron detection and nuclear research.

The [Cremat CR-113's datasheet](https://www.cremat.com/CR-113-R2.1.pdf) shows 18k electrons RMS baseline noise, 1.3 mV/pC gain and 30 electrons of noise RMS per pF, which means for the 0.01 microfarad AC coupled capacitor they show in their datasheet means they'll have around 300,000 electrons RMS of noise- which is a LOT of noise. Our SNR?

Op-amp voltage noise is 0.69 nV/√Hz (LMH6629), our feedback capacitor: Cf = 1pF, our feedback resistor: Rf = 10MΩ, our bandwidth: f = 1/(2π × Rf × Cf) = 1/(2π × 10MOhm × 1pF) = 15.9 kHz. Voltage noise is 0.69 nV/√Hz × √(15,900 Hz) = 0.69nV * 126 = 87 nV RMS voltage noise. Our gain is 1/Cf = 1/(1pF) = 1e12 V/C = 1000 mV/pC which is 750 times their gain. Our charge noise is thus 87nV / (1V/pC) = 87fC RMS, which is ~543,000 electrons, which is about a ~5 dB difference. 

Schematic file looks like:

![image](https://github.com/user-attachments/assets/9812d0b5-c8cc-4c7e-b07f-7144abcbc98e)

PCB file looks like:

![image](https://github.com/user-attachments/assets/a6c8ca8e-0048-4fb1-8ef2-8eb41f2a56b4)

Gerbers, BOM and all manufacturing information is already there, and the project is in KiCAD's native file formats. It's a normal four-layer PCB with an estimated BOM of around $50/unit, which is less than half the price of a Cremat CR-113 module. 

## Charge Sensitive Amplifiers
Here's my attempt at explaining what a charge sensitive amplifier, written as a dialectic for my amusement (because who has the time to write a datasheet?)

Me: Do you know what an op-amp is?

### You: A what?
Me: It's an electrical engineering thing. Don't worry about it.

### You: Okay.
Me: What, you're not the least bit curious?

### You: ...No, not really. Where's the lightning in a bottle part come from? Is this some lame nerd stuff?
Me: Not telling.

### You: ...
Me: ...

### You: Fine. What's an op-amp?
Me: VOLTAGE GO UP!
![OPAMPMAN](https://github.com/user-attachments/assets/163c48ee-580d-459e-87b7-294ac67ae7c1)

### You: Wh-what?
Me: Awesome, right? We can make a circuit that outputs a spike of voltage when a small amount of current comes inside. So, we can turn really small amounts of current- in the pico or nano-ampere range, into voltage spikes that are detectable by modern analog to digital converters.

### You: Speak English, four-eyes.
Me: OKAY! Basically- the feedback capacitor captures charge and holds it, and that's where the name comes from.

### You: That's it?
Me: It's cooler when you know the physics.

### You: Uh-huh. Why is this important?
Me: Do you like living?

### You: No.
Me: Well, the people who do should know it's used in particle accelerators for cancer treatments, is critical for X-ray/CT/PET scanning and so is probably responsible for saving a large amount of lives. Also, it's useful in semiconductor manufacturing, so if it didn't exist your phone wouldn't exist.

### You: You should've said so earlier, before all of the useless waffling. 
Me: For a caricature I invented you sure do have a lot of spine.

### You: I'm a what?
Me: Nothing, nothing. So, the problem is it's extremely important to modern society but no one makes it cheaply. This one company, Cremat, uses 2000-era op-amps and so the signal to noise ratio is basically 200,000 times worse than modern op-amps, and they sell it at a greater price than it would take for you to make the PCB yourself.

### You: ARE YOU KIDDING ME? I'M NOT REAL? WHAT IN THE [REDACTED] DO YO-
Me: So, since my Cremat CR-113 shipment didn't arrive (they refunded it, but still! Don't put up stuff for sale you know isn't in stock), I just made a modern-era CSA. Fully made in KiCAD (open source for the win), with the schematics, PCB files, Gerber files, and generic bill of materials all in this repository. Have fun!
