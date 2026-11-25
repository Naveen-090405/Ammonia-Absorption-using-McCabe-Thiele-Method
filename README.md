# Ammonia Absorption — McCabe–Thiele Stage Calculation

A chemical engineering calculation implemented in Python to estimate the solvent requirement and theoretical number of equilibrium stages for removing ammonia from an air stream by absorption into water.

## Project overview

The notebook applies gas–liquid absorption fundamentals and the McCabe–Thiele graphical stepping method. It calculates gas flow using the ideal gas law, converts gas compositions to solute-free mass ratios, estimates the minimum solvent rate from equilibrium data, applies a 50% solvent excess, and steps between the equilibrium curve and operating line.

## Given conditions in the notebook

- Gas volumetric flow rate: 0.071 m³/s
- Temperature: 15°C (288.15 K)
- Pressure: 1 atm
- Inlet ammonia mole fraction: 0.10
- Required ammonia removal: 85%
- Solvent: water
- Actual solvent rate: 1.5 times the calculated minimum solvent rate
- Equilibrium data: tabulated `X_eq` and `Y_eq` arrays defined in the notebook

No external dataset file is required; the equilibrium data are entered directly in the Python code.

## Methodology

1. Convert gas volumetric flow to total molar flow using the ideal gas law.
2. Calculate air molar and mass flow rates.
3. Convert inlet and outlet ammonia compositions to solute-free mass ratios, `Y`.
4. Use the equilibrium data to estimate the liquid composition corresponding to the inlet gas condition.
5. Calculate the minimum liquid-to-gas ratio and minimum water flow rate.
6. Set the actual water flow to 1.5 times the minimum.
7. Construct the operating line.
8. Perform McCabe–Thiele staircase stepping between the equilibrium curve and operating line.
9. Estimate the fractional and whole theoretical stage counts and plot the equilibrium curve, operating line and stages.

## Results recorded in the notebook

| Quantity | Result |
|---|---:|
| Total gas flow | 0.003003 kmol/s |
| Air mass flow | 0.078292 kg/s |
| Inlet gas ratio, Y₁ | 0.065317 kg NH₃/kg air |
| Outlet gas ratio, Y₂ | 0.009797 kg NH₃/kg air |
| Minimum solvent rate | 0.068347 kg/s |
| Actual solvent rate | 0.102521 kg/s |
| Theoretical stages | 2.472 |
| Whole theoretical stages (rounded up) | 3 |

## Tools

Python, NumPy, Matplotlib.

## Run the notebook

Open `Ammonia_Absorption_McCabe_Thiele.ipynb` in Google Colab or Jupyter and run the cell. No separate data file is required.

## Assumptions and limitations

- The supplied equilibrium data are treated as the equilibrium relationship for this calculation.
- The notebook linearly extrapolates the final segment of the equilibrium data to obtain the required inlet-equilibrium point.
- The result is based on the specified operating conditions and the equilibrium data entered in the notebook; it is not a plant design without further validation.
