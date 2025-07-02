# Lightning In A Bottle

Lightning in a bottle is an open-source, low-cost charge sensitive amplifier with several improvements over all existing commercial designs.

| Metric | Lightning In A Bottle (by Hume) | Cremat CR-113 | Advantage |
|---------------|----------------------|---------------|-----------|
| **Cost** | ~$50 | >$100 | **>2x lower cost** ✅ |
| **Gain** | 1000 mV/pC | 1.3 mV/pC | **750x higher gain** ✅ |
| **Bandwidth** | ~16 kHz | ~3 kHz | **>5x greater bandwidth** ✅ |
| **Power Supply** | +5V (standard) | ±6V-13V (proprietary) | **Standard power** ✅ |
| **Rise Time** | <1 ns | 1 ns | **Definitively faster** ✅ |
| **Raw Noise** | 530k electrons RMS | 300k electrons RMS | **~5dB weaker** ❌ |
| **True SNR** | No ADC noise bottlenecks | Bottlenecked by ADC noise (**750x greater ADC noise due to 750x lower gain**) | **Vastly superior SNR in real systems** ✅ |
| **Component Availability** | Off-the-shelf components | Proprietary parts | **Global availability** ✅ |
| **License** | Open Source (The Unlicense) | Proprietary | **Less morally bankrupt** ✅ |
| **Scalability** | Infinitely scalable with JLCPCB, PCBWay, etc. | Limited by vendor | **Unlimited scaling** ✅ |
| **Lead Time** | Days to weeks (PCB fab lead times) | Vendor dependent | **Faster deployment** ✅ |
| **Name** | Descriptive, evocative and physically realistic | Cremat?? (megablunder) | **We Didn't Name Ourselves Cremat** ✅✅✅|

It has a >2x lower cost, a 750x greater gain, >5x greater bandwidth, >50% lower cost, and sub-5 dB lower SNR. Importantly- its real SNR will be higher since the gain is >750x, and since ADCs have noise, our gain will basically reduce that noise by 750x, and **so in real systems our CSA will have a much higher SNR than Cremat's module**, and thus this has no real 'weakness'. It also uses standard +5V as its power source rather than the weird +-6V-13V supplies the Cremat module needs.

It also uses commercial off-the-shelf components and so can be more easily and cheaply scaled than the Cremat CR-113 and other modules, whose components are proprietary and who may not ship to every country in the world in a timely manner.

Components:
- LMH6629SD, an ultra-low noise Op-Amp
- TPS7A3301RGW for power regulation
- Several miscellaneous ceramic capacitors, SMD resistors, inductors, and other generic components.

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

A charge sensitive amplifier is basically just a capacitor around an op-amp. A capacitor is a thing which has capacitance, whereas an op-amp is something which makes voltage go up. I've made an informative schematic to fully get the concept across. 

![OPAMPMAN](https://github.com/user-attachments/assets/163c48ee-580d-459e-87b7-294ac67ae7c1)

