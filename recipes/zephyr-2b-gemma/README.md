
# Instructions to train Zephyr 2B Gemma with SFT

This model is fine-tuned via SFT, we used the [`HuggingFaceH4/deita-10k-v0-sft`](https://huggingface.co/datasets/HuggingFaceH4/deita-10k-v0-sft) dataset, which was used to train Zephyr-7B-Gemma.

See below for commands to train these models.

## Full training examples

You can finetune a model on any 16GB GPU, using QLoRA. A recipe involving DPO will come soon 🤗.


```shell
ACCELERATE_LOG_LEVEL=info accelerate launch --config_file recipes/accelerate_configs/multi_gpu.yaml --num_processes=1 scripts/run_sft.py recipes/zephyr-2b-gemma/sft/config_qlora.yaml --load_in_4bit=false
```
