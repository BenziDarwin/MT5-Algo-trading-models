# Algo Bot - MT5 Trading Algorithm

A machine learning-based trading algorithm that uses historical OHLC data from MetaTrader 5 (MT5) to predict future price movements on forex pairs like XAUUSD.

## Features

- **MT5 Integration**: Connects to MetaTrader 5 to fetch live trading data
- **Data Pipeline**: HOLC (High, Open, Low, Close) data processing and feature engineering
- **Machine Learning Models**: Gradient Boosting and PyTorch neural networks for price prediction
- **Model Persistence**: Pre-trained model included (`best_model_improved.pth`)

## Prerequisites

- Python 3.8 or higher
- MetaTrader 5 terminal installed and running
- Active MT5 account (demo or live)

## Installation

### 1. Clone the Repository
```bash
git clone <repository-url>
cd algo_bot
```

### 2. Create Virtual Environment
```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

Required packages:
- `pandas` - Data manipulation
- `numpy` - Numerical computing
- `scikit-learn` - Machine learning algorithms
- `torch` - Deep learning framework
- `MetaTrader5` - MT5 terminal connection
- `python-dotenv` - Environment variable management
- `matplotlib` - Data visualization
- `seaborn` - Statistical visualization

### 4. Configure Environment Variables

Create a `.env` file in the project root by copying the example file:

```bash
copy env.example .env
```

Edit `.env` with your MT5 credentials:

```env
MT5_LOGIN=5045407623
MT5_PASSWORD="Your MT5 Password"
MT5_SERVER="MetaQuotes-Demo"
MT5_PAIR="XAUUSD"
MT5_TIMEFRAME="30MIN"
```

**Configuration Details:**
- `MT5_LOGIN`: Your MT5 account login number
- `MT5_PASSWORD`: Your MT5 account password
- `MT5_SERVER`: MT5 server name (e.g., "MetaQuotes-Demo" for demo accounts)
- `MT5_PAIR`: Trading pair (default: "XAUUSD" for Gold/USD)
- `MT5_TIMEFRAME`: Timeframe for analysis ("1HR" or "30MIN")

## Usage

### Running the Pipeline

Execute the Jupyter notebook to process data and train models:

```bash
jupyter notebook HOLC_pipeline.ipynb
```

The notebook will:
1. Initialize MT5 connection using your credentials
2. Fetch 1 year of historical OHLC data
3. Preprocess and engineer features
4. Train machine learning models
5. Evaluate model performance
6. Save predictions and visualizations

### Project Structure

```
algo_bot/
├── env.example              # Example environment variables
├── HOLC_pipeline.ipynb      # Main analysis and modeling notebook
├── main.py                  # Entry point (to be implemented)
├── README.md                # This file
├── data/
│   ├── best_model_improved.pth    # Pre-trained PyTorch model
│   └── ONE_YEAR_DATA.csv          # Historical OHLC data
└── models/                  # Directory for model artifacts
```

## Troubleshooting

### MT5 Connection Issues
- Ensure MetaTrader 5 terminal is running
- Verify credentials in `.env` file
- Check that the server name matches your account type (Demo/Live)
- Ensure your MT5 account has API access enabled

### Environment Variables Not Loading
- Verify `.env` file is in the project root directory
- Check for typos in variable names
- Ensure no spaces around `=` signs in `.env` file

## License

[Add your license information here]

## Support

For issues or questions, please refer to the notebook's documentation or check MetaTrader 5 API documentation.
