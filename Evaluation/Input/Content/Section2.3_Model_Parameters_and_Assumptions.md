### 2.3.1 Absorption

The model parameter `Specific intestinal permeability`  for S-omeprazole was optimized to best match clinical data (see  [Section 2.3.4](#235-automated-parameter-identification)). The same parameter value was assumed for R-omeprazole.

The dissolution of the capsule formulation was implemented via an empirical Weibull dissolution equation with parameters `Dissolution time (50% dissolved)` and `Dissolution shape` fitted to observed data. A `Lag time ` = 30 min was used to account for the gastric emptying time.

### 2.3.2 Distribution

Physico-chemical parameter values of S- and R-omeprazole were set to the reported values (see [Section 2.2.1](#221-in-vitro-and-physico-chemical-data)) except for lipophilicity of S-omeprazole, which was estimated with i.v. data. It was assumed that the major binding partner in plasma is albumin.

After testing the available organ-plasma partition coefficient and cell permeability calculation methods available in PK-Sim, observed clinical data were best described by choosing the partition coefficient calculation by `Rodgers and Rowland` and cellular permeability calculation by `PK-Sim Standard`.

The same distribution model and parameter values were assumed for R-omeprazole, as no i.v. data are available for R-omeprazole.

### 2.3.3 Metabolism and Elimination

Two linear metabolic pathways for S- and R-omeprazole were implement in the model:

* CYP2C19
* CYP3A4

To describe multiple dose oral solution data, time-dependent autoinhibition (TDI) on CYP2C19 was added as irreversible inhibition / Mechanism-based inactivation as described by [Wu 2014](#5-references).

Competitive inhibition of CYP2C19 by both isomers was implemented in addition to TDI ([Liu 2005](#5-references)).

Simulation results suggested that the expression of CYP2C19 isoenzymes in the GI tract as provided by the RT-PCR PK-Sim database is significantly preventing R-omeprazole from entering the circulation. This was less apparent for S-omeprazole. To note, while the absolute mean CYP3A4 abundance in liver (1.03e7 pmol per liver) and the intestinal/liver CYP3A4 ratio in PK-Sim default individual are similar to values used in other models, the relative intestinal CYP2C19 and CYP2D6 abundances differ ([Table 6](#table-6)). The relative expression of CYP2C19 in gut was therefore reduced according to [Olivares-Morales 2016](#5-references) for the final model.

| **Ratio**                                | **[Olivares-Morales 2016](#5-references)**<sup>1</sup> | **[Galetin and Houston 2006](#5-references)**<sup>2</sup> | **GastroPlus** | **RT-PCR PK-Sim** | **Comment**                                                  |
| ---------------------------------------- | ------------------------------------------------------ | --------------------------------------------------------- | -------------- | ---------------- | ------------------------------------------------------------ |
| CYP3A4/2C19 relative abundance liver     | 9.8                                                    | 11.1                                                      | 8.1            | 5.68             | CYP2C19 abundance in liver 1.8-fold higher than  other literature sources |
| CYP3A4/2C19 relative abundance intestine | 43.8                                                   | 43.0                                                      | -              | 1.28             | CYP2C19 abundance in intestine 22-fold higher  than other literature sources |
| CYP3A4/2D6 relative abundance liver      | 17.1                                                   | 19.4                                                      | 14.2           | 10.80            | CYP2D6 abundance in liver 1.6-fold higher than  other literature sources |
| CYP3A4/2D6 relative abundance intestine  | 83.8                                                   | 86.0                                                      | -              | 8.64             | CYP2D6 abundance in intestine 6-fold higher than  other literature sources |
| CYP3A4 abundance Small intestine/liver   | 0.66%                                                  | -                                                         | -              | 0.44%            | in range with literature                                     |
| CYP2C19 abundance Small intestine/liver  | 0.15%                                                  | -                                                         | -              | 1.95%            | 23-fold higher than in literature                            |
| CYP2D6 Small intestine/liver             | 0.14%                                                  | -                                                         | -              | 0.55%            | 4-fold  higher than in literature                            |

**Table 6:**<a name="table-6"></a> Comparison of CYP3A4, CYP2C19 and CYP2D6 relative abundance in liver and small intestine from different literature sources. <sup>1</sup> Based on Sjörgen 2014: CYP relative expressions (pmol/mg_mic_p) from Paine 2006 calibrated against total intestinal CYP3A4 abundance. <sup>2</sup> Mean hepatic and intestinal relative abundance based on Rowland and Yeo 2003 and Paine 2006

Additionally, renal plasma clearance was implemented ([Wu 2014](#5-references)).

### 2.3.4 Observer for racemic omeprazole

Omeprazole concentrations in peripheral venous blood plasma at any specific time points were obtained by adding the simulated concentrations of two enantiomers together at the corresponding time points to generate the omeprazole PK profiles, according to the following formula:

*fQ_art\*(C_pls_art_Eso+C_pls_art_R_O) +fQ_bon\*(C_pls_bon_Eso+C_pls_bon_R_O)+fQ_fat\*(C_pls_fat_Eso + C_pls_fat_R_O)+fQ_mus\*(C_pls_mus_Eso + C_pls_mus_R_O) +fQ_skn\*(C_pls_skn_Eso + C_pls_skn_R_O)*

where *fQ_* are fraction of blood flow and *C_pls_* concentrations in plasma compartment respectively in the arterial (*art*), bone (*bon*), fat (*fat*), muscle (*mus*) or skin (*skn*) tissues. *Eso* and *R_O* stand for S- and R-omeprazole respectively.

### 2.3.5 Automated Parameter Identification

Following parameter values were estimated for the base model:

| **Parameter**                                    | **Compound** |
| ------------------------------------------------ | ------------ |
| Lipophilicity                                    | S-Omeprazole |
| Specific intestinal permeability (transcellular) | S-Omeprazole |
| Dissolution time (Weibull)                       | S-Omeprazole |
| Dissolution shape (Weibull)                      | S-Omeprazole |
| Specific CL_2C19                                 | S-Omeprazole |
| Specific CL_2C19                                 | R-Omeprazole |
| Specific CL_3A4                                  | S-Omeprazole |
| Specific CL_3A4                                  | R-Omeprazole |