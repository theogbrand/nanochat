# nanochat training report

Generated: 2025-10-16 10:10:25

## Environment

### Git Information
- Branch: master
- Commit: af82c3a (dirty)
- Message: report

### Hardware
- Platform: Linux
- CPUs: 112 cores (224 logical)
- Memory: 2015.6 GB
- GPUs: 8x NVIDIA H100 80GB HBM3
- GPU Memory: 632.8 GB total
- CUDA Version: 12.8
- Hourly Rate: $24.00/hour

### Software
- Python: 3.10.12
- PyTorch: 2.8.0+cu128


### Bloat
- Characters: 339,535
- Lines: 8,397
- Files: 44
- Tokens (approx): 84,883
- Dependencies (uv.lock lines): 2,004

Run started: 2025-10-16 10:10:33

---

## Tokenizer training
timestamp: 2025-10-16 10:12:02

- max_chars: 2,000,000,000
- doc_cap: 10,000
- vocab_size: 65,536
- train_time: 76.6713
- num_special_tokens: 9
- token_bytes_min: 1
- token_bytes_max: 32
- token_bytes_mean: 6.9151
- token_bytes_std: 2.8736


## Tokenizer evaluation
timestamp: 2025-10-16 10:12:06

### Comparison with GPT-2

| Text Type | Bytes | GPT-2 Tokens | GPT-2 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 404 | 4.50 | 375 | 4.85 | +7.2% |
| korean | 893 | 745 | 1.20 | 721 | 1.24 | +3.2% |
| code | 1259 | 576 | 2.19 | 493 | 2.55 | +14.4% |
| math | 1834 | 936 | 1.96 | 966 | 1.90 | -3.2% |
| science | 1112 | 260 | 4.28 | 225 | 4.94 | +13.5% |
| fwe-train | 4208518 | 900364 | 4.67 | 856901 | 4.91 | +4.8% |
| fwe-val | 4908443 | 1059062 | 4.63 | 1010356 | 4.86 | +4.6% |

### Comparison with GPT-4

| Text Type | Bytes | GPT-4 Tokens | GPT-4 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 387 | 4.70 | 375 | 4.85 | +3.1% |
| korean | 893 | 364 | 2.45 | 721 | 1.24 | -98.1% |
| code | 1259 | 309 | 4.07 | 493 | 2.55 | -59.5% |
| math | 1834 | 832 | 2.20 | 966 | 1.90 | -16.1% |
| science | 1112 | 249 | 4.47 | 225 | 4.94 | +9.6% |
| fwe-train | 4208518 | 874799 | 4.81 | 856901 | 4.91 | +2.0% |
| fwe-val | 4908443 | 1029691 | 4.77 | 1010356 | 4.86 | +1.9% |


## Base model training
timestamp: 2025-10-16 13:21:58

- run: dummy
- depth: 20
- max_seq_len: 2048
- num_iterations: -1
- target_flops: -1.0000
- target_param_data_ratio: 20
- device_batch_size: 32
- total_batch_size: 524,288
- embedding_lr: 0.2000
- unembedding_lr: 0.0040
- weight_decay: 0.0000
- matrix_lr: 0.0200
- grad_clip: 1.0000
- eval_every: 250
- eval_tokens: 10,485,760
- core_metric_every: 2000
- core_metric_max_per_task: 500
- sample_every: 2000
- model_tag: 
- Number of parameters: 560,988,160
- Number of FLOPs per token: 3.491758e+09
- Calculated number of iterations: 21,400
- Number of training tokens: 11,219,763,200
- Tokens : Params ratio: 20.0000
- DDP world size: 8
- warmup_ratio: 0.0000
- warmdown_ratio: 0.2000
- final_lr_frac: 0.0000
- Minimum validation bpb: 0.8120
- Final validation bpb: 0.8120
- CORE metric estimate: 0.2074
- MFU %: 47.36%
- Total training flops: 3.917670e+19
- Total training time: 175.85m
- Peak memory usage: 75422.02MiB


## Base model loss
timestamp: 2025-10-16 13:23:22

