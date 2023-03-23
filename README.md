# How to take data

### open a terminal and go to the directory:

cd /mdt/daq/GLIBC_PC

from there you can start the gui with:

./startGUI

in the GUI Settings, set the IP address to 192.168.1.175, hit the button "GetID"

In the Mezzanine Card configuration hit the button "Auto Detect", then "Init"

In the Lemo Input table set the THR1 to 1500 mV and hit the button "Set".

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



