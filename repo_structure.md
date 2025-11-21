
YIELD_CURVE/
│
├── swap_data/                  # Raw input Excel files (SOFR OIS swap rates by tenor)
│
│
├── Plots/                      # Generated figures (NPV function, yield curve.)
│   ├── NPV_function.png
│   └── SOFR_yield_curve_highres.png
│
│
├── get_swap_curves.ipynb       # Builds the dataset by aggregating all Excel rate files
|   │                           # into a single, cleaned CSV panel
|   └── SOFR_panel_Date_Tenor_Rate_sorted.csv  
|                                  # Final preprocessed panel dataset used for curve building
│
├── zero_from_swap.ipynb        # Bootstraps the SOFR yield curve using the Solver
│                               # provided by `rateslib` and produces the analytical plots
│
├── zero_from_swap_recursive.ipynb
│                               # Implements the bootstrapping procedure manually
│                               # using a custom bisection root-finding algorithm
│                               # instead of the built-in Solver
|
├── Curves_outputs/             # CSV outputs of bootstrapped curves for specific dates
│   ├── Curves_at_2025-10-17.csv
│   └── Curves_at_2025-11-14.csv