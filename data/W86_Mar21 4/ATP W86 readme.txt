PEW RESEARCH CENTER
Wave 86 American Trends Panel 
Dates: March 15-March 28, 2021
Mode: Web 
Sample: Subsample with KnowledgePanel oversample
Language: English and Spanish
N=3,375

***************************************************************************************************************************
NOTES


The Wave 86 survey is Pew Research Center's 2021 National Survey of Latinos (NSL). The sample consisted of all ATP panel members who identified as Hispanic in the annual profile surve plus an oversample of Hispanic panel members from KnowledePanel that were of Mexican or Central American ancestry or had an educational attainment of high school diploma or less. 

The W86 dataset contains the following created variables. SPSS syntax for computing some of these variables is included in the SYNTAX section below.
 - SELFNAT_ORIG_W86 is the original SELFNAT question asked in the survey
 - SELFNAT_W86 is backcoded to include Mexico and Cuba
 - F_BIRTHPLAC_EXPANDED uses SELFNAT but is backcoded to include Mexico, Cuba, Dominican Republic and Central America to be used in weighting (see methods report for weighting details)
 - CVDECON13_TOTAL_W86 combines all items (a-c) in CVDECON13_W86 and is 1 if "yes" to any item and 2 if "no" to all items.
 - CVDECON13_14_TOTAL_W86 combines all items (a-c) in CVDECON13_W86 and CVDECON14_W86. It is 1 if "yes" to any item and 2 if "no" to all items.
 - PRIMARY_LANGUAGE_W86 is a language proficiency (English and Spanish) variable created from LAN1 - LAN4
 - COVID_SELFUM_W86 is a summary variable for self-reported Covid exposure based on COVIDSELFa-e
 - COVID_SELFUM2_W86 is a summary variable for self-reported Covid exposure, included vaccinated, based on COVIDSELFa-e
 - SUM_HISPDISCR_NUM_W86 sums the number of experiences (1, "Yes, has happened") from HISPDISCRb-i
 - HISPDISCR_NUM_W86 summary variable for SUM_HISPDISCR_NUM_W86  (1 "0-4", 2 "5-8")
 - HISPDISCR_NUM3_W86 summary variable for SUM_HISPDISCR_NUM_W86  (1 "0", 2 "1 or more")
 - USVSCOOCMB_A_W86 summary variable of USVSCOO1_a_W86, USVSCOO2_a_W86 and USVSCOO3_a_W86
 - USVSCOOCMB_B_W86 summary variable of USVSCOO1_b_W86, USVSCOO2_b_W86 and USVSCOO3_b_W86
 - USVSCOOCMB_C_W86 summary variable of USVSCOO1_c_W86, USVSCOO2_c_W86 and USVSCOO3_c_W86
 - USVSCOOCMB_D_W86 summary variable of USVSCOO1_d_W86, USVSCOO2_d_W86 and USVSCOO3_d_W86
 - USVSCOOCMB_E_W86 summary variable of USVSCOO1_e_W86, USVSCOO2_e_W86 and USVSCOO3_e_W86
 - USVSCOOCMB_F_W86 summary variable of USVSCOO1_f_W86, USVSCOO2_f_W86 and USVSCOO3_f_W86
 - USVSCOOCMB_G_W86 summary variable of USVSCOO1_g_W86, USVSCOO2_g_W86 and USVSCOO3_g_W86
 - MIGUSAGAINCMB_W86 summary variable for MIGUSAGAIN1_W86 and MIGUSAGAIN2_W86
 - DISCRCOOCMB_W86 summary variable for DISCRCOO1_W86 and DISCRCOO2_W86

Variables OPENRACE_W86_DETAILED_1 through OPENRACE_W86_COLLAPSED_other are coded responses to the open-ended question OPENRACE. These variables are included in the dataset to match how they are reported in the topline that accompanies this release. 

Variables NATIVITY1_W86, IMMGEN_W86, NATIVITY2_W86 and IMMGEN2_W86 are recodes of SELFNAT and MOTHERNAT and FATHERNAT. These variables are included in the dataset to match how they are reported in the topline that accompanies this release. 

For a small number of respondents with high risk of identification, certain values have been randomly swapped with those of lower risk cases with similar characteristics.


***************************************************************************************************************************
WEIGHTS 


