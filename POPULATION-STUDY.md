## HOW CTR CHANGES WITH AGE AND GENDER 
The CTR estimation method described in section "METHODOLOGY-CTR" has been applied on a subset of the CheXpert dataset[18]: a large public dataset with CXRs labeled for the presence of 14 observations. 
In this subset (called in this research CheXpertCTR dataset):

  - only PA images are extracted,
  - images labeled as positive to cardiomegaly and enlarged
  cardiomediastinum are excluded.

It results in 25369 CXRs with 34% female and 66% male, from 18 to 90-year-old. The mean age is 56.5±17.1.From the CheXpertCTR dataset an average CTR of 0.498 ± 0.089 was reported. 
A general increase in mean CTR isreported as the age of the patients increases: from 0.448 in 18-year-old to 0.562 in 90-year-old patients, showing an increase of the 25%. 
A mean value and a standard deviation of 0.507 ± 0.094 and 0.492 ± 0.085 has been reported for female and male respectively, showing a slightly higher mean CTR for females. 
This difference has been demonstrated to be significant (p-value < 0.5). Since a significant difference was reported, CXRs of males and females have been considered separately. 

Figure 1 shows how the predicted CTR changes according to age and gender. Both the trends appear to be fairly linear, showing similar mean values for younger patients, while females reach higher mean CTR values with increasing
age.
