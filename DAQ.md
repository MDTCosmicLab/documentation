# How to take data

### open a terminal and go to the directory

cd /mdt/daq/GLIB_PC

Give the following command to start a run:

./readData.sh runNumber

where runNumber is an integer ( the number that will identify your run ).

The command will also open a GUI ( Graphical User Interface ) to setup the readout, in the GUI settings:
- set the IP address to 192.168.1.175, hit the button "GetID"
- In the Mezzanine Card configuration hit the button "Auto Detect", then "Init"
- In the Lemo Input table set the THR1 to 1500 mV and hit the button "Set" two times (first time gives error, second time OK).

### to analyse the data ( also while the run is ongoing ) go to the directory:

cd /mdt/reconstruction/mdtreco

and give the command:

./mdtreco nevents runNumber inputdir

nevents is the number of events you want to process, 0 means all events

runNumber is the run number set in the previous step

inputdir is the directory where the data are stored: you can also not give this argument and the data will be taken from /mdt/data by default

