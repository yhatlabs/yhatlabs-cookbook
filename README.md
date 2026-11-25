# YHat Labs Cookbook

This cookbook has runnable notebooks for our models on real data, from loading it to a scored result, and our benchmark
results with how to reproduce them.

[Website](https://yhatlabs.com) · [Docs](https://yhatlabs.com/models/docs) · [Get started](https://yhatlabs.com/models/signup) ·
[Hugging Face](https://huggingface.co/yhatlabs)

## Get started

One notebook per model, from install to a scored result in a few minutes. Each one opens in Colab.

| Notebook | What you do |
|---|---|
| [ChakraTS](getting-started/chakrats.ipynb) (API) | Forecast a week of electricity demand with ranges, check the model on past days, add what you know about the future, and fine-tune it |
| [ChakraTab](getting-started/chakratab.ipynb) (API) | Predict credit risk with probabilities, compare with standard models, see which columns matter, and predict house prices with ranges |
| [ChakraTS-OS-10M](getting-started/chakrats-os-10m.ipynb) (open weights) | The ChakraTS steps on your own machine, with [yhatmodels](https://github.com/yhatlabs/yhatmodels) |

## Recipes

The recipes use our hosted models through the [Python library](https://github.com/yhatlabs/yhatlabs-python) and need an
API key:

```bash
pip install -U "yhatlabs[plot]"
export YHAT_API_KEY=...    # create one at https://yhatlabs.com/models/signup
```

| Recipe | What you learn |
|---|---|
| [Forecasting with ChakraTab: drivers as columns](recipes/forecasting/forecasting_with_chakratab.ipynb) | Forecast daily series as a table of known drivers (paydays, promotions, calendar), compare with ChakraTS and their average in a backtest, and read each driver's effect |

More recipes are coming soon.

To run a model on your own machine with no API key, see [yhatmodels](https://github.com/yhatlabs/yhatmodels).

## Benchmarks

[`benchmarks/`](benchmarks/) holds our results on the public forecasting leaderboards as we submitted them, and how
to reproduce each one:

| Model | fev-bench | GIFT-Eval | TIME |
|---|---|---|---|
| [ChakraTS](https://huggingface.co/yhatlabs/ChakraTS) (API) | win rate 90.1%, skill score 51.4 | MASE 0.640, CRPS 0.436 | MASE 0.623, CRPS 0.522 |
| [ChakraTS-OS-10M](https://huggingface.co/yhatlabs/ChakraTS-OS-10M) (open weights) | skill score 49.9 | MASE 0.674, CRPS 0.461 | MASE 0.642, CRPS 0.537 |

GIFT-Eval and TIME scores are relative to a seasonal forecast (lower is better). For the current standings, see the
[fev-bench](https://huggingface.co/spaces/autogluon/fev-leaderboard), [GIFT-Eval](https://huggingface.co/spaces/Salesforce/GIFT-Eval)
and [TIME](https://huggingface.co/spaces/Real-TSF/TIME-leaderboard) leaderboards. ChakraTab is on
[TabArena](https://huggingface.co/spaces/TabArena/leaderboard), [RamanBench](https://huggingface.co/spaces/HTW-KI-Werkstatt/RamanBench)
and [STRABLE](https://soda-inria.github.io/strable), run by the benchmark maintainers through our API.

## License

The code and result files in this repository are released under the [Apache License 2.0](LICENSE). ChakraTS and
ChakraTab are served through the API under the [YHat Labs terms](https://yhatlabs.com/terms). The weights of
[ChakraTS-OS-10M](https://huggingface.co/yhatlabs/ChakraTS-OS-10M) are released under the
[Chakra Non-Commercial Model License](https://yhatlabs.com/model-license).
