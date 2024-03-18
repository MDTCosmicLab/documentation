# How to start the trigger

1) Check that the mainframe CAEN SY4527 is switched on (switch it on in case it's not)  

2) Trigger scintillators HV is controlled via GECO (CAEN SW). To start the GUI right-click and select "Run as a program" on the GECO icon in your desktop

3) Click on "Autodetect", the IP address of the CAEN frame (141.108.12.36) should appear. Type it in the GUI. Add user and password.

4) Look for the channels named MDT1 and MDT2 (and MDT3) on the board13

5) Set the HV set value of the two channels (column V0set) to the desired value (default is 2000 V)  

6) In the Pw column, go from Off to On -> check in the GUI that the HV and current start indeed increasing