WEIGHT_W86 is the weight for the sample. Data for all Pew Research Center reports are analyzed using this weight.


***************************************************************************************************************************
Releases from this survey:


April 20, 2021 "Most Latinos say U.S. immigration system needs big changes"
https://www.pewresearch.org/fact-tank/2021/04/20/most-latinos-say-u-s-immigration-system-needs-big-changes/

July 15, 2021 "For U.S. Latinos, COVID-19 Has Taken a Personal and Financial Toll"
https://www.pewresearch.org/race-ethnicity/2021/07/15/for-u-s-latinos-covid-19-has-taken-a-personal-and-financial-toll/

November 4, 2021 "Majority of Latinos Say Skin Color Impacts Opportunity in America and Shapes Daily Life"
https://www.pewresearch.org/hispanic/2021/11/04/majority-of-latinos-say-skin-color-impacts-opportunity-in-america-and-shapes-daily-life/

January 20, 2022 "Latinos See U.S. as Better Than Place of Family’s Ancestry for Opportunity, Raising Kids, Health Care Access"
https://www.pewresearch.org/race-ethnicity/2022/01/20/latinos-see-u-s-as-better-than-place-of-familys-ancestry-for-opportunity-raising-kids-health-care-access/

February 14, 2022 "Around four-in-ten Latinos in U.S. worry that they or someone close to them could be deported"
https://www.pewresearch.org/fact-tank/2022/02/14/around-four-in-ten-latinos-in-u-s-worry-that-they-or-someone-close-to-them-could-be-deported/


***************************************************************************************************************************
SYNTAX

*/Please create CVDECON13_TOTAL as follows and include variable in dataset.
compute CVDECON13_TOTAL_W86=99.
if CVDECON13_a_W86=1 or CVDECON13_b_W86=1 or CVDECON13_c_W86=1 CVDECON13_TOTAL_W86=1.
if (CVDECON13_a_W86=2 or CVDECON13_a_W86=3) and (CVDECON13_b_W86=2 or CVDECON13_b_W86=3) and (CVDECON13_c_W86=2 or CVDECON13_c_W86=3) CVDECON13_TOTAL_W86=2.

Variable labels CVDECON13_TOTAL_W86 'CVDECON13, combined'.
Value labels CVDECON13_TOTAL_W86 1 'Said yes to at least one' 2 'Said no or NA to all' 99 'Refused or said no/NA to all'.

*/Please create CVDECON13_14_TOTAL as follows and include variable in dataset:

compute CVDECON13_14_TOTAL_W86=99.
if CVDECON13_a_W86=1 or CVDECON13_b_W86=1 or CVDECON13_c_W86=1 or CVDECON14_a_W86=1 or CVDECON14_b_W86=1 or CVDECON14_c_W86=1 CVDECON13_14_TOTAL_W86=1.
if (CVDECON13_a_W86=2 or CVDECON13_a_W86=3) and (CVDECON13_b_W86=2 or CVDECON13_b_W86=3) and (CVDECON13_c_W86=2 or CVDECON13_c_W86=3) and 
((CVDECON14_a_W86=2 or CVDECON14_a_W86=3) and (CVDECON14_b_W86=2 or CVDECON14_b_W86=3) and (CVDECON14_c_W86=2 or CVDECON14_c_W86=3))  CVDECON13_14_TOTAL_W86=2.

Variable labels CVDECON13_14_TOTAL_W86 'CVDECON13 and CVDECON14, combined'.
Value labels CVDECON13_14_TOTAL_W86 1 'Said yes to at least one' 2 'Said no or NA to all' 99 'Refused or said no/NA to all'.
EXECUTE.

*/Please create PRIMARY_LANGUAGE as follows and include variable in dataset:

compute Spnspk=LAN1_W86.
compute Spnrd=LAN2_W86.
compute Engspk=LAN3_W86.
compute Engrd=LAN4_W86.
EXECUTE.
 
recode Spnspk Spnrd Engspk Engrd (1=2)(2=1)(else=0).
 
compute English = Engspk + Engrd.
compute Spanish = Spnspk + Spnrd.
EXECUTE.
 
compute Language = English - Spanish.
compute PRIMARY_LANGUAGE_W86 = Language.
EXECUTE.
 
