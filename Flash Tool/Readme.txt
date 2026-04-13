This isn't my tool got it from the OFficial AmebaD... !!!

1. Extract the Image_Tool zip File

2. Inside that folder Launch the ImageTool.exe

3. From the Top Left Corner in "Chip Select" select AmebaD(8721D)

4. on the Download Tab,
	- Under Serial -> COM -> Select the Board (Eg: COM8, COM6, ...)
		*IF COULDN'T SEE THE BOARD, CONFIRM IF 'CH340' DRIVES INSTALLED OR NOT
		*SIMPLY CLOSE THE PROGRAMME -> REPLUG THE BOARD TO YOUR PC/LAP -> RELAUNCH THE PROGRAMME
	- Leave the baud rate at 1500000
	- Under Flash Download select first 3 raws (Tick the first 3 raws)
		- Simply attach the Files in these order and update the address (double click on the address bar to change it)
		
		Row 1 -> km0_boot_all.bin -> 0x08000000

		Row 2 -> km4_boot_all.bin -> 0x08004000

		Row 3 -> km0_km4_image2.bin -> 0x08006000

	- Simply Click the Download button at the bottom (it flash failed you will have to set the board into Download Mode before clicking "Download" Button)
		*SETTING THE BOARD INTO DOWNLOAD MODE
			1. Hold the Burn button
			2. Tap the RST (Reset) button once
			3. Release the Burn button
			4. Release the RST button

5. Enjoy The New Firmware
