# NEWA project configuration of the Ensembles

Please note that most setups use **modified MYNN**  version available in https://github.com/newa-wind/Mesoscale and documented in [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2682604.svg)](https://doi.org/10.5281/zenodo.2682604).

## Explanation for the various digits of the sensitivity experiments that refers to the code available in GitHub

| digit | option | convention |
|---|---|---|
| 1 | IC/BC data |	E: ERA5, I: ERA-Interim, M: MERRA2, C: CFSR2, F: FNL |
| 2 | Land IC |		same as digit 1 (E, I, M, C, F), G: GLDAS |
| 3  |   SST data 	|	S: OSTIA, H: HRSST, O: OISST, or same as digit 1 (E, I, M, C, F) |
| 4  |   WRF version |	6: WRFV3.6.1, 8: WRFV3.8.1 |
| 5   |  Roughness option |	1: constant, 2: annual cycle, 3: aggregated |
| 6  |   Separator underscore | |
| 7  |  Land Surface Model |  Code as in WRF: Thermal diffusion=1, NOAH=2, RUC=3, CLM4=4, PLX=7 |
| 8  |   PBL scheme |  Code as in WRF: YSU=1, MYJ=2, QNSE=4, MYNN2=5, MYNN3=6, ACM2=7 |
|9    | Surface layer |	Code as in WRF: Revised MM5=1, M-O=2, QMSE=4, MYNN=5, P-X=7 |
|10  |  Modified PBL and surface layer? | no=0, yes=1. The requited modifications are available in https://github.com/newa-wind/Mesoscale and documented in [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2682604.svg)](https://doi.org/10.5281/zenodo.2682604) |
| 14-15 | Cloud Microphysics    |   Code as in WRF: WSM5=04, Thompson=08, Thompson+aerosol=28 |
| 16-17 | Convective scheme (D1,D2)	 |    Code as in WRF: No=00, K-F=01, B-M=02, Grell-Devenyi=93 |
| 18-19 | SW/LW radiation |	 Code as in WRF: CAM=03, RRTMG=04, Fast RRTMG=24 |
| 20-21 | Separator (if need) + extra option |  A, B, C, see table below |

For example: EES81_2521040004 is the production run with: ERA5 atmosphere and land (EE), OSTIA SST (S), WRF Version 3.8.1 (8), cosntant roughness (1), NOAH LSM (2), MYNN2 (5), M-O (2), modified PBL (1), WSM5 microphysics (04), no convection (00), and RRTMG radiation (04).

Extra options:

| Code | option |
|---|---|
|EES81_2551040004_A | lower wavelength in nudging |
|EES81_2551040004_B| larger relaxation zone near the domain borders|
|EES81_2551040004_C| two-way nesting|
|EES81_2551040004_D| radiation timestep 3s in all domains|
|EES81_2551040004_E| radiation timestep 12s in all domains|
|EES81_2551040004_F| icing options: iceblade_opt = 1; sum_qcqi_wsm = 0|
|EES81_2551040004_G| icing options: iceblade_opt = 1; sum_qcqi_wsm = 1|
|EES81_2551040004_H| grid nudging in all (D1, D2, D3) domains|
|EES81_2551040004_H| grid nudging in D1 domain|
|EES81_2551040004_J| spectral nudging in all (D1, D2, D3) domains|
|EES81_3551040004_A| standard VEGPARM.TBL|
|EES81_4550040004_A| standard MPTABLE.TBL|
|EES81_4550040004_B| opt_sfc=2 in the NOAH-MP scheme|
|EES82_2551040004_A| standard VEGPARM.TBL|