recode PRIMARY_LANGUAGE_W86 (2,3,4=1)(-1,0,1=2)(-2,-3,-4=3).
ADD VALUE LABELS PRIMARY_LANGUAGE_W86 (1) English dominant (2) Bilingual (3) Spanish dominant.
VARIABLE LABELS PRIMARY_LANGUAGE_W86 Primary language of respondent.
EXECUTE.


*/Please create COVID_SELFSUM and COVID_SELFSUM2 as follows and include variable in dataset:

compute COVID_SELFSUM_W86=99.
IF (COVID_SELF_B_W86=1 OR COVID_SELF_C_W86=1 OR COVID_SELF_E_W86=1) COVID_SELFSUM_W86=1.
IF (COVID_SELF_B_W86=2 AND COVID_SELF_C_W86=2 AND COVID_SELF_E_W86=2) COVID_SELFSUM_W86=2.
IF (COVID_SELF_B_W86=99 AND COVID_SELF_C_W86=99 AND COVID_SELF_E_W86=99) COVID_SELFSUM_W86=99.
EXECUTE.

variable labels COVID_SELFSUM_W86 Self-reported COVID.
value labels COVID_SELFSUM_W86 1 'Tested positive for COVID or antibodies, or pretty sure they had COVID' 2 'None of the self-reported Covid measures' 99 'DK, DK/No'. 

compute COVID_SELFSUM2_W86=99.
IF (COVID_SELF_A_W86=1 OR COVID_SELF_B_W86=1 OR COVID_SELF_C_W86=1 OR COVID_SELF_E_W86=1) COVID_SELFSUM2_W86=1.
IF (COVID_SELF_A_W86=2 AND COVID_SELF_B_W86=2 AND COVID_SELF_C_W86=2 AND COVID_SELF_E_W86=2) COVID_SELFSUM2_W86=2.
IF (COVID_SELF_A_W86=99 AND COVID_SELF_B_W86=99 AND COVID_SELF_C_W86=99 AND COVID_SELF_E_W86=99) COVID_SELFSUM2_W86=99.
EXECUTE.

variable labels COVID_SELFSUM2_W86 Self-reported COVID or vaccination.
value labels COVID_SELFSUM2_W86 1 'Had vaccine, tested positive for COVID or antibodies, or pretty sure they had COVID' 2 'None of the self-reported Covid measures' 99 'DK, DK/No'. 

*/Please create SUM_HISPDISCR_NUM and HISPDISCR_NUM as follows and include variable in dataset:

compute hispdiscrb=0.
compute hispdiscrc=0.
compute hispdiscrd=0.
compute hispdiscre=0.
compute hispdiscrf=0.
compute hispdiscrg=0.
compute hispdiscrh=0.
compute hispdiscri=0.

IF HISPDISCR_b_W86=1 hispdiscrb=1.
IF HISPDISCR_c_W86=1 hispdiscrc=1.
IF HISPDISCR_d_W86=1 hispdiscrd=1.
IF HISPDISCR_e_W86=1 hispdiscre=1.
IF HISPDISCR_f_W86=1 hispdiscrf=1.
IF HISPDISCR_g_W86=1 hispdiscrg=1.
IF HISPDISCR_h_W86=1 hispdiscrh=1.
IF HISPDISCR_i_W86=1 hispdiscri=1.


compute SUM_HISPDISCR_NUM_W86= hispdiscrb+hispdiscrc+hispdiscrd+hispdiscre+hispdiscrf+hispdiscrg+hispdiscrh+hispdiscri.
VARIABLE LABELS SUM_HISPDISCR_NUM_W86 SUM_HISPDISCR_NUM_W86. Flag for discrimination experiences in the past 12 months for each experience listed.
recode SUM_HISPDISCR_NUM_W86 (0 thru 4=1) (5 thru 8=2) into HISPDISCR_NUM_W86.
VARIABLE LABELS HISPDISCR_NUM_W86 HISPDISCR_NUM_W86. Number of discrimination experiences in the past 12 months.
VALUE LABELS HISPDISCR_NUM_W86
1 "0-4"
2 "5-8".

