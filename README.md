# Assignement 2 - Human Value Detection Challenge

## Task description.
We address the task of [Human Value Detection](https://aclanthology.org/2022.acl-long.306/), a typical multi-label classification problem, using BERT-based models.

Each sample in the training set consists of 3 arguments: premise, conclusion, and stance.

E.g.:
- premise: fast food should be banned because it is really bad for your health and is costly.
- conclusion: we should ban fast food
- stance: in favour of

The dataset is labelled, hence for each sample we have the corresponding values, that may be 1 if present, 0 otherwise. Instead of considering all the categories, we logically merge low-level annotations into high-order values. As a consequence, we are tasked to predict 4 high-order categories:
- Openness to change
- Self-enhancement
- Conversation
- Self-transcendence

![Labels](/img/labels.png)

## Models
We pick 2 baselines (random and majority), and construct 3 different BERT-based models, each of them taking as input only the premise, premise and conclusion, or all the attributes. We then investigate whether additional context and information improve model performances or keep them unchanged. All the BERT models are imported from [Hugging-face](https://huggingface.co/models). All BERT-base pre-trained models come equipped with random initialized classification heads (linear layers).

![Bert model](/img/bert_cps.png)

## Metrics
For each of the 4 binary cateogories, we define f1 score metric, and the macro f1 score among the categories.

![F1 scores](/img/f1_scores.png)

All the results and comments can be found in the notebook.

## License
MIT license