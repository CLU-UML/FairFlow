
# FairFlow: Mitigating Dataset Biases through Undecided Learning for Natural Language Understanding

#### Authors: 
- [Jiali Cheng](https://chengjiali.github.io/) (jiali_cheng@uml.edu)
- [Hadi Amiri](https://cs.uml.edu/~hadi/) (hadi_amiri@uml.edu)

#### FairFlow Paper: [EMNLP 2024](https://aclanthology.org/2024.emnlp-main.1225/), [Preprint]()


## Overview 

We propose *FairFlow*, a novel debiasing method that mitigates dataset biases (spurious correlations / shortcuts) of Language Models (LMs). It formulates debiasing with *Undecided Learning* -- when facing biased / corrupted examples, a robust LM should remain *undecided about the label*. FairFlow creates biased samples through a series of explicit and implict perturbations and encourages LMs to be predict uniform distribution across classes for biased samples while maintaining the correct label for intact inputs. FairFlow is effective across a wide range of biases (OOD, stress), tasks (NLI, Paraphrase Identification, Relation Classification), architectures (Bert, Roberta, GPT2, DeBerta). 

<p align="center">
    <img src="images/fig1.png" width="1000" align="center">
</p>


## Key idea of Undecided Learning and FairFlow

We observe that when biased LMs make wrong predictions on biased examples, they tend to be over-confident. Therefore, we propose *Undecided Learning*, which encourages LMs to be undecided about the labels of biased inputs.

**Overview of FairFlow.** Built upon this formulation, FairFlow debiases LMs with two steps. _First_, the input samples are corrupted to be biased samples without enough information for a model to determine the label. We design a series of perturbation operations, including explicit and implicit ones. Explicit perturbations directly work on the input text, targetting explicit biases that are easily perceivable by human, such as dropping constituents, shuffling. While implicit perturbations does not directly work on the input text, such as deactivating models, zeroing out representations, targetting implicit biases that are not perceivable by human, unknown, or undefined. _Then_, the LM is encouraged to predict uniform distribution across classes for biased / corrupted inputs, while predict the correct labels for intact inputs, through the proposed Debiasing Contrastive Loss.



## Code

I'm currently working on cleaning the code.


## Citation

If you find *FairFlow* useful for your research, please consider citing this paper:

```
@inproceedings{cheng-amiri-2024-fairflow,
    title = "{F}air{F}low: Mitigating Dataset Biases through Undecided Learning for Natural Language Understanding",
    author = "Cheng, Jiali  and
      Amiri, Hadi",
    editor = "Al-Onaizan, Yaser  and
      Bansal, Mohit  and
      Chen, Yun-Nung",
    booktitle = "Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing",
    month = nov,
    year = "2024",
    address = "Miami, Florida, USA",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.emnlp-main.1225",
    pages = "21960--21975",
}
```
