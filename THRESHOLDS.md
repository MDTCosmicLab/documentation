# How to modify the thresholds 

You need to edit the files that are in /mdt/daq/GLIB_PC/config 

There is a file for each ASD:
MEZZ_X_ASD_CONFIG.txt   ->  where X is the TDC number in the convention 0 to 5 ( corresponding to the numbering 1 to 6 on the chamber )

The parameter that has to be changed is the one called:
asd0_main_thr_dac[7:0]          108             108                 8       Main threshold DAC (DISC1)

the first column is the setup value ( the one you should modify ), the second column is the default value (this you don't have to modify but you can put the default value back in the first column when you are done ) , the third column is the number of bits you have to define the parameter

The actual electronics threshold is applied to a negative signal, with the 25th electron corresponding to -39 mV and changing one count corresponds to a change of 2 mV. So a correspondance table ( just as an example with a few reasonable values ):

98  = -19 mV

99  = -21 mV

101 = -23 mV

...

...

108 = -39 mV  =  25th electron

...

...

116 = -55 mV  

117 = -57 mV

118 = -59 mV

You can modify the threshold of a given ASD globally ( i.e. for all 24 channels ) by modifying the three values in each file ( each value is corresponding to a group of 8 channels )

Always remember to re-init the readout in the GUI after you've modified the configuration files.


