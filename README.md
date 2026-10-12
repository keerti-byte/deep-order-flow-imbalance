# Deep Order Flow Imbalance: Multi-Horizon Forecasting

Kolm et al. (2023) show that stationary order flow (OF) inputs outperform raw limit order book (LOB) inputs, and that predictability plateaus at around 2 average price changes. This project tests whether stationary order flow imbalance (OFI) extracted from deeper levels of the book (levels 2-5) can lift that R² plateau. The LSTM receives a wider stationary feature set of latent liquidity pressure, and the hypothesis is improved multi-horizon forecasting over a level-1 baseline.

Status:Data loading and level-1 baseline complete; LSTM training underway.

## Objectives
**Replication**: implement the multi-horizon regression framework on the FI-2010 benchmark dataset.
**Extension**: engineer multi-level OFI (levels 2-5) and test whether it improves on standard level-1 OFI.
**Modeling**: compare ARX and MLP baselines against an LSTM that captures temporal dependencies in high-frequency microstructure data.
Data

FI-2010 is a public benchmark of limit order book data for mid-price forecasting (Ntakaris et al., 2018). The raw files are not included in this repository because of their size. [Add where you downloaded it and which files or normalization you used.]

## Methodology
Targets: continuous returns 10, 20 and 50 ticks ahead.
Features: level-1 OFI, and extended multi-level OFI (levels 2-5).
Models: ARX, MLP, LSTM (PyTorch / scikit-learn).
Validation: strict chronological split. Days 1-8 for training, days 9-10 for testing, to prevent look-ahead bias.
Results

[Number's to be updated]

Model	Features	R² (10 ticks)	R² (20 ticks)	R² (50 ticks)
ARX	Level-1 OFI			
MLP	Level-1 OFI			
LSTM	Level-1 OFI			
LSTM	Levels 1-5 OFI			
## Limitations
FI-2010 covers only 10 trading days, so the test set is small and results may not generalize across market regimes.

## Repository structure
notebooks/: exploratory analysis and visualization of LOB mechanics
src/: data loading, feature engineering and model training
data/: location of the FI-2010 files (excluded from version control)
How to run

bash
conda create -n ofi python=3.11
conda activate ofi
pip install -r requirements.txt
python src/<your_training_script>.py

## References
Kolm, P. N., Turiel, J., and Westray, N. (2023). Deep order flow imbalance: Extracting alpha at multiple horizons from the limit order book. Mathematical Finance.
Ntakaris, A., Magris, M., Kanniainen, J., Gabbouj, M., and Iosifidis, A. (2018). Benchmark dataset for mid-price forecasting of limit order book data with machine learning methods. Journal of Forecasting.
