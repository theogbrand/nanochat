# nanochat training report

Generated: 2025-10-15 16:40:09

## Environment

### Git Information
- Branch: master
- Commit: 67aaca9 (dirty)
- Message: export NANOCHAT_BASE_DIR so child processes get it too

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
- Characters: 330,660
- Lines: 8,077
- Files: 42
- Tokens (approx): 82,665
- Dependencies (uv.lock lines): 2,004

Run started: 2025-10-15 16:40:16

---

## Tokenizer training
timestamp: 2025-10-15 16:41:29

- max_chars: 2,000,000,000
- doc_cap: 10,000
- vocab_size: 65,536
- train_time: 53.9190
- num_special_tokens: 9
- token_bytes_min: 1
- token_bytes_max: 32
- token_bytes_mean: 6.9197
- token_bytes_std: 2.8748


## Tokenizer evaluation
timestamp: 2025-10-15 16:41:41

### Comparison with GPT-2

| Text Type | Bytes | GPT-2 Tokens | GPT-2 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 404 | 4.50 | 375 | 4.85 | +7.2% |
| korean | 893 | 745 | 1.20 | 712 | 1.25 | +4.4% |
| code | 1259 | 576 | 2.19 | 492 | 2.56 | +14.6% |
| math | 1834 | 936 | 1.96 | 966 | 1.90 | -3.2% |
| science | 1112 | 260 | 4.28 | 228 | 4.88 | +12.3% |
| fwe-train | 4208518 | 900364 | 4.67 | 856883 | 4.91 | +4.8% |
| fwe-val | 4670204 | 1001940 | 4.66 | 954023 | 4.90 | +4.8% |

### Comparison with GPT-4

| Text Type | Bytes | GPT-4 Tokens | GPT-4 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 387 | 4.70 | 375 | 4.85 | +3.1% |
| korean | 893 | 364 | 2.45 | 712 | 1.25 | -95.6% |
| code | 1259 | 309 | 4.07 | 492 | 2.56 | -59.2% |
| math | 1834 | 832 | 2.20 | 966 | 1.90 | -16.1% |
| science | 1112 | 249 | 4.47 | 228 | 4.88 | +8.4% |
| fwe-train | 4208518 | 874799 | 4.81 | 856883 | 4.91 | +2.0% |
| fwe-val | 4670204 | 974174 | 4.79 | 954023 | 4.90 | +2.1% |


## Base model training
timestamp: 2025-10-15 20:14:23

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
- Minimum validation bpb: 0.8119
- Final validation bpb: 0.8119
- CORE metric estimate: 0.2275
- MFU %: 48.19%
- Total training flops: 3.917670e+19
- Total training time: 193.58m
- Peak memory usage: 75422.02MiB


## Base model loss
timestamp: 2025-10-15 20:17:45

- train bpb: 0.8146
- val bpb: 0.8120
- sample 0: <|bos|>The capital of France is Paris. It is the largest city in France and the capital of the country.
- sample 1: <|bos|>The chemical symbol of gold is Au. It is a soft, malleable, ductile, and a good conductor of
- sample 2: <|bos|>If yesterday was Friday, then tomorrow will be Friday. If tomorrow is Friday, then tomorrow will be Friday. If tomorrow is
- sample 3: <|bos|>The opposite of hot is cold. The opposite of cold is cold. The opposite of hot is hot.
- sample 4: <|bos|>The planets of the solar system are: Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Neptune,
- sample 5: <|bos|>My favorite color is red. I love it because it is a warm color and it is a color
- sample 6: <|bos|>If 5*x + 3 = 13, then x is a factor of 5. If 5*x + 3 = 


## Base model evaluation
timestamp: 2025-10-15 20:21:53

- Model: base_model (step 21400)
- CORE metric: 0.2206
- hellaswag_zeroshot: 0.2631
- jeopardy: 0.1138
- bigbench_qa_wikidata: 0.5169
- arc_easy: 0.5449
- arc_challenge: 0.1331
- copa: 0.3400
- commonsense_qa: 0.1155
- piqa: 0.3711
- openbook_qa: 0.1253
- lambada_openai: 0.3674
- hellaswag: 0.2707
- winograd: 0.3407
- winogrande: 0.0750
- bigbench_dyck_languages: 0.1240
- agi_eval_lsat_ar: 0.0924
- bigbench_cs_algorithms: 0.3432
- bigbench_operators: 0.1476
- bigbench_repeat_copy_logic: 0.0000
- squad: 0.2451
- coqa: 0.2096
- boolq: -0.0671
- bigbench_language_identification: 0.1817


## Midtraining
timestamp: 2025-10-15 20:37:02

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
- Minimum validation bpb: 0.4156


## Chat evaluation mid
timestamp: 2025-10-15 20:44:13

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
- ARC-Easy: 0.2576
- ARC-Challenge: 0.2491
- MMLU: 0.2468
- GSM8K: 0.0265
- HumanEval: 0.0549
- ChatCORE metric: 0.0172


## Chat SFT
timestamp: 2025-10-15 20:50:51

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
- Training loss: 1.2296
- Validation loss: 1.0673


## Chat evaluation sft
timestamp: 2025-10-15 20:56:46

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
- ARC-Easy: 0.2567
- ARC-Challenge: 0.2671
- MMLU: 0.2601
- GSM8K: 0.0516
- HumanEval: 0.0549
- ChatCORE metric: 0.0303


## Summary

- Characters: 330,660
- Lines: 8,077
- Files: 42
- Tokens (approx): 82,665
- Dependencies (uv.lock lines): 2,004

| Metric          | BASE     | MID      | SFT      | RL       |
|-----------------|----------|----------|----------|----------|
| CORE            | 0.2206   | -        | -        | -        |
| ARC-Challenge   | -        | 0.2491   | 0.2671   | -        |
| ARC-Easy        | -        | 0.2576   | 0.2567   | -        |
| GSM8K           | -        | 0.0265   | 0.0516   | -        |
| HumanEval       | -        | 0.0549   | 0.0549   | -        |
| MMLU            | -        | 0.2468   | 0.2601   | -        |
| ChatCORE        | -        | 0.0172   | 0.0303   | -        |

Total wall clock time: 4h16m
