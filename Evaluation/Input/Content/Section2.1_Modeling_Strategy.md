The general workflow for building an adult PBPK model has been described by Kuepfer et al. ([Kuepfer 2016](#5-references)). Relevant information on the anthropometry (height, weight) was gathered from the respective clinical study, if reported. Information on physiological parameters (e.g. blood flows, organ volumes, hematocrit) in adults was gathered from the literature and has been incorporated in PK-Sim® as described previously ([Willmann 2007](#5-references)). The  applied activity and variability of plasma proteins and active processes that are integrated into PK-Sim® are described in the publicly available 'PK-Sim® Ontogeny Database Version 7.3' ([PK-Sim Ontogeny Database Version 7.3](#5-references)).

The model includes distinct molecules for S- and R-omeprazole, the racemic omeprazole is represented by an observer that sums up the concentrations of S- and R-omeprazole. It was assumed that both isomers correspond to the half of the racemic omeprazole dose.

In general, the following step-wise workflow was followed:

1a. Define distribution and metabolism for S-omeprazole

1b. Mechanism based inactivation of CYP2C19 by omeprazole

2. Define S-omeprazole absorption based on p.o. 

3. Capsule formulation 

- 3a. Building racemic omeprazole

- 3b. Adjust CYP2C19 expression in gut

4. Define metabolism for R-omeprazole

5. Refine CYP3A4 metabolism on CYP2C19 PM data

6. Refine CYP2C19 metabolism on CYP2C19 EM data

The predefined “Standard European Male for DDI” individual was used (age = 30 y, weight = 73 kg, height = 176 cm, BMI = 23.57 kg/m2) until stated otherwise. CYP2C19 expression from the PK-Sim in-built RT-PCR database was added and adjusted as described in [Section 2.3.3](#233-metabolism-and-elimination).

Selection of the distribution model for S-omeprazole and estimation of the lipophilicity parameter were performed with i.v. data ([Wilder-Smith 2005](#5-references), [Hassan-Alin 2000](#5-references)).

The kinetics of CYP2C19 and CYP3A4 metabolization processes of S-omeprazole and R-omeprazole were estimated using the Parameter Identification module provided in PK-Sim® with i.v. and p.o. data including administration of S-, R- or racemic omeprazole, see [Table 3](#Table 3), [Table 4](#Table 4), and [Table 5](#Table 5) for more details. The kinetic parameters were assumed not to be identical for the isomers. For simulations of CYP2C19 poor metabolizers, the CYP2C19 pathway was switched off.

For studies in Japanese subjects, a typical Japanese subject (age = 30 y, weight = 61.87 kg, height = 168.99 cm, BMI = 21.67 kg/m2) was created in PK-Sim from predefined database “Japanese (2015)” by adding CYP3A4 and CYP2C19 expression from PK-Sim RT PCR database, and adapting CYP2C19 expression in gut as described in [Section 2.3.3](#233-metabolism-and-elimination).

Intestinal permeability of S-omeprazole was estimated by fitting the model to concentration-time data measured after p.o. administration of 20 or 40 mg given as solution ([Hassan-Alin 2005](#5-references)).

Parameters `Dissolution time (50% dissolved)` and `Dissolution shape`  describing the dissolution of capsule formulation were fitted to the data after single dose S-omeprazole 40 mg capsule ([Wilder-Smith 2005](#5-references)).

Details about input data (physicochemical, *in vitro* and clinical) can be found in [Section 2.2](#22-data).

Details about the structural model and its parameters can be found in [Section 2.3](#23-model-parameters-and-assumptions).

Population simulations of single and multiple i.v. or p.o. administration over a wide range of dose levels were conducted to visually compare the predicted concentration-time profile to the observed concentrations reported in the literature, in terms of mean and variability. The simulated populations matched the race (European or Asian) and the age-weight ranges reported in the respective clinical studies. A total of 1000 individuals were generated for studies in males only, while 2000 were generated for mixed gender populations. The concentration time profile was simulated for each virtual subject and summarized as geometric mean and 95% CI. The simulations were performed for extensive and poor CYP2C19 metabolizers.
