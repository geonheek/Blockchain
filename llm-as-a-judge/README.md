# LLM-as-a-Judge for ERC-20 Spender Detection

This project evaluates whether an LLM can distinguish malicious and benign ERC-20 spenders using only summarized on-chain behavioral features.

Claude API was used as the LLM judge.

## Features

Seven spender-level features were provided to the models:

1. Approval count
2. Unique owner count
3. Unlimited approval count
4. Execution count
5. Token diversity
6. Approval-to-execution time gap
7. Contract status

Ground-truth labels were not included in the LLM input.

## Experimental Conditions

Four prompting conditions were evaluated.

| Condition | Prompt setup |
| --- | --- |
| A | Few-shot |
| B | Domain knowledge |
| C | Few-shot + domain knowledge |
| D | C + edge cases + chain-of-thought |

The conditions were evaluated separately rather than incrementally modifying a single prompt.

## Data Split

The experiment used separate data partitions for model development and evaluation.

- Test set: 200 samples
- Validation set: 100 samples
- Few-shot example pool: separate from validation and test data

The classification threshold for LLM scores was selected using only the validation set.

The test labels were not exposed to the LLM prompt.

## Baseline

Logistic Regression using the same seven behavioral features was used as a baseline.

| Model / Condition | ROC-AUC |
| --- | ---: |
| Logistic Regression | 0.695 |
| A | 0.757 |
| B | 0.684 |
| C | 0.741 |
| D | **0.821** |

For Condition D:

- Accuracy: 72.0%
- Malicious precision: 69.3%
- Malicious recall: 79.0%

## Stability

To examine sensitivity to few-shot example selection, the experiment was repeated with different random seeds.

Observed ROC-AUC values:

```text
0.835
0.810
0.815
