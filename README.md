The five files above create RADAR. Through their implimentation, one should be able to preliminarily reduce their own data and then carry out beam RFI analysis based on the type of telescope the data is coming from. This pipeline is tailored to VLA and MeerKAT data but can easily be updated to include other telescopes. 

The order of operation for these notebooks is as follows:

Preliminary Notes: The known-s-band_RFI file is a compilation of known RFI frequencies from uploaded from the NRAO and MeerKAT website and can be used as a reference for the preliminary frequency cleans. One can also upload more known RFI frequency files to better suit their data. Also note that the frequencies above 2GHz file is a method for sorting through files directly from their repository to eliminate hits above 2GHz from files before downloading them to clean. 

1) After loading in your known RFI frequency files, then implement the file_splitting.ipynb to get rid of preliminary known RFI frequecy ranges. This stage also begins eliminating SNR, Power, and Drift Rate values that are for certian indicative of the hit being RFI. These can be updated to fit ones preferences but generally are a very large threshold. This notebook also helps compile the hits into fewer large files to make loading in hundreds of files less time consuming. 

2) Once the preliminary clean of the data has been compiled into anywhere from 1-10 files ideally, then you are ready to run the Main_RFI_filtering notebook on your data. Here is where the customization begins. You can mess around with the arbitraty thresholds for beam overlapping, SNR, drift rate, power ratios for incoherent and coherent, and so on. The ones currently implemented are specified for VLA and MeerKAT but are easily interchangable. 
