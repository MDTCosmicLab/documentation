# How to take data

### open a terminal and go to the directory:

cd /mdt/daq/GLIB_PC

from there you can start the gui with:

./startGUI

in the GUI Settings, set the IP address to 192.168.1.175, hit the button "GetID"

In the Mezzanine Card configuration hit the button "Auto Detect", then "Init"

In the Lemo Input table set the THR1 to 1500 mV and hit the button "Set" two times (first time gives error, second time OK).

### open another terminal and go to the directory

cd /mdt/daq/PyChips/scripts

to start a run you can give the command:

./readData.sh runNumber

where runNumber is an integer ( the number that will identify your run ).

### to analyse the data ( also while the run is ongoing ) go to the directory:

cd /mdt/reconstruction/mdtreco

and give the command:

./mdtreco nevents runNumber inputdir

nevents is the number of events you want to process, 0 means all events

runNumber is the run number set in the previous step

inputdir is the directory where the data are stored: you can also not give this argument and the data will be taken from /mdt/data by default

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

108 = -39 mV

...

...

116 = -55 mV

117 = -57 mV

118 = -59 mV

You can modify the threshold of a given ASD globally ( i.e. for all 24 channels ) by modifying the three values in each file ( each value is corresponding to a group of 8 channels )





