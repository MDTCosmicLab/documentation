Description of the content of the ROOT Tree. The tree name is "mdt" and the variables are:

Variables with dimension 1 ( i.e. 1 entry per event )
- eventNumber: number of the saved event
- nhits: total number of leading hits (no selection applied apart from requiring leading edge)

Vectors with dimension equal to the number of hits:
- tdc: tdc board number ( from 0 to 5 )
- channel: channel number (from 0 to 23) in each TDC board
- coarse: coarse time
- fine: fine time   ( the tdc counts are computed as coarse*25 + fine ) 
- chamber: number of the chamber to which the TDC board belongs ( from 1 to 3 i.e. from top to bottom )
- layer: layer number of the hit ( from 1 to 3 ) 
- tube: tube number of the hit ( from 1 to 16 )
- time: TDC time ( in ns ) 
- charge: Hit charge
- leading: leading edge if =1 , otherwise trailing edge
