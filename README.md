# 7-Key Custom MIDI Keypad

This is my 7-key MIDI keypad project for Hack Club Half Life Week 3 It features custom capacitive touch pads mx switches, a rotary encoder, slide potentiometers.
I used Kai Pereira's MIDI Keypad tutorial as a loose guide, but I customized the layout to make my own capacitive touch pads with a mix of rectangular and hexagonal shapes.

## What I Learned & How I Built It

1. **Making the Capacitive Touch Pads:** I designed the 7-key touch pads directly in KiCad's Footprint Editor. I made sure to uncheck `F.Paste` so solder paste won't be applied to the pads, leaving the copper exposed so it detects your finger. I also set a 0.5mm clearance gap between every key so they don't trigger each other.
2. **Routing the PCB:** I routed all the signal traces by hand, sticking to smooth 45-degree bends instead of sharp 90-degree corners to avoid acid traps or whatever that is.
3. **Fixing DRC Errors & Ground Pour:** I poured ground zones on both the top and bottom layers (`F.Cu` and `B.Cu`). I had a few "starved thermal" warnings where ground pads weren't getting enough copper spokes, so I ran short bridge traces from those pads to nearby ground areas. After that, DRC passed with 0 unconnected pads
4. **3D Models:** I set up the `HACKCLUB_3DMODEL_DIR` path variable in KiCad preferences so all the components show up properly in the 3D viewer.
5. **lack of gpio** due to the lack of gpio pins i had to sacrifice the leds for an extra button wich i wanted.

## Bill of Materials (BOM)

| Item | Category | Part Description | Qty | Price (USD) | Supplier | Link |
| :---: | :--- | :--- | :---: | :---: | :---: | :---: |
| **1** | Microcontroller | Waveshare ESP32-S3-Zero Dev Board | 1 | $9.88 | AliExpress | [Link](https://it.aliexpress.com/item/1005012733231291.html) |
| **2** | Keycaps | Relegendable Transparent Keycaps (10 Pcs) | 1 pack | $4.66 | AliExpress | [Link](https://it.aliexpress.com/item/1005005825113345.html) |
| **3** | Switches | Tactile Mechanical Switches (3-Pin MX) | 1 pack | $4.70 | AliExpress | [Link](https://it.aliexpress.com/item/1005013167413073.html) |
| **4** | Encoders | EC11 Rotary Encoders w/ Push Button (5 Pcs) | 1 pack | $3.53 | AliExpress | [Link](https://it.aliexpress.com/item/1005007644083514.html) |
| **5** | Potentiometers | 30mm Single Slide Potentiometer B5K (3 Pcs) | 1 pack | $1.94 | AliExpress | [Link](https://it.aliexpress.com/item/1005009637487801.html) |
| **6** | PCB | Custom PCB Fabrication | 5 pcs | $4.00 | JLCPCB | [Link](https://jlcpcb.com) |

### Cost 

* **Components Subtotal (AliExpress):** $24.71
* **AliExpress Shipping & Import Fees:** $25.40
* **JLCPCB (5 PCBs + Shipping):** $17.48
* **--------------------------------------------------**
* **Total Project Cost:** **$67.59 USD**
  
## Project Files

- `Hardware/Midi.kicad_sch` — KiCad schematic
- `Hardware/Midi.kicad_pcb` — KiCad PCB layout
- `Hardware/Midi.kicad_pro` — KiCad project file
- `FabricationFiles/` — Gerber zip and fabrication files for JLCPCB also includes a .step file 
- `Firmware/` — Firmware

## Credits

- Based on Kai Pereira's MIDI Keypad tutorial for Hack Club Half Life Week 3.
- Built using footprints and symbols from the Hack Club KiCad Library.
  
<img width="1099" height="817" alt="7" src="https://github.com/user-attachments/assets/2572e432-ff55-4b24-823d-ad9f05556477" />
<img width="1420" height="1023" alt="6" src="https://github.com/user-attachments/assets/7451a9fd-ed6a-49d7-9470-c99aa466e1ca" />
<img width="1416" height="1020" alt="5" src="https://github.com/user-attachments/assets/3288d387-b3ae-4ca6-91b1-71be40208b7c" />
<img width="1416" height="1021" alt="4" src="https://github.com/user-attachments/assets/3b1b4eb4-ab05-4133-b0ec-05f10fbb134b" />
<img width="504" height="723" alt="3" src="https://github.com/user-attachments/assets/bb9b4bc7-9392-42fd-bba3-93adcbce818e" />
<img width="1750" height="701" alt="2" src="https://github.com/user-attachments/assets/ac51b630-7958-4135-b658-78d1238d52bf" />
<img width="1541" height="880" alt="1" src="https://github.com/user-attachments/assets/9e944d81-f026-47a2-9c28-777ad37d1a4d" />
<img width="1536" height="919" alt="15" src="https://github.com/user-attachments/assets/d4b37733-5818-47fd-9593-30b6514722d9" />
<img width="1719" height="922" alt="14" src="https://github.com/user-attachments/assets/6576dcbd-871d-4ba2-b077-fc469b5ee4db" />
<img width="1337" height="856" alt="13" src="https://github.com/user-attachments/assets/b7adac21-1869-4241-8585-fa758e26d69d" />
<img width="1334" height="866" alt="12" src="https://github.com/user-attachments/assets/078e0a42-de93-4fb2-a72a-db0c35965869" />
<img width="1918" height="1013" alt="11" src="https://github.com/user-attachments/assets/3fb1db35-d8e6-40e0-936e-47bfd6c468f2" />
<img width="1066" height="706" alt="10" src="https://github.com/user-attachments/assets/08add1d5-c2e7-4db1-ab93-bc8cd4fc3336" />
<img width="1382" height="739" alt="9" src="https://github.com/user-attachments/assets/947ab160-0fdf-4522-86ac-c98c910745cb" />
<img width="1082" height="673" alt="8" src="https://github.com/user-attachments/assets/10583d9a-908f-4e15-a07f-cf345f64ae88" />
