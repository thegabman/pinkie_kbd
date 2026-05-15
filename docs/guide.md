# Build Guide

-----

## Tools and Supplies

- Soldering iron + solder
- Tweezers
- Flush cutters
- M2 x 0.4 pitch tap + handle
- Superglue
- 3D printer or at least the printed parts

-----

## Before You Start

Order your PCBs and top plates from the gerber files in `/pcbs` and `/plates`. While you wait for them to arrive, print your case parts.

-----

## Step 1 — Print the Travel Bracket

Print the travel bracket from `/cases`. This print requires you to pause mid-print to place the magnets.

> [!IMPORTANT]
> **Magnet polarity.** Before starting the print, figure out which way your magnets need to face so the bracket attracts the keyboard. Mark them first. Placing them wrong means reprinting.

- Slice the model and add a pause at the two layers where the magnet pockets are fully formed
- **First pause** — drop in 2 magnets, resume print
- **Second pause** — drop in the remaining 2 magnets, resume print
- The remaining layers will lock them in place
- Best results: print the bracket in PLA with PETG as the support interface material (or vice versa) — the two materials don’t bond well to each other, making supports easy to remove cleanly

-----

## Step 2 — Print Case Parts

Print the following from `/cases`:

- Case left
- Case right
- Spacer (2x) — can also be laser cut from EVA foam
- Lipo bracket (2x)

-----

## Step 3 — Tap Threads

Tap M2 x 0.4 threads into all screw holes in both case halves.

Go slow, keep the tap straight, back off every half turn to clear chips.

`[photo placeholder — tapping threads in case]`

-----

## Step 4 — Glue Magnets to Top Plates

Attach the 10 x 1mm magnets to the bottom of each top plate using superglue.

> [!CAUTION]
> **Check polarity before gluing.** Hold the top plate over the travel bracket and confirm the magnets attract. Once glued they cannot be removed without damage.

- Place the spacer on the top plate to use as a positioning guide — the magnet pockets in the spacer show exactly where the magnets go
- Apply a small drop of superglue to each pocket
- Press magnet in, hold for 30 seconds
- Let cure fully before continuing

`[photo placeholder — magnets on top plate]`

-----

## Step 5 — Solder Diodes

Solder all 52 diodes to the PCB.

- Diodes are **1N4148W SOD-123** — surface mount, directional
- Match the cathode line on the diode to the marking on the PCB
- Solder one pad first, reflow to align, then solder the second

`[photo placeholder — diode orientation on PCB]`

-----

## Step 6 — Solder JST Connector (Optional)

Solder the JST 1.25mm 2P connector to the battery pads.

> [!TIP]
> If you skip the JST connector you can solder the battery wires directly in step 12 — but the connector makes it much easier to disconnect the battery later.

`[photo placeholder — JST connector placement]`

-----

## Step 7 — Solder Reset Button (Optional)

Solder the reset button to the PCB.

Not strictly required — you can also reset by briefly shorting the reset pads — but the button makes flashing much easier.

-----

## Step 8 — Solder Hot-Swap Sockets (Optional)

If you are going the hot-swap route, solder the Gateron low profile 2.0 hot-swap sockets now. Correct socket orientation is marked on the PCB silkscreen.

Skip this step if you are soldering switches directly — you will do that in step 12.

`[photo placeholder — hot-swap socket orientation]`

-----

## Step 9 — Flash Firmware and Test MCU

Before soldering the MCU to the board, flash it and confirm it works.

- Download the prebuilt firmware from [releases](../../releases) or build your own from the [pinkie ZMK config repo](https://github.com/gabrielschmitz/pinkie-zmk-config)
- Put the MCU into bootloader mode (double-tap reset)
- Drag and drop the `.uf2` file onto the drive that appears
- Confirm the MCU powers on and is discoverable via bluetooth

-----

## Step 10 — Solder MCU

Solder the MCU to the PCB.

> [!IMPORTANT]
> Solder the MCU directly to the PCB — do not use low profile sockets. The MCU must sit flush so the USB-C port aligns correctly with the case cutout. A case variant with a different USB-C cutout placement is in the making.

- Confirm orientation before soldering — the USB-C port must face the correct edge
- Place a strip of kapton tape on the PCB where the MCU will sit to prevent shorts
- Push pin headers through from the opposite side of the PCB
- Place the MCU on top and solder one side completely
- Slide the plastic spacer off the pin header
- Solder the other side
- Flush cut all pins on both sides

> [!TIP]
> Both the MCU pads and the PCB pads are plated through-holes, so with some practice you can skip the pin headers entirely and solder them directly together.

`[photo placeholder — MCU placement and orientation]`

-----

## Step 11 — Test the Matrix

Before assembling, test every key position by shorting the switch pads with tweezers while the keyboard is connected.

Use a keyboard tester ([keyboard-test.com](https://keyboard-test.com) or similar) to confirm every key registers. Fix any cold joints or missed diodes now — it is much harder after assembly.

`[photo placeholder — testing matrix with tweezers]`

-----

## Step 12 — Assemble Switches and Top Plate

**If using hot-swap sockets:**

1. Place the PCB on a flat surface, components facing down
1. Place the spacer on top of the PCB
1. Place the top plate on top of the spacer
1. Push all switches through the top plate into the sockets — confirm each one clicks in fully

**If soldering switches directly:**

1. Place all switches into the top plate, pins facing up
1. Lay the top plate face down on a flat surface
1. Place the spacer on top
1. Place the PCB on top of the spacer, components facing you — align all switch pins through the PCB holes
1. Confirm alignment, then solder all switches

`[photo placeholder — switch and top plate assembly]`

-----

## Step 13 — Connect Battery

> [!CAUTION]
> **Check polarity before connecting.** Reversed polarity will damage the MCU. Match positive (red) to positive and negative (black) to negative.

- Plug in the JST connector, or solder the battery wires directly

-----

## Step 14 — Case Assembly

1. Place the lipo bracket into the case
1. Place the lipo into the bracket
1. Lower the PCB + spacer + top plate assembly into the case
1. Screw down with M2 x 10mm screws (14 total, 7 per half)
1. Do not overtighten — the threads are in printed plastic

`[photo placeholder — PCB in case before screwing down]`

-----

## Step 15 — Keycaps

Put your keycaps on. Low profile keycaps for Gateron KS-33 switches.

-----

## Step 16 — Repeat for Second Half

Build the second half following the same steps. All parts except the case are reversible — the PCB, top plate, spacer and lipo bracket are all the same. Only the case has a left and right variant.

-----

## Step 17 — Pair and Enjoy

Pair via bluetooth. The left half is the central, the right half is the peripheral.

> [!NOTE]
> The keyboard has no physical power switch. The default firmware puts both halves into soft off by holding ESC for 5 seconds. Press any key to wake — each half needs to be woken separately.

Clip both halves into the travel bracket when you head out. Enjoy your keyboard at home and on the go.

`[photo placeholder — finished build]`

-----

## Troubleshooting

|symptom                |likely cause                  |fix                                              |
|-----------------------|------------------------------|-------------------------------------------------|
|Key not registering    |Cold joint on diode or switch |Reflow solder joints                             |
|Entire row/column dead |Cold joint on MCU pin         |Reflow MCU                                       |
|Keyboard not discovered|Firmware not flashed correctly|Reflash                                          |
|Battery draining fast  |Short somewhere               |Inspect PCB visually, check for solder bridges   |
|Magnet polarity wrong  |Bracket repels keyboard       |Reprint bracket with corrected magnet orientation|