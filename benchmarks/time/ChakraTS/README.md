# ChakraTS on TIME

Evaluation results of **ChakraTS** ([YHat Labs](https://yhatlabs.com), model card: https://huggingface.co/yhatlabs/ChakraTS) on all 98 TIME tasks (50 datasets, short / medium / long terms), from the version of the model updated in November 2026.

- ChakraTS is a pretrained time-series model served through an API. These results use its `pro` preset, with the full history before each window sent as context and nine quantiles (0.1 to 0.9).
- Files follow the TIME layout: `{dataset}/{freq}/{term}/{config.json, metrics.npz, predictions.npz}`, written with `timebench.evaluation.saver.save_window_predictions` at the benchmark settings (official `datasets.yaml` prediction lengths and test lengths).
- `scripts/compute_local_leaderboard.py` over this folder: MASE (norm.) 0.623, CRPS (norm.) 0.522.

Contact: shubham@yhatlabs.com
