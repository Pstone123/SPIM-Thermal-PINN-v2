# SPIM Thermal PINN — Diagnostic Study

## When Does Physics Help? A Diagnostic Study of Physics-Informed Neural Networks for Single-Phase Induction Motor Thermal Estimation

### Repository Structure

| File | Description |
|---|---|
| SPIM_Thermal_PINN_Journal.ipynb | Complete training and evaluation notebook |
| dataset_A_v2.csv | Dataset A — Training (stepped load, 25°C ambient) |
| dataset_B_final.csv | Dataset B1 — Moderate distribution shift |
| dataset_B2.csv | Dataset B2 — Severe shift (40°C ambient) |
| dataset_C_final.csv | Dataset C — Cold start (100 seconds) |
| dataset_D_v2.csv | Dataset D — Noisy measurements (5% Gaussian noise) |
| pmsm_small.csv | PMSM benchmark — Real test bench data (Kirchgässner et al., 2021) |

### Motor Parameters
- Motor: 1 HP, 230V, 50Hz Single-Phase Induction Motor
- Stator resistance (main): 2.02 Ω
- Stator resistance (auxiliary): 7.14 Ω
- Rotor resistance: 4.12 Ω
- Thermal capacitance: 25000 J/°C
- Heat transfer coefficient: 28 W/°C
- Bearing loss coefficient: 0.0005 Nm·s/rad

### Key Results

| Dataset | Condition | DNN MAE | PINN MAE | Winner |
|---|---|---|---|---|
| A | Training | 0.0660°C | 0.0785°C | DNN |
| B1 | Moderate shift | 0.4338°C | 0.4710°C | DNN |
| B2 | Severe shift (40°C ambient) | 1.8500°C | 1.8705°C | DNN |
| C | Cold start | 0.0629°C | 0.0786°C | DNN |
| D | Sensor noise | 0.1276°C | 0.1313°C | DNN |
| Self-supervised PINN | No labels | — | ~30°C | Fails |

### Requirements
- Python 3.x
- PyTorch
- scikit-learn
- pandas
- matplotlib
- numpy

### How To Run
Open `SPIM_Thermal_PINN_Journal.ipynb` in Google Colab and run cells in order.

### References
- Calasan et al. (2021). Applied Sciences, 11, 5102.
- Kirchgässner et al. (2021). IEEE Trans. Energy Convers.
- Raissi et al. (2017). arXiv.
