# Lightning In A Bottle

Have you ever wanted to catch lightning in a bottle? Well, now you can!

Sort of.

### How?
Do you know what an op-amp is?

### A what?
It's an electrical engineering thing. Don't worry about it.

### Okay.
What, you're not the least bit curious?

### ...No, not really. Where's the lightning in a bottle part come from? Is this some lame nerd stuff?
Not telling.

###...
...

### Fine. What's an op-amp?
Glad you asked! **Magic triangle make voltage go up.**

### That's it? 
**M̶̡̛̲̯̪̱̺̪͍̻̜̽͂̌́͐͊̈́́̈́͗́a̷̞̳̺̹͎͉̎̀͜g̸̨̨͎̤̺̭̯̮̪̙̥̺̔͂͐͐̍̈́͘ͅǐ̵̧̗̈̀̏͜͜͝c̴̨̨̢̦̻͇̟͙̳̬͙̦̕ͅ ̸̱̬̲̝͇̱̘̦̫̹͚̈́̒̓̎́̊̚t̴̥͇̅͛͆̾̌r̵̞̰̣͓̯̍̂̈́̄̽́̇̄̅̈́͒̐͐i̴͔̻̿̽͗̋̅̀͝ǎ̸͉̺̹̱̈͋̆̅̒̅̕͘͜ņ̶̯͓̰̹̲̩̞̠̞̫͔̰̊͛̉̚̕͜ģ̶̡͉̺͇̣͈̩̏l̵̬̭͙̩͎͓̱͙͙̊̇͐͜ȩ̸̨̭̲̤̺̪͎̍̽̋̿͛͝ͅ ̵̢̧̱̬̯̟̙̟̪̺̭̙͇̌̐̈́̾̄̏͆̓̎̌̎̍̎̈́͜m̵̠̭̠̆å̶̬͇̀̐̎͌̈̅͗̍̀̀͝ͅk̷̨̬̼̘̻̘̣̠͎̪̣̖͠e̸̺̰̫͆̀̄́̃̉̿̒͂̌̚͜͜͠ ̶̻̗̻̗̃̅̀͑̇̉̋͐̌́̀̽̚͝v̵͉̭̦̼͎̖̩͈͉̳͙̙̿̇̀̑̆͜͠ͅo̶̻̿̆͐̍ļ̷̱̲͎͊̓̿̈́̾̿̅̈̈́̉̋͋̕t̸̨̡̰͎̟̭̭͚̹̮̫̙̑̽́͘͝ạ̶̺̮̠͋̓́̐́̔͗̈́̓̍͗͆͌̓͘ģ̴̏͑̓ȅ̵̢̛̠̼̖̰͈̩͍͕̮͕̌͗̇̽ ̴̧̡̞̙̬̥̣̠̪͕͖͖̹̈́̔̏̔͗̀̒̈́͠g̶̡̧̡̩̲̟̼͕̭̰͓̘̞̼̈́͛̀̒̀͠o̷̢̝͍̲̖͛̃̆̃̎̂̾͂̏͠ ̵̧̛̹̠̮̪̬̞͙̱̙̆͒́͑̀̏͘̚u̸̡̺̯̩̬̠̠̜̖̪̺͔̼͒́́̽̊̅̄̈́̉̈́̐̅̚̕̕͜p̴̨̧̩̊̌̃̎̀͑̿.̵̡̣̲̳̭̮̬̙̉͊̅̅̀͌̌͛́̅͘**

### ???
Yeah. Don't worry about what's inside.

### I wasn't.
Sure you weren't. But, we can make a circuit that outputs a spike of voltage when a small amount of current comes inside. So, we can turn really small amounts of current- in the pico or nano-ampere range, into voltage spikes that are detectable by modern analog to digital converters.

### I'm not bilingual.
Heh? What do you mean?

### SPEAK ENGLISH FOUR-EYES!!!
OKAY! Basically- the feedback capacitor captures charge and holds it, and that's where the name comes from.

### T-That's it?
It's cooler when you know the physics.

### Uh-huh. Why is this important?
Do you like living?

### No.
Well, the people who do should know it's used in particle accelerators for cancer treatments, is critical for X-ray/CT/PET scanning and so is probably responsible for saving a large amount of lives. Also, it's useful in semiconductor manufacturing, so if it didn't exist your phone wouldn't exist.

### You should've said so earlier. 
Yeah, I forgot you're a caricature I invented so I could play at the Socratic method.

### I'm a what?
Nothing, nothing. So, the problem is it's extremely important to modern society but no one makes it cheaply. This one company, Cremat, uses 2000-era op-amps and so the signal to noise ratio is basically 200,000 times worse than modern op-amps, and they sell it at a greater price than it would take for you to make the PCB yourself.

### ARE YOU KIDDING ME? I'M NOT REAL? WHAT IN THE [REDACTED] DO YO-
So, since my Cremat CR-113 shipment didn't arrive (they refunded it, but still! Don't put up stuff for sale you know isn't in stock), I just made a modern-era CSA. Fully made in KiCAD (open source for the win), with the schematics, PCB files, Gerber files, and generic bill of materials all in this repository. Have fun!