# rotp_analyses
Repo for Reflecting on the Pandemic project analyses

Analyses Plan (pulled from preregistration)

Pre-Analytic Data Processing
Data Prep and Cleaning
Exclude Ineligible Participants 


•	Document and remove ineligible participants. Participants in either study branch will be excluded from analysis for the following reasons: 
o	Participant takes any of the surveys more than once (we will keep only the first set of responses). 
o	Participant does not complete the baseline (T1) survey.
o	Participant takes less than or equal to ⅓ of the median time to complete the T1 survey.
o	Participant not successfully randomized to intervention/control condition. 
•	In addition, participants in the physio branch will be excluded from the study for the following reasons:
o	Participant does not complete the baseline (T1) blood sample. 
o	Participant did not meet medical eligibility criteria at prescreening and was inadvertently included in the study.
o	Participant did not meet medical eligibility criteria at T3 and/or T4. 

Recode & Create New Variables


•	Create a binary variable for education by simplifying the responses into two groups: 
o	1 = More than a high school degree
o	2 = High school degree or less
•	Create a variable for participant retention, identifying the point in the study at which participants dropped out. Participants will be grouped into the following categories:
o	1 = Dropped out after completing T1 (baseline) and being successfully randomized, but before completing intervention/control task. 
o	2 = Dropped out after completing T2, including intervention/control task, but before completing T3 survey.
o	3 = Dropped out after completing T3 survey, but before completing T3 blood sample (physio branch), or T4 survey (non-physio branch). 
o	4 = Dropped out after completing T3 blood sample but before completing T4 survey (physio branch). 
o	5 = Dropped out after completing T4 survey, but before completing T4 blood sample (physio branch). 
o	6 = Successfully completed T4 blood sample (physio branch) or T4 survey (non-physio branch). 

Calculate Summary Scores


•	Reverse score items and calculate summary scores for all scales as indicated by scoring instructions for the respective scales. 
•	Calculate alphas and conduct confirmatory factor analysis for the CO mindset scale. If indicated, calculate subscale scores. 

Multiple imputation

Examine Data & Descriptive Statistics 


•	Examine data and calculate descriptive statistics (e.g. mean, SD, range, etc.) for all variables:
o	Overall
o	Separately by condition
o	Change over time. For variables with repeated measures, we will also create plots to visualize change over time in the two conditions. 

Equivalence Testing
Baseline Equivalence by Group Assignment 


•	We will examine baseline differences across conditions for demographic and individual difference variables that were measured at baseline (T1) using the appropriate test for the variable type and the number of variables tested (e.g., t-test, anova, or chi-square).
o	Demographics
	Race, gender, income, education, age, religion, marital status, location, political affiliation, household composition, caregiving, vaccination status, employment status
o	Individual Differences
	Self-fulfilling meta mindset, controllable meta mindset, Big 5 personality, trait optimism, self-efficacy, primal world belief, pandemic-related hardships, SEH mindset, COVID history
•	Baseline differences in mindsets, primary, and secondary outcome variables are modeled as part of the mixed models conducted as part of our analyses described below. 

Baseline Equivalence by Retention


•	We will explore differences in retention for study level variables, demographics, and individual differences that were measured at baseline (T1) using the appropriate test for the variable type and number of variables tested (e.g., t-test, anova, or chi-square).
o	Study level variables
	Condition
o	Demographics
	Race, gender, education, income, age, religion, location, political affiliation, household composition, caregiving, marital status, vaccination status, employment status
o	Individual Differences
	Self-fulfilling meta mindset, controllable meta mindset, extroversion, openness, emotional stability, agreeableness, conscientiousness, trait optimism, self-efficacy, primal world belief, pandemic-related hardships, SEH mindset, COVID history
•	We will report any differences in retention if we find that any variables differ significantly. 



Confirmatory Analyses

Manipulation Check

Overview


•	This analysis aims to evaluate the effect of the CO mindset intervention on CO mindset. We aim to determine if there are differences in CO mindset by condition over time (T1, T2, T3, and T4).
Hypothesis


•	The change in CO mindset over time (T1, T2, T3, and T4) will differ across conditions, with participants in the CO mindset intervention condition showing a significantly greater increase in this mindset over time. 
o	This will be represented by a significant coefficient for the time variable for the treatment reference (the CO mindset intervention) group in the output of the mixed model. 
•	We will consider a failure of manipulation to have occurred if no significant differences from over time across conditions are observed. 

Analytic Plan


•	We will run longitudinal mixed effects models predicting the trajectory (i.e. slope) of CO mindset over time (T1, T2, T3, and T4). 

Primary Outcome Analyses

Overview


•	This analysis aims to evaluate the effect of the CO mindset intervention on PTG outcomes. As discussed in Outcomes, we will be measuring PTG using the C-PTGI and domain-specific measures of life meaning, resilience, and personal relationships. 
•	We plan to run separate mixed-effects models for each of these PTG measures to determine if they change over the course of the study (T1, T3 and T4) and if this change differs across conditions. 
•	In addition, we plan to run factor analyses to determine whether these measures (and/or individual C-PTGI subscales) can be grouped into combined indices, either of overall PTG or of specific PTG domains (meaning, resilience, etc.). If so, we plan to also run mixed-effects models examining changes in these combined indices over time (T1, T3, and T4).

