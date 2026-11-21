# Benchmarks

Results of ChakraTS (served through the API) and ChakraTS-OS-10M (open weights) on public forecasting leaderboards, as
submitted, and how to reproduce them. The ChakraTS standings are in the
[main README](../README.md#benchmark-standing-as-of-november-2026).

## ChakraTS

The results use the `chakra-ts` model with its `pro` preset, the same model the API serves.

**Files**

- `fev_bench/ChakraTS/chakrats_api.csv`: the [fev](https://github.com/autogluon/fev) summary file (100 tasks).
- `gift_eval/ChakraTS/`: `all_results.csv` and `config.json` in the [GIFT-Eval](https://github.com/SalesforceAIResearch/gift-eval) format (97 configurations).
- `time/ChakraTS/`: the [TIME](https://github.com/zqiao11/TIME) submission, `config.json`, `metrics.npz` and `predictions.npz` for each of the 98 tasks, written with TIME's own evaluation code.
- `gift_eval/ChakraTS-Lab/`: our October 2026 GIFT-Eval entry for ChakraTS-Lab, unchanged.

**Reproduce.** Each needs an API key (`YHAT_API_KEY`).

- **fev-bench:** the wrapper in the fev repository, [`models/chakrats_api/model.py`](https://github.com/autogluon/fev/tree/main/models/chakrats_api), runs any task through the API.
- **GIFT-Eval:** [`gift_eval/reproduce.ipynb`](gift_eval/reproduce.ipynb) (also `notebooks/ChakraTS.ipynb` in the [gift-eval](https://github.com/SalesforceAIResearch/gift-eval) repository). Run it from that repository's `notebooks/` folder; its quick mode reruns 13 configurations in a few minutes and prints each result next to the submitted row.
- **TIME:** `scripts/compute_local_leaderboard.py` in the [TIME](https://github.com/zqiao11/TIME) repository scores `time/ChakraTS/` (copied to its `output/results/`) against Seasonal Naive.

## ChakraTS-OS-10M

[ChakraTS-OS-10M](https://huggingface.co/yhatlabs/ChakraTS-OS-10M) is our open-weight forecasting model (10.6M
parameters). It runs on your own machine with the [`yhatmodels`](https://github.com/yhatlabs/yhatmodels) library, with
no API key. The results use its default `pro` preset.

**Files**

- `fev_bench/ChakraTS-OS-10M/chakrats-os-10m.csv`: the fev summary file (100 tasks).
- `gift_eval/ChakraTS-OS-10M/`: `all_results.csv` and `config.json` (97 configurations), and `ChakraTS-OS-10M.ipynb`, the notebook that produced them.
- `time/ChakraTS-OS-10M/`: `config.json`, `metrics.npz` and `predictions.npz` for each of the 98 tasks.

Submitted in November 2026: fev-bench [#219](https://github.com/autogluon/fev/pull/219), GIFT-Eval [#260](https://github.com/SalesforceAIResearch/gift-eval/pull/260), TIME [#20](https://github.com/zqiao11/TIME/pull/20) (code) and [#65](https://huggingface.co/datasets/Real-TSF/TIME-Output/discussions/65) (results).

**Reproduce.** `pip install yhatmodels`, then:

- **fev-bench:** in the fev repository, `uv run python models/evaluate.py -m chakrats-os -b benchmarks/fev_bench/tasks.yaml -n chakrats-os-10m` (wrapper in `models/chakrats-os/`).
- **GIFT-Eval:** [`gift_eval/ChakraTS-OS-10M/ChakraTS-OS-10M.ipynb`](gift_eval/ChakraTS-OS-10M/ChakraTS-OS-10M.ipynb), run from the gift-eval repository's `notebooks/` folder (its first cell has the setup); its quick mode reruns 13 configurations in a few minutes.
- **TIME:** in the TIME repository, `bash scripts/run_chakrats_os.sh`.

Each one, rerun in a fresh environment on one NVIDIA H200, reproduced the submitted files exactly (fev-bench 45 min,
GIFT-Eval 59 min, TIME 19 min).

During early access the weights are gated on Hugging Face: request access on the model page, then sign in with
`hf auth login`. They are released under the Chakra Non-Commercial Model License, accepted once with a yhatlabs.com
account before the first download.
