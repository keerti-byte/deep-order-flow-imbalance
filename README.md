# Deep Order Flow Imbalance: Multi-Horizon Forecasting

A quantitative research project replicating and extending the methodology of Kolm, Turiel & Westray (2023). The goal is to forecast mid-price movements of a Limit Order Book (LOB) at multiple horizons using Order Flow Imbalance (OFI) as the primary predictive feature.
## 🎯Project Objectives

    **Replication**: Implement the multi-horizon regression framework using the FI-2010 benchmark dataset.
    **Extension**: Engineer Multi-Level OFI (Levels 2-5) to test if latent liquidity pressure from deeper order book levels improves predictive accuracy over standard Level-1 OFI.
    **Modeling**: Compare baseline ARX/MLP models against an LSTM architecture capable of capturing temporal dependencies in high-frequency market microstructure data.

## 🛠️ Tech Stack

    **Language**: Python
    **Data Manipulation**: Pandas, NumPy
    **Machine Learning**: PyTorch / Scikit-Learn
    **Environment**: Conda

## 📁 Repository Structure

    **notebooks/**: Exploratory data analysis and visualization of LOB mechanics.
    **src/**: Modularized source code for data loading, feature engineering, and model training.
    **data/**: Directory for the FI-2010 dataset (Raw data is excluded from version control due to size).

## 📈 Methodology

    **Target**: Continuous returns at 10, 20, and 50 ticks ahead.
    **Features**: Level 1 OFI, Extended Multi-Level OFI (Levels 2-5).
    **Validation**: Strict chronological train/test split (Days 1-8 for training, Days 9-10 for testing) to prevent look-ahead bias in time-series data.
