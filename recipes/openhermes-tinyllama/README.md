
# Instructions to train OpenHermes TinyLlama with SFT

This model is fine-tuned via SFT, we used the [`Ritvik19/open-hermes-2_5-reformatted`](https://huggingface.co/datasets/Ritvik19/open-hermes-2_5-reformatted) dataset, which is a reformatted filtered version of the [`teknium/OpenHermes-2.5`]('https://huggingface.co/datasets/teknium/OpenHermes-2.5) dataset and was used to train OpenHermes 2.5 and Nous Hermes 2 series of models.

See below for commands to train these models.

## Full training examples

You can finetune a model on any 16GB GPU, using QLoRA. A recipe involving DPO will come soon 🤗.


```shell
ACCELERATE_LOG_LEVEL=info accelerate launch --config_file recipes/accelerate_configs/multi_gpu.yaml --num_processes=1 scripts/run_sft.py recipes/openhermes-tinyllama/sft/config_qlora.yaml --load_in_4bit=false
```
