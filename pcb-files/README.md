# Atom47 PCB

## Rev5 (with per key RGB)
![Atom47 rev5](https://i.imgur.com/lVYLru7.jpg)

## Rev4
![Atom47 rev4](https://i.imgur.com/Pqt8uBg.jpg)

### JLCPCB order process 

JLCPCB-specific production files can be found in [this folder](/pcb-files/rev4/manufacturing/jlc). Here are the files you need to upload to JLCPCB:

- `atom47-rev4-gerber.zip` 
- `Atom47-Rev4-BOM-JLC.csv` is the BOM (Bill of Materials) file
- `Atom47-Rev4-Bottom-CPL-JLC.csv` is the POS/CPL (Footprint POSition/Component Placement List) file

Once you have the files ready, go to the JLCPCB website and follow the steps below:

1. Upload the gerber file
2. Once it is processed, select the options for the PCB:
   1. Leave all options as default, choose your material and color etc.
   2. Remember that MOQ (Minimum Order Quantity) is `5` PCBs
   3. Set `Confirm Production file` to `Yes`
   4. Enable `PCB Assembly`
   5. Choose `Assemble bottom side`
   6. Leave all options as default, set `Confirm Parts Placement` to `Yes`
   7. Proceed with your order
3. Upload the BOM and CPL files
4. Once the files are uploaded, the system will automatically recognize the components and you will be able to review them:
   1. `ATMEGA32U2` is likely to be out of stock. You can choose the `Do not place` option and source it yourself, then finish assembly by hand 
5. Once the parts list is confirmed, the system will attempt to automatically place the components on the board. The initial placement will be off, but JLCPCB engineers will catch it and fix it for you. You can then review the corrected placement and confirm it later
6. Complete your order:
   1. Pay for production, choose your shipping option etc.
7. Your files will be reviewed by JLCPCB engineers, and you will have to confirm the corrected placement. Here's a preview of the verified, corrected placement:

![Atom47 JLCPCB corrected placement](https://i.imgur.com/NFNugQg.png)

*Note: MCU not seen here, as this component was out of stock at the time of this order. It was sourced separately, and the assembly was finished by hand*

8. Once you receive your PCBs, you can then proceed with testing, assembly (if needed) and flashing the firmware

### VIA support 

Follow these step to use your Rev4 Atom47 PCB with VIA:

1. Compile the firmware with VIA support using your preferred method
   1. Example: `qmk compile -kb evyd13/atom47 -km via`
2. Flash the firmware using your preferred method
3. Open VIA: 
   1. Navigate to the `Design` tab
   2. Click on `Load` under `Load Draft Definition`
   3. Provide the `Atom47_Rev4.json` file from [this folder](/pcb-files/rev4/via) 
4. Connect your Rev4 Atom47 PCB 

*Note: This definition file only supports the default Vortex Core layout*
