# Purpose

Data from: Natural and experimental cold exposure in adulthood increase the sensitivity to future stressors in a free-living songbird. 2022. Functional Ecology.

Maren N. Vitousek, Jennifer L. Houtz, Monique A. Pipkin, David A. Chang van Oordt, Kelly K. Hallinger, Jennifer J. Uehling, Cedric Zimmer, and Conor C Taff.

# Archiving

The repository is permanently archived on Zenodo: [![DOI](https://zenodo.org/badge/512863639.svg)](https://zenodo.org/badge/latestdoi/512863639)

# Description of contents

The markdown script 'cort_response_to_temperature' reproduces all the analyses and figures included in the paper and annotation for each code block is included in the script along with a description of analyses. Data used in the paper is included in sub folders. To fully reproduce all of the analyses, weather data will need to be accessed from the Northeast Regional Climate Center (nrcc.cornell.edu). A full html of the markdown script output is also included in the repository.

The data files included with the repository are:

1. 'cold_snap_adult.txt', which includes information about each adult used in the experimental nest cooling treatment.
2. 'data_by_capture.txt', which includes information about every individual capture included in the long term observational analyses.
3. 'snaps.txt', which includes information about the exact dates and times that cold snap or control treatments were applied to the experimentally cooled nests. This is used to merge with the raw temperature records of each nest when analyzing the effect of experimental cooling.
4. 'raw_hobo', which is a folder containing a raw temperature logger output file for each nest included in the experimental cooling treatment. These temperature records are processed and joined to the information in files 1 and 3 above using the included R script.

# Data file columns

Descriptions of the column names are given for each of the four data files described above.

## cold_snap_adult

- *look_code* - used for joining to other records
- *band_type* - used for joining to other records
- *assay* - code for the assay that cort samples were run on
- *experiment* - designates these are part of the cooling experiment
- *treatment* - designates cooling or control treatment
- *band* - unique USGS band for this individual
- *unit* - field site that this bird nested at
- *box* - nest box for breeding record (unique within unit)
- *sex* - male, female, or nestling
- *month* - month of capture
- *day* - day of capture
- *type* - type of corticosterone sample (B = base, S = stress-induced, D = post-dex)
- *amount* - amount of plasma collected
- *cap_num* - capture number for this bird with first capture of season = 1
- *plas_num* - plasma number for tracking samples
- *concat* - used for tracking samples in assays
- *latency* - time from capture to sample collection
- *cort_value* - raw cort value from assay
- *assay_grp* - group of samples that were extracted and assayed together
- *grp_effic* - assay efficiency for this group
- *final_cort* - cort value after correcting for efficiency
- *note* - any additional notes about this sample
- *cv* - coefficient of variation for cort sample run in two wells
- *doy* - day of year of capture

## data_by_capture

- *lookcode1* - lookup code for merging with other data
- *lookcode2* - lookup code for merging with other data
- *stage* - breeding stage
- *band* - unique USGS band
- *hatch_doy* - day of year of hatching for this breeding attempt
- *site* - field site the bird was sampled at
- *nest* - nest box the bird was sampled at (unique for each site)
- *year* - year of sampling
- *adult_or_nestling* - specifies if bird is an adult or nestling
- *sex* - sex as male, female, or nestling
- *experiment* - specifies experiment this bird was a part of
- *treatment* - specifies exact treatment within each experiment
- *ok_for_weather* - specifies whether this record is ok to use for weather analyses
- *cap_doy* - day of year of capture
- *cap_time* - time of capture
- *cap_num* - capture number for this year (first capture = 1)
- *age* - age of bird (ASY = after second year, AHY = after second year, SY = second year, ## = age in days)
- *mass* - mass in grams
- *bhead* - head plus bill length in mm
- *wing* - wing length in mm
- *latency* - latency from capture to sample in seconds
- *type1* - type of sample for first blood sample (B = baseline, S = stress-induced, D = post-dex, A = post-cotrosyn)
- *type2* - type of sample for second blood sample (B = baseline, S = stress-induced, D = post-dex, A = post-cotrosyn)
- *type3* - type of sample for third blood sample (B = baseline, S = stress-induced, D = post-dex, A = post-cotrosyn)
- *cort1_raw* - cort value of first blood sample from assay
- *cort2_raw* - cort value of second blood sample from assay
- *cort3_raw* - cort value of third blood sample from assay
- *cort1_correct* - cort value of first blood sample after efficiency correction
- *cort2_correct* - cort value of second blood sample after efficiency correction
- *cort3_correct* - cort value of third blood sample after efficiency correction
- *cort_assay* - identifies which assay the samples were run in
- *extract_efficiency* - extraction efficiency used for corrections
- *ria_or_eia* - was the sample run by ELISA or RIA
- *note* - any notes from field or lab work for this sample

## snaps

- *ubox* - combination of unit (site) and box used for merging
- *unit* - unit (field site identity)
- *box* - nest box (unique within unit)
- *experiment* - identified the experiment this individual was a part of
- *treatment* - identifies exact treatment (here cold or control are relevant)
- *pend_in* - day of year when pendant HOBO (temperature logger) was installed
- *pend_out* - day of year when pendant HOBO (temperature logger) was removed
- *start* - start date and time of first cold snap treatment
- *end* - end date and time of first cold snap treatment
- *snap_type* - type of treatment at first cold snap
- *start2* - start date and time of second cold snap treatment
- *end2* - end date and time of second cold snap treatment
- *snap_type2* - type of treatment at second cold snap

## raw_hobo

Each file is the temperature record from a single nest. In the file name, the field site and box number are identified by the first numbers (e.g., 1_10 is for field site '1', nest box '10'). This number is used in the script to join the temperature record to the appropriate nest. Within each file there are three columns:

- *blank* - index column with record number
- *Date-Time (EST)* - date and time of recording
- *CH: 1 - Temperature...* - Temperature reading in degrees Celcius
- *Host Connected* - internal HOBO info, not useful
- *End of File* - internal HOBO info, not useful