# 8-Aout-modbus-TCU-RTU

8 x D/A converter, 0..10V output, resolution 12 bit

Scaled output 0..1000 

Write single register FC6  <start register> <register number> <register value>

Write multiple register  FC16 <start register> <number of registers> <register values .. register values>

max update rate 2 Hz

end of scale pre-trimmered. can be adjusted by software

used a 28 pin MCU but a 20pin such as PIC18F15Q40 can be used. cheaper but more than enough. need to be redesigned the PCB and recompiled the formware
if using TCP IP address can be assigned from browser. access to 192.168.0.7 admin admin than go to the LOCAL IP config tab. set in serial port tab local port 502 and select TCP server 


Power supply: DC IN 12..28V

Inverse plarity protection
RTU mode is 19200,n,8,1
to change baudrate requires recompile. it should be possible to change by software, if someone need this I can add this function. just ask
to set node address in RTU mode, issue a FCT6 command, node 1, to address 200 with node address as value. unit must be the only one on the net

to set gain select the channel and send an FCT6 command to address 100+channel, 3290 + offset until you get 10.00 volt in output

board uses a PIC18F25K80 MCU. should use another one but this is the one I usually have in stock so this is my preferred
requires a PICKIT 4 or PICKIT 5 to program via ICSP
power from board or if not powered requires 5V from PICKIT. if powered set 'power from board' into the MPLAB IPE (access extended function password microchip)
can work from 14 volt up to 36 VDC. basically best voltage is 24VDC. a diode is placed for inverse polarity protection
components are all available from mouser or similar
for the USR-TCP232-T2 - USR IOT can be found on aliexpress or even amazon for around 10..20 usd
for RTU use ONLY max485 chip. comm is half duplex, bus is always in RX, goes in TX only when replying to proper node call 



issued upon "The Creative Commons Non-Commercial (NC) clause"
it allows others to copy, distribute, display, and perform your work – and derivative (i.e. modified) works based upon your work – but the work cannot be used for commercial purposes.
