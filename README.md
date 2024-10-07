# 8-Aout-modbus-TCU-RTU

8 x D/A converter, 0..10V output, resolution 12 bit

Scaled output 0..1000 

Write single register FC6  <start register> <register number> <register value>

Write multiple register  FC16 <start register> <number of registers> <register values .. register values>

max update rate 2 Hz

end of scale pre-trimmered. can be adjusted by software

if using TCP IP address can be assigned from browser. access to 192.168.0.7 admin admin than go to the LOCAL IP config tab. set in serial port tab local port 502 and select TCP server 


Power supply: DC IN 12..28V

Inverse plarity protection

to set node address in RTU mode, issue a FCT6 command, node 1, to address 200 with node address as value. unit must be the only one on the net

to set gain select the channel and send an FCT6 command to address 100+channel, 3290 + offset until you get 10.00 volt in output

