| title | speakers-DIY |
| --- | --- |
| author | GLOXIOU |
| description | A DIY project to build two fairly powerful wooden "head" speakers. A project linked to "subwoofer-DIY" |
| created_at | 2026-09-08 |

# Day 1: Defining system & idea search & inspiration

My goal is to build two wooden "head" speaker cabinets, each consisting of a bass/mid-range module and a high-frequency module. I am aiming for a pair with approximately 300W RMS per speaker, and I plan to use 10-inch woofers along with a compression driver and a horn.

Later on, I also want to build a wooden subwoofer, so this project is linked to [that one](https://github.com/GLOXIOU/subwoofer-DIY).

Today, I’ve just been gathering information. The goal is to put together a kit similar to what L-Acoustics might offer. These speakers are intended for use at events—birthdays, weddings, or private parties. Consequently, they need to be powerful enough for both indoor and outdoor settings, yet compact enough for easy transport. As for the subwoofer, it will be tailored to the music being played—primarily reggae, techno, and other modern party music.

After some research, I’ve decided to base the build on [the box speaker 10-250/8-A](https://www.thomann.fr/the_box_speaker_102508a.htm?gad_source=1&gad_campaignid=1544038022&gbraid=0AAAAADuDMCWqEhEq4n_4zOgVoqLUYxvDH&gclid=Cj0KCQjw5P7UBhDaARIsAOSlS1O6Oam1ZMXhtpK8U2jO1B9wILoDKDmiaS_8sWZ5LIXVSXQzi_hM2LIaAu0UEALw_wcB) drivers for the woofers, [the box pro DSP 115](https://www.thomann.fr/the_box_pro_hochtoener_dsp_115.htm?gad_source=1&gad_campaignid=1544038022&gbraid=0AAAAADuDMCWqEhEq4n_4zOgVoqLUYxvDH&gclid=Cj0KCQjw5P7UBhDaARIsAOSlS1NRoL0ZqlUKUBtIAG-FUjx-qwFdyAcWcUgyI_sR7WdiULvsenBMprMaAozLEALw_wcB) compression drivers, and [Monacor MRH-83 horns 1800Hz–18kHz, 2.5cm diameter](https://www.audiophonics.fr/fr/chambres-de-compression/monacor-mrh-83-pavillon-pour-chambre-de-compression-haut-medium-1800hz-18khz-o25cm-p-1172.html). I should note that this is just an initial selection and is subject to change later on.

The price for these three items is €111.90, or $130.10. The maximum budget per speaker is around $200. That leaves $69.90 for the rest (wood, glue, cables, etc.).

I then turned my attention to the wood design. I think we should use 15 mm birch plywood, which currently costs around €40/m²—or $47/m².

For the internal design of the enclosures, I think I’ll take inspiration from the design I found on [this site](https://www.astuces-pratiques.fr/high-tech/plan-de-construction-d-enceinte-sono) though I know I need to perform calculations based on the selected driver, the horn, and so on. I’ll look into that over the next few days. You can see the image just down this text. Over the next few days, I will also model this design in Fusion 360 to perform calculations more quickly and make modifications more easily.

![Schéma 1](images/shema-1.png)

The question I'm asking myself now is whether to build passive or active speakers. Active would be ideal, but it might not fit the budget. That’s why I’m also considering building an external amplifier myself—not from scratch, but using modules—which could turn out to be cheaper.

**Time spent today:** ~1.5 hours on research, and ~30 minutes on documentation, creating the repo, etc.  
**Total spent from the beginning:** 2h

# Day 2: research and datasheet compilation

Today, I’m going to look into the question of amplification and share the thoughts I had last night; above all, however, I’ll be gathering data from the manufacturers of the project's three main components to perform acoustic calculations and validate or reconside my choice of parts.

So, for the amplification, I’d like to build active speakers, using an amplifier module and a DSP module for each speaker. Alternatively, I could build an external rack for instance, to use a single amplifier for all three speakers.

The choice will depend mainly on one thing: whether or not I manage to secure full funding for the project. If not, the speakers will be passive and I do have a way to test them’but I would have to wait until later to actually use them for gigs or other events.

I am now going to retrieve the data for the three main components and bring them together in one single location.

Here is all the data I need for the calculations. Everything will be filled in in this file: [driver-data](https://github.com/GLOXIOU/speakers-DIY/blob/main/docs/driver-data.md), as well as in a table in this log.

| Woofer — 10-250/8-A | Compression Driver — DSP 115 | Horn — MRH-83 |
|---|---|---|
| Resonance frequency (Fs) | Resonance frequency (Fs) | Throat diameter |
| DC resistance (Re) | Nominal impedance | Mouth width |
| Nominal impedance | Minimum impedance | Mouth height |
| Mechanical Q (Qms) | RMS power | Depth |
| Electrical Q (Qes) | AES power | Horizontal dispersion |
| Total Q (Qts) | Sensitivity | Vertical dispersion |
| Equivalent volume (Vas) | Frequency response | Minimum frequency |
| Effective cone area (Sd) | Recommended crossover frequency | Maximum frequency |
| Maximum linear excursion (Xmax) | Maximum SPL | Frequency response |
| RMS power | Voice coil diameter | Directivity |
| Sensitivity | Throat diameter | Weight |
| Voice coil inductance (Le) | Mounting type | |
| Moving mass (Mms) | Dimensions | |
| Compliance (Cms) | Depth | |
| Force factor (BL) | Weight | |
| Overall diameter | Frequency response curve | |
| Cutout diameter | Impedance curve | |
| Depth | | |
| Weight | | |
| Frequency response curve | | |
| Impedance curve | | |
| Phase response curve | | |
| Directivity | | |

The research sources are:
* For the woofer: Thoman for [this doc](https://github.com/GLOXIOU/speakers-DIY/blob/main/docs/woofer-data.pdf), and [that site](https://petoindominique.fr/php/mysql_listehp3.php?marque=THE+BOX+SPEAKERS) for others stuff.
* For the horn: The official [Monacor site](https://www.monacor.com/products/mrh-83/?lang=en&r=pdf).
* For the compression driver: The product page [on Thomann](https://www.thomann.fr/the_box_pro_hochtoener_dsp_115.htm).

Here is the main information table:

| Elements | Informations |
|---|---|
| **10-250/8-A** | **Fs:** 56.8 / 75.65 Hz · **Qts:** 0.38 / 0.392 · **Vas:** 33.3 / 19.35 L · **Sd:** 356.3 cm² · **Xmax:** ±2.0 mm · **Pe:** 250 W RMS · **Sens.:** 94 / 96.22 dB · **Re:** 5.8 / 5.62 Ω |
| **DSP 115** | **Z:** 8 Ω · **RMS:** 45 W · **Bobine:** 44 mm · **Gorge:** 1⅜" · **Profondeur:** 55 mm |
| **MRH-83** | **Gorge:** 25 mm / 1" · **Dispersion:** 90° H × 60° V · **Bande:** 1.8–18 kHz · **Dimensions:** 242 × 198 × 138 mm · **Poids:** 270 g |

For the calculations and internal design of the enclosures, I will use [linearteam](https://www.linearteam.org/), a speaker designing software for Windows.

**Time spent today:** ~1.5 hours on research, and ~1 hour on documentation.
**Total spent from the beginning:** 4h30
