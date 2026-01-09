# signal-scope

## Overview
A Python package for analyzing time-series signals with trend, volatility, drift, regime shift, and anomaly detection metrics. Designed for finance, forecasting, sensor data, and fast exploratory analysis.

**Version:** 0.1.0  
**Author:** Ryan Sabouhi  
**License:** MIT

## Recent Changes
- 2026-01-09: Initial package creation with all core modules
- Fixed turning_points function to handle list inputs by converting to numpy array
- Switched build backend from poetry-core to hatchling for proper PEP 621 compliance

## Project Structure
```
├── pyproject.toml          # PEP 621 compliant package config (hatchling backend)
├── README.md               # Package documentation
├── LICENSE                 # MIT License
├── signal_scope/           # Main package directory
│   ├── __init__.py         # Package exports
│   ├── core.py             # Main analyze_ts() function
│   ├── metrics.py          # Signal analysis metrics
│   └── visualize.py        # Matplotlib visualization
├── tests/                  # Test suite
│   ├── __init__.py
│   ├── test_core.py
│   └── test_metrics.py
├── run_demo.py             # Demo script
└── demo.csv                # Sample data file
```

## Core Features
- **trend_strength(x)**: Normalized linear correlation with index
- **volatility(x)**: Standard deviation normalized by mean magnitude
- **drift(x)**: Difference between last and first value
- **turning_points(x)**: Count of local maxima + minima
- **anomaly_score(x)**: Z-score based anomaly measure
- **analyze_ts(path, col, plot)**: All-in-one CSV analysis function

## Usage
```python
from signal_scope.core import analyze_ts

result = analyze_ts("demo.csv", col="value", plot=True)
print(result)
```

## Running Tests
```bash
python -m pytest tests/ -v
```

## Building for PyPI
```bash
pip install build
python -m build
```

## Dependencies
- numpy
- pandas
- matplotlib
- scipy
