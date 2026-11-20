# YHat Labs Cookbook

Runnable recipes for the YHat Labs models: **ChakraTS** for time-series forecasting and **ChakraTab** for prediction on
tables. Each recipe is a notebook on public or synthetic data that runs with only an API key.

```bash
pip install -U "yhatlabs[plot]"
export YHAT_API_KEY=...    # https://yhatlabs.com/models
```

## Recipes

### Forecasting

| Recipe | What you learn |
|---|---|
| [Forecasting with ChakraTab: drivers as columns](recipes/forecasting/forecasting_with_chakratab.ipynb) | Forecast daily series as a table of known drivers (paydays, promotions, calendar), compare with ChakraTS and their average in a backtest, and read each driver's effect |

More recipes are on the way: tuning ChakraTS on your own series, known and past drivers, backtesting and calibration,
anomalies, prediction on tables with intervals and explanations.

## Benchmarks

ChakraTS is the best model across forecasting benchmarks.

### Benchmark standing (as of November 2026)

**ChakraTS** (time-series forecasting)

| Benchmark | Standing | Result | Leaderboard |
|---|---|---|---|
| fev-bench (Amazon) | 1st by win rate | Win rate 90.1%, skill score 51.4 | [fev-bench](https://huggingface.co/spaces/autogluon/fev-leaderboard) |
| GIFT-Eval (Salesforce) | 2nd among non-agentic models | MASE 0.640 | [GIFT-Eval](https://huggingface.co/spaces/Salesforce/GIFT-Eval) |
| TIME | 1st by MASE rank | MASE 0.624, CRPS 0.523 | [TIME](https://huggingface.co/spaces/Real-TSF/TIME-leaderboard) |

GIFT-Eval and TIME scores are normalized by Seasonal Naive (lower is better).

**ChakraTab** (prediction on tables)

| Benchmark | Standing | Leaderboard |
|---|---|---|
| TabArena | 3rd | [TabArena](https://huggingface.co/spaces/TabArena/leaderboard) |
| STRABLE (Inria) | 2nd by score | [STRABLE](https://soda-inria.github.io/strable) |
| RamanBench (HTW Berlin) | 3rd | [RamanBench](https://huggingface.co/spaces/HTW-KI-Werkstatt/RamanBench) |

[`benchmarks/`](benchmarks/) has the ChakraTS results as submitted and how to reproduce them.

## Learn more

- Documentation: https://yhatlabs.com/models/docs
- Python library: https://github.com/yhatlabs/yhatlabs-python
- Models: https://yhatlabs.com/models

## License

The code and result files in this repository are released under the [Apache License 2.0](LICENSE). The models are not
distributed; they are served through the API under the [YHat Labs terms](https://yhatlabs.com/terms).
