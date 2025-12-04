The five files above create RADAR. Through their implimentation, one should be able to preliminarily reduce their own data and then carry out beam RFI analysis based on the type of telescope the data is coming from. This pipeline is tailored to VLA and MeerKAT data but can easily be updated to include other telescopes. 

The order of operation for these notebooks is as follows:

Preliminary Notes: The known-s-band_RFI file is a compilation of known RFI frequencies from uploaded from the NRAO and MeerKAT website and can be used as a reference for the preliminary frequency cleans. One can also upload more known RFI frequency files to better suit their data. Also note that the frequencies above 2GHz file is a method for sorting through files directly from their repository to eliminate hits above 2GHz from files before downloading them to clean. 

1) After loading in your known RFI frequency files, then implement the file_splitting.ipynb to help 
