# ActionPiece

Rethinking Action Tokenization for Autoregressive Vision-Language-Action Models

[Project page](https://deepcybo-physai.github.io/ActionPiece/)

## Abstract

Action tokenizers define the action representations learned by autoregressive vision-language-action models. Reconstruction accuracy measures the fidelity of individual actions, while their physical relationships provide structure for learning across demonstrations. We introduce physical rank consistency (PRC) to measure neighborhood-order preservation through encoding and decoding, providing a common evaluation across token vocabularies and decoder architectures. Guided by this perspective, we develop ActionPiece, which jointly augments reconstruction with physical rank preservation in learned representations and quantization regularization over codeword assignments. Under the same Qwen3-VL-4B policy training setup, ActionPiece achieves 94.8% on LIBERO and 68.8% on unseen LIBERO-Plus. Component ablations improve both PRC and policy success, with the two objectives together performing best. Replacing the action tokenizer also achieves 71.9% on SimplerEnv and 51.5% mean success across VLA-Arena L0–L2 with standard next-token prediction. These results support physical relationship supervision as a useful principle for learning action representations for control.

[PhysBrain1.5](https://huggingface.co/collections/DeepCybo/physbrain-15) uses ActionPiece as its action tokenizer.

## Benchmark results

| Benchmark | ActionPiece success (%) |
| --- | ---: |
| LIBERO | 94.8 |
| LIBERO-Plus | 68.8 |
| SimplerEnv | 71.9 |
| VLA-Arena L0 / L1 / L2 | 82.2 / 42.7 / 29.5 |
| VLA-Arena overall | 51.5 |

The project page contains the full comparisons. LIBERO-Plus is evaluated without its demonstrations in policy training. SimplerEnv scores average five independent 24-episode repeats per task. VLA-Arena averages the 11 suites equally at each level.

## Key insight

PRC measures neighborhood-order preservation through encoding and decoding. The project figure compares fidelity and PRC with policy success using within-group ranks across 55 tokenizer–benchmark evaluations, and presents a matched LIBERO-Plus comparison.
