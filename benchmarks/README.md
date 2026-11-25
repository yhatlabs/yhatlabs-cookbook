# Benchmarks

Our results on the public forecasting leaderboards, as submitted, and notebooks that rerun them with each benchmark's
own code and compare the new results with the submitted ones.

| Model | fev-bench | GIFT-Eval | TIME |
|---|---|---|---|
| [ChakraTS](https://huggingface.co/yhatlabs/ChakraTS) (API) | [results](fev_bench/ChakraTS/chakrats_api.csv) · [reproduce](fev_bench/ChakraTS/reproduce.ipynb) | [results](gift_eval/ChakraTS/all_results.csv) | [results](time/ChakraTS) |
| [ChakraTS-OS-10M](https://huggingface.co/yhatlabs/ChakraTS-OS-10M) (open weights) | [results](fev_bench/ChakraTS-OS-10M/chakrats-os-10m.csv) · [reproduce](fev_bench/ChakraTS-OS-10M/reproduce.ipynb) | [results](gift_eval/ChakraTS-OS-10M/all_results.csv) · [reproduce](gift_eval/ChakraTS-OS-10M/reproduce.ipynb) | [results](time/ChakraTS-OS-10M) · [reproduce](time/ChakraTS-OS-10M/reproduce.ipynb) |

Notebooks to reproduce ChakraTS on GIFT-Eval and TIME are coming soon.

Each notebook runs locally or in Colab. `MODE = "quick"` reruns a few tasks in minutes; `MODE = "full"` reruns the whole
benchmark. ChakraTS needs an API key (`YHAT_API_KEY`). ChakraTS-OS-10M runs on your own machine with
[yhatmodels](https://github.com/yhatlabs/yhatmodels); its full reruns on one NVIDIA H200 reproduced the submitted files
exactly (fev-bench 45 min, GIFT-Eval 59 min, TIME 19 min), and on other hardware the results differ only slightly. During
early access its weights are gated: request access on the model page, then sign in with `hf auth login`.

Leaderboards: [fev-bench](https://huggingface.co/spaces/autogluon/fev-leaderboard) ·
[GIFT-Eval](https://huggingface.co/spaces/Salesforce/GIFT-Eval) ·
[TIME](https://huggingface.co/spaces/Real-TSF/TIME-leaderboard). `gift_eval/ChakraTS-Lab/` is our October 2026 GIFT-Eval
entry, unchanged.