*/Creating variables to merge responses to USVSCOO1-3_a-g.
COMPUTE USVSCOOCMB_A_W86=0.
IF USVSCOO1_a_W86=1 or USVSCOO2_a_W86=1 or USVSCOO3_a_W86=1 USVSCOOCMB_A_W86=1.
IF USVSCOO1_a_W86=2 or USVSCOO2_a_W86=2 or USVSCOO3_a_W86=2 USVSCOOCMB_A_W86=2.
IF USVSCOO1_a_W86=3 or USVSCOO2_a_W86=3 or USVSCOO3_a_W86=3 USVSCOOCMB_A_W86=3.
IF USVSCOO1_a_W86=99 or USVSCOO2_a_W86=99 or USVSCOO3_a_W86=99  USVSCOOCMB_A_W86=99.
VARIABLE LABELS USVSCOOCMB_A_W86 [Combining USVSCOO1-3_a] How would you rate each of the following when comparing the United States to the country you came from? Treatment of the poor.
VALUE LABELS USVSCOOCMB_A_W86 1 'Better in the United States' 2 'Better where you came from' 3 'About the same' 99 'Refused'.

COMPUTE USVSCOOCMB_C_W86=0.
IF USVSCOO1_c_W86=1 or USVSCOO2_c_W86=1 or USVSCOO3_c_W86=1 USVSCOOCMB_C_W86=1.
IF USVSCOO1_c_W86=2 or USVSCOO2_c_W86=2 or USVSCOO3_c_W86=2 USVSCOOCMB_C_W86=2.
IF USVSCOO1_c_W86=3 or USVSCOO2_c_W86=3 or USVSCOO3_c_W86=3 USVSCOOCMB_C_W86=3.
IF USVSCOO1_c_W86=99 or USVSCOO2_c_W86=99 or USVSCOO3_c_W86=99  USVSCOOCMB_C_W86=99.
VARIABLE LABELS USVSCOOCMB_C_W86 [Combining USVSCOO1-3_c] How would you rate each of the following when comparing the United States to the country you came from? The strength of family ties.
VALUE LABELS USVSCOOCMB_C_W86 1 'Better in the United States' 2 'Better where you came from' 3 'About the same' 99 'Refused'.

COMPUTE USVSCOOCMB_D_W86=0.
IF USVSCOO1_d_W86=1 or USVSCOO2_d_W86=1 or USVSCOO3_d_W86=1 USVSCOOCMB_D_W86=1.
IF USVSCOO1_d_W86=2 or USVSCOO2_d_W86=2 or USVSCOO3_d_W86=2 USVSCOOCMB_D_W86=2.
IF USVSCOO1_d_W86=3 or USVSCOO2_d_W86=3 or USVSCOO3_d_W86=3 USVSCOOCMB_D_W86=3.
IF USVSCOO1_d_W86=99 or USVSCOO2_d_W86=99 or USVSCOO3_d_W86=99  USVSCOOCMB_D_W86=99.
VARIABLE LABELS USVSCOOCMB_D_W86 [Combining USVSCOO1-3_d] How would you rate each of the following when comparing the United States to the country you came from? The opportunity to get ahead.
VALUE LABELS USVSCOOCMB_D_W86 1 'Better in the United States' 2 'Better where you came from' 3 'About the same' 99 'Refused'.

COMPUTE USVSCOOCMB_E_W86=0.
IF USVSCOO1_e_W86=1 or USVSCOO2_e_W86=1 or USVSCOO3_e_W86=1 USVSCOOCMB_E_W86=1.
IF USVSCOO1_e_W86=2 or USVSCOO2_e_W86=2 or USVSCOO3_e_W86=2 USVSCOOCMB_E_W86=2.
IF USVSCOO1_e_W86=3 or USVSCOO2_e_W86=3 or USVSCOO3_e_W86=3 USVSCOOCMB_E_W86=3.
IF USVSCOO1_e_W86=99 or USVSCOO2_e_W86=99 or USVSCOO3_e_W86=99  USVSCOOCMB_E_W86=99.
VARIABLE LABELS USVSCOOCMB_E_W86 [Combining USVSCOO1-3_e] How would you rate each of the following when comparing the United States to the country you came from? The way immigrants are treated.
VALUE LABELS USVSCOOCMB_E_W86 1 'Better in the United States' 2 'Better where you came from' 3 'About the same' 99 'Refused'.

