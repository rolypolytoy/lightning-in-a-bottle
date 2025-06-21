# Lightning In A Bottle

Have you ever wanted to catch lightning in a bottle? Well, now you can!

Sort of.

## What a Charge Sensitive Amplifier Is
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
