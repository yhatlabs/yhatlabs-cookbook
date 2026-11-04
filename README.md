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

[`benchmarks/`](benchmarks/) holds our leaderboard submissions (fev-bench, GIFT-Eval) and a notebook that reproduces them.

## Learn more

- Documentation: https://yhatlabs.com/models/docs
- Python library: https://github.com/yhatlabs/yhatlabs-python
- Models: https://yhatlabs.com/models

## License

The code and result files in this repository are released under the [Apache License 2.0](LICENSE). The models are not
distributed; they are served through the API under the [YHat Labs terms](https://yhatlabs.com/terms).