- train bpb: 0.8148
- val bpb: 0.8121
- sample 0: <|bos|>The capital of France is Paris. It is the largest city in France and the second largest city in the
- sample 1: <|bos|>The chemical symbol of gold is Au. Gold is a soft, malleable, ductile, and malleable metal. It
- sample 2: <|bos|>If yesterday was Friday, then tomorrow will be tomorrow. If yesterday was yesterday, then tomorrow will be tomorrow. If yesterday was
- sample 3: <|bos|>The opposite of hot is cold. The opposite of cold is hot. The opposite of hot is cold.
- sample 4: <|bos|>The planets of the solar system are: Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Neptune,
- sample 5: <|bos|>My favorite color is red. I love red because it is the color of blood. I love red
- sample 6: <|bos|>If 5*x + 3 = 13, then x is a multiple of 5. If 5*x + 3 = 


## Base model evaluation
timestamp: 2025-10-16 13:27:22

- Model: base_model (step 21400)
- CORE metric: 0.2055
- hellaswag_zeroshot: 0.2655
- jeopardy: 0.0926
- bigbench_qa_wikidata: 0.5303
- arc_easy: 0.5297
- arc_challenge: 0.1149
- copa: 0.2600
- commonsense_qa: 0.0244
- piqa: 0.3613
- openbook_qa: 0.0960
- lambada_openai: 0.3701
- hellaswag: 0.2626
- winograd: 0.2821
- winogrande: 0.0687
- bigbench_dyck_languages: 0.0880
- agi_eval_lsat_ar: 0.1304
- bigbench_cs_algorithms: 0.4023
- bigbench_operators: 0.1619
- bigbench_repeat_copy_logic: 0.0000
- squad: 0.2146
- coqa: 0.2034
- boolq: -0.1178
- bigbench_language_identification: 0.1812


## Midtraining
timestamp: 2025-10-16 13:40:20

- run: dummy
- dtype: bfloat16
- max_seq_len: 2048
- device_batch_size: 32
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- init_lr_frac: 1.0000
- weight_decay: 0.0000
- final_lr_frac: 0.0000
- eval_every: 150
- eval_tokens: 10,485,760
- total_batch_size: 524,288
- Number of iterations: 765
- DDP world size: 8
- Minimum validation bpb: 0.4158


## Chat evaluation mid
timestamp: 2025-10-16 13:46:01

- source: mid
- task_name: None
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- ARC-Easy: 0.2605
- ARC-Challenge: 0.2679
- MMLU: 0.2547
- GSM8K: 0.0334
- HumanEval: 0.0671
- ChatCORE metric: 0.0289


## Chat SFT
timestamp: 2025-10-16 13:52:52

- run: dummy
- source: mid
- dtype: bfloat16
- device_batch_size: 4
- num_epochs: 1
- max_iterations: -1
- target_examples_per_step: 32
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- weight_decay: 0.0000
- init_lr_frac: 0.0200
- eval_every: 100
- eval_steps: 100
- eval_metrics_every: 200
- Training rows: 20,843
- Number of iterations: 651
- Training loss: 1.2217
- Validation loss: 1.0662


## Chat evaluation sft
timestamp: 2025-10-16 13:58:44

- source: sft
- task_name: None
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- ARC-Easy: 0.2618
- ARC-Challenge: 0.2432
- MMLU: 0.2599
- GSM8K: 0.0387
- HumanEval: 0.0549
- ChatCORE metric: 0.0227


## Chat RL
timestamp: 2025-10-16 14:42:09

- run: dummy
- source: sft
- dtype: bfloat16
- device_batch_size: 8
- examples_per_step: 16
- num_samples: 16
- max_new_tokens: 256
- temperature: 1.0000
- top_k: 50
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- weight_decay: 0.0000
- init_lr_frac: 0.0500
- num_epochs: 1
- save_every: 60
- eval_every: 60
- eval_examples: 400


## Chat evaluation rl
timestamp: 2025-10-16 14:44:36

- source: rl
- task_name: GSM8K
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- GSM8K: 0.0758


## Summary

- Characters: 339,535
- Lines: 8,397
- Files: 44
- Tokens (approx): 84,883
- Dependencies (uv.lock lines): 2,004

| Metric          | BASE     | MID      | SFT      | RL       |
|-----------------|----------|----------|----------|----------|
| CORE            | 0.2055   | -        | -        | -        |
| ARC-Challenge   | -        | 0.2679   | 0.2432   | -        |
| ARC-Easy        | -        | 0.2605   | 0.2618   | -        |
| GSM8K           | -        | 0.0334   | 0.0387   | 0.0758   |
| HumanEval       | -        | 0.0671   | 0.0549   | -        |
| MMLU            | -        | 0.2547   | 0.2599   | -        |
| ChatCORE        | -        | 0.0289   | 0.0227   | -        |

Total wall clock time: 3h48m