COMPUTE USVSCOOCMB_F_W86=0.
IF USVSCOO1_f_W86=1 or USVSCOO2_f_W86=1 or USVSCOO3_f_W86=1 USVSCOOCMB_F_W86=1.
IF USVSCOO1_f_W86=2 or USVSCOO2_f_W86=2 or USVSCOO3_f_W86=2 USVSCOOCMB_F_W86=2.
IF USVSCOO1_f_W86=3 or USVSCOO2_f_W86=3 or USVSCOO3_f_W86=3 USVSCOOCMB_F_W86=3.
IF USVSCOO1_f_W86=99 or USVSCOO2_f_W86=99 or USVSCOO3_f_W86=99  USVSCOOCMB_F_W86=99.
VARIABLE LABELS USVSCOOCMB_F_W86 [Combining USVSCOO1-3_f] How would you rate each of the following when comparing the United States to the country you came from? The conditions for raising children.
VALUE LABELS USVSCOOCMB_F_W86 1 'Better in the United States' 2 'Better where you came from' 3 'About the same' 99 'Refused'.

COMPUTE USVSCOOCMB_G_W86=0.
IF USVSCOO1_g_W86=1 or USVSCOO2_g_W86=1 or USVSCOO3_g_W86=1 USVSCOOCMB_G_W86=1.
IF USVSCOO1_g_W86=2 or USVSCOO2_g_W86=2 or USVSCOO3_g_W86=2 USVSCOOCMB_G_W86=2.
IF USVSCOO1_g_W86=3 or USVSCOO2_g_W86=3 or USVSCOO3_g_W86=3 USVSCOOCMB_G_W86=3.
IF USVSCOO1_g_W86=99 or USVSCOO2_g_W86=99 or USVSCOO3_g_W86=99  USVSCOOCMB_G_W86=99.
VARIABLE LABELS USVSCOOCMB_G_W86 [Combining USVSCOO1-3_g] How would you rate each of the following when comparing the United States to the country you came from? Access to healthcare services.
VALUE LABELS USVSCOOCMB_G_W86 1 'Better in the United States' 2 'Better where you came from' 3 'About the same' 99 'Refused'.


*/Creating variable to merge responses to MIGUSAGAIN1 and MIGUSAGAIN2.
COMPUTE MIGUSAGAINCMB_W86=$sysmis.
IF MIGUSAGAIN1_W86=1 or MIGUSAGAIN2_W86=1 MIGUSAGAINCMB_W86=1.
IF MIGUSAGAIN1_W86=2 or MIGUSAGAIN2_W86=2 MIGUSAGAINCMB_W86=2.
IF MIGUSAGAIN1_W86=3 or MIGUSAGAIN2_W86=3 MIGUSAGAINCMB_W86=3.
IF MIGUSAGAIN1_W86=99 or MIGUSAGAIN2_W86=99 MIGUSAGAINCMB_W86=99.
VARIABLE LABELS MIGUSAGAINCMB_W86 [Combining MIGUSAGAIN1 and MIGUSAGAIN2] If you could do it again, would you...?.
VALUE LABELS MIGUSAGAINCMB_W86 1 'Come to the United States' 2 'Stay where you were born' 3 'Move to a different country' 99 'Refused'.


*/Creating variable to merge responses to DISCROO1 and DISCROO2.
COMPUTE DISCRCOOCMB_W86=$sysmis.
IF DISCRCOO1_W86=1 or DISCRCOO2_W86=1 DISCRCOOCMB_W86=1.
IF DISCRCOO1_W86=2 or DISCRCOO2_W86=2 DISCRCOOCMB_W86=2.
IF DISCRCOO1_W86=3 or DISCRCOO2_W86=3 DISCRCOOCMB_W86=3.
IF DISCRCOO1_W86=4 or DISCRCOO2_W86=4 DISCRCOOCMB_W86=4.
IF DISCRCOO1_W86=99 or DISCRCOO2_W86=99 DISCRCOOCMB_W86=99.
VARIABLE LABELS DISCRCOOCMB_W86 [Combining DISCRCOO1 and DISCRCOO2] As far as you know, how does discrimination based on race or skin color in your home country compare to discrimination based on race or skin color in the U.S.? Are things in your home country generally….
VALUE LABELS DISCRCOOCMB_W86 1 'Better' 2 'Worse' 3 'About the same' 4 'Discrimination based on race or skin color is not an issue in my home country' 99 'Refused'.


