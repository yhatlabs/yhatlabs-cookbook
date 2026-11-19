# Benchmarks

ChakraTS results on public forecasting leaderboards, as submitted, and how to reproduce them. The standings are in the
[main README](../README.md#benchmark-standing-as-of-november-2026). The results use the `chakra-ts` model with its
`pro` preset, the same model the API serves.

## Files

- `fev_bench/ChakraTS/chakrats_api.csv`: the [fev](https://github.com/autogluon/fev) summary file (100 tasks).
- `gift_eval/ChakraTS/`: `all_results.csv` and `config.json` in the [GIFT-Eval](https://github.com/SalesforceAIResearch/gift-eval) format (97 configurations).
- `time/ChakraTS/`: the [TIME](https://github.com/zqiao11/TIME) submission, `config.json`, `metrics.npz` and `predictions.npz` for each of the 98 tasks, written with TIME's own evaluation code.
- `gift_eval/ChakraTS-Lab/`: our October 2026 GIFT-Eval entry for ChakraTS-Lab, unchanged.

## Reproduce

Each needs an API key (`YHAT_API_KEY`).

- **fev-bench:** the wrapper in the fev repository, [`models/chakrats_api/model.py`](https://github.com/autogluon/fev/tree/main/models/chakrats_api), runs any task through the API.
- **GIFT-Eval:** [`gift_eval/reproduce.ipynb`](gift_eval/reproduce.ipynb) (also `notebooks/ChakraTS.ipynb` in the [gift-eval](https://github.com/SalesforceAIResearch/gift-eval) repository). Run it from that repository's `notebooks/` folder; its quick mode reruns 13 configurations in a few minutes and prints each result next to the submitted row.
- **TIME:** `scripts/compute_local_leaderboard.py` in the [TIME](https://github.com/zqiao11/TIME) repository scores `time/ChakraTS/` (copied to its `output/results/`) against Seasonal Naive.