Hypothesis


•	The change in PTG outcomes over time will differ across conditions, with participants in the CO mindset intervention condition showing a significantly greater increase in PTG over time (T1, T3, and T4). 
o	This will be represented by a significant coefficient for the time variable for the treatment reference (the CO mindset intervention) group in the output of the mixed model. 

Analytic Plan


•	We will run longitudinal mixed models predicting the trajectory (i.e. slope) of PTG over time (T1, T3, and T4). 

Mediation Analyses

Overview


•	We aim to evaluate whether any observed effects of condition on PTG are driven by effects of condition on CO mindset. We will run a separate mediation model for every PTG measure that shows a main effect for condition x time (see above for full list of PTG measures). 

Hypothesis


•	CO mindset at T2 will partially mediate the relationship between condition and PTG. We will run separate serial mediations using PTG at T3 and T4 as our outcome variables. 

Analytic Plan


•	All mediation models will be conducted using the Lavaan package in R. Condition will be our independent variable, CO mindset will be our mediator, and a PTG measure will be our outcome variable. 
o	Condition will be coded as a binary variable (1 = CO mindset intervention, 0 = control)
o	CO mindset will be calculated as CO mindset at T2, controlling for CO mindset at T1. 
o	PTG will be calculated as the score of the chosen PTG outcome measure at either T3 or T4, controlling for PTG score at T1. 

Model


Serial Mediation Analysis

Overview


•	We aim to evaluate whether any observed effects of condition on PTG are serially mediated by SFMM and CO mindset. We will run a separate serial mediation model for every PTG measure that shows a main effect for condition x time (see above for a full list of PTG measures). 

Hypothesis


•	SFMM and CO mindset (T2) will partially mediate the relationship between condition and PTG. We will run separate mediation models using PTG at T3 and T4 as our outcomes.

Analytic Plan


•	All mediation models will be conducted using the Lavaan package in R. We will model all paths as outlined in Hayes’ model 6, with condition as our independent variable, SFMM as M1, CO mindset as M2, and a PTG measure as our outcome variable. 
o	Condition will be coded as a binary variable (1 = CO mindset intervention, 0 = control)
o	SFMM will be calculated as SFMM at T2, controlling for SFMM at T1.
o	CO mindset will be calculated as CO mindset at T2, controlling for CO mindset at T1. 
o	PTG will be calculated as the score of the chosen PTG outcome measure at either T3 or T4, controlling for PTG score at T1. 

Model



Post-Traumatic Growth (Qualitative)

Overview


•	As discussed in Outcomes, this series of analyses aims to evaluate the effect of the CO mindset intervention on the following four domains of post-traumatic growth, as measured by free response questions:
o	Life meaning
o	Personal relationships
o	Perceptions of communities/society
o	Sense of fragility/durability
•	We plan to conduct thematic analysis of the free responses using a mix of inductive and deductive approaches to identify how participants in each condition differ in their experiences of post-traumatic growth in each of these domains. 

Hypotheses


•	We expect the following themes to emerge as differences between the CO mindset intervention and control groups:
o	Life meaning
	Participants in the CO mindset intervention group will be more likely to express that they have experienced a greater sense of meaning in life, greater appreciation of life, increased gratitude, and/or changes in life priorities, as a result of their experiences during the COVID-19 pandemic.
o	Personal relationships
	Participants in the CO mindset intervention group will be more likely to express that have deepened their relationships with friends and family, felt more satisfied with their social relationships, and/or prioritized their relationships more, as a result of their experiences during the COVID-19 pandemic. 
o	Perceptions of communities/society
	Participants in the CO mindset intervention group will be more likely to express that they feel more invested in helping their communities/society, feel a greater sense of unity in their communities/society, and/or perceive their communities/society more positively, as a result of their experiences during the COVID-19 pandemic.
o	Sense of fragility/durability
	Participants in the CO mindset intervention group will be more likely to express a greater sense of durability and resilience, and a lower sense of fragility, in the face of future challenges and catastrophes as a result of their experiences during the COVID-19 pandemic. 

Analysis Plan


•	We will conduct thematic analysis of the free responses and compare themes that emerge across conditions. The stages of the thematic analysis are as follows:
o	Generate an initial set of codes for free responses deductively based on areas of growth commonly reported in the post-traumatic growth literature. 
o	Randomly sample 50 participants from each condition and generate a set of codes inductively based on these responses. 
o	Compare codes generated inductively vs. deductively and generate a finalized codebook.
o	Have multiple raters read through responses and categorize according to codebook. Calculate inter-rater reliability. 
o	Generate and review themes separately for each condition according to thematic analysis protocols as outlined by Braun and Clarke (2006).
o	Compare themes that emerge in each condition and evaluate whether these themes align with hypotheses. 

Secondary Outcome Analyses

Overview


•	This series of analyses aim to evaluate the effect of the CO mindset intervention on a range of outcome variables:
o	Positive and negative affect (PANAS)
o	Depression and anxiety (PHQ-4)
o	Physical health
o	Mental health
o	Quality of life
o	Social well-being (MHC-SF Social Well-Being subscale)
o	C-PTGI Subscales
	new possibilities
	relating to others
	spiritual change
	personal strength
	appreciation of life. 
•	We aim to determine if there is a change in these exploratory outcomes over time (T1, T3, and T4) and if this change differs across conditions. 

Analytic Plan


•	We will run longitudinal mixed models predicting the trajectory (i.e. slope) of the exploratory outcomes over time (T1, T3, and T4).

Exploratory Analyses
Mediation Analyses - Behavioral

Overview


•	The purpose of this series of analyses is to explore whether the relationship between condition and PTG is mediated by any of the following exploratory mindsets:
o	Well-being growth mindset
o	Stress mindset
o	Cognitive flexibility
o	Controllable meta mindset

Analytic Plan


•	All mediation models will be conducted using the Lavaan package in R. Condition will be our independent variable, one of the above exploratory mediators will be our mediator, and a PTG measure will be our outcome variable. 
o	Condition will be coded as a binary variable (1 = CO mindset intervention, 0 = control)
o	Exploratory mediator will be calculated as the exploratory mediator score at T3, controlling for the score at T1. 
o	PTG will be calculated as the score of the chosen PTG outcome measure at either T3 or T4, controlling for PTG score at T1. 

Model


Exploratory Moderation Analyses - Behavioral

Overview


•	The purpose of this series of exploratory analyses is to explore the potential moderating role of demographic and individual difference variables on the relationship between condition and secondary outcomes. As described in Objectives, we will include a wide range of demographics and or individual difference variables in these analyses, where indicated.

Analytic Plan


•	Re-run the appropriate models outlined in our primary and secondary analyses including an interaction effect with the moderator of interest. 


Analysis Plan - Physiological Data
Exploratory Immune Modeling Analyses

Overview


•	This exploratory project will take a multiverse approach to comparing a couple of different options for variable reduction/feature selection with respect to the immune variables to determine the best course of action for immune-analyses with a transparent, empirically-driven approach. Specifically, we will compare a) immune composites created using EFA as secondary treatment outcomes of the mindset intervention to b) a regularized model with all immune proteins modeled individually. We will also crosscheck our results with analysis from single proteins with well known functions (CRP, IL1-β, TNF-ɑ, IL-6, and IL-10). 

Analytic Plan


•	Immune composites:
o	Exploratory factor analysis (using robust estimators due to expected outliers in immune data)
o	Potentially CFA in a second dataset (in the situation that this is possible, EFA will be done in the larger of the two datasets)
o	Longitudinal measurement invariance will be explored to determine ability for aggregates to validly quantify change before inclusion in the below models. If MI is not supported, will explore if measurement invariance is a function of treatment group.
o	Latent variables will be modeled as outcomes in a latent growth model with treatment group as a time invariant predictor. If the model won’t estimate, latent variable values will be extracted from the EFA and used as observed variables to reduce the number of parameters estimated.
•	Regularized models
o	Latent growth models with individual proteins as outcomes of treatment group will be fit. 

Exploratory Outcome Analyses - Physiological


Overview


•	This series of analyses aim to evaluate the effect of the CO mindset intervention on immune composites/individual biomarkers (see above).
•	We aim to determine if there is a change in the level of these immunity variables over time (T1, T3, and T4) and if this change differs across conditions. 

Analytic Plan


•	We will run longitudinal mixed models predicting the trajectory (i.e. slope) of immunity variables from over time (T1, T3, and T4).  

Exploratory Mediation Analyses - Physiological

Overview


•	We plan to conduct three sets of mediation analysis using immunity variables as our outcome measures:
o	Mediation analysis to determine if the hypothesized effects of the intervention on immunity variables are mediated by changes in CO mindset. 
o	Serial mediation analyses to examine whether the relationship between CO mindset and immunity variables is itself mediated by changes in the following mindsets and behavioral variables: 
	Positive and negative affect (PANAS)
	Depression and anxiety (PHQ-4)
	Physical health
	Mental health
	Quality of life
	Social well-being (MHC-SF Social Well-Being subscale)
	Life meaning (MLQ - abridged) 
	Resilience (BRS) 
	Personal relationships
	Controllable meta mindset
o	Serial mediation analyses to determine if the hypothesized effects of the CO mindset intervention on CO mindset (and consequently on immunity variables) are themselves mediated by SFMM. 

Analytic Plan


•	All mediation models will be conducted using the Lavaan package in R. See previous sections for sample analytic plans for simple and serial mediation models. 

Exploratory Moderation Analyses - Physiological

Overview


•	The purpose of this series of analyses is to explore the potential moderating role of demographic and individual difference variables on the relationship between condition and immunity variables. As described in Objectives, we will include a wide range of demographic and or individual difference variables in these analyses, where indicated:

Analytic Plan


•	Re-run the appropriate models outlined in our primary and secondary analyses including an interaction effect with the moderator of interest. 

