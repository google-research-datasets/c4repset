# c4repset: Representative Subset from C4 data for Training Pre-trained LMs

## TL;DR
This dataset is a subset of [C4 data in TFDS](https://www.tensorflow.org/datasets/catalog/c4) that we can possibly train language models effectively with a small data size.

The details of how to obtain the subset is described in our paper [Extracting Representative Subset from Extensive Text Data  for Training Pre-trained Language Models, Information Processing & Management (Accepted Dec 17, 2022, To appear: This link is currently to the journal homepage, not to the paper)](https://www.sciencedirect.com/journal/information-processing-and-management).

## Reason of providing this dataset
Neural language models, which have been rapidly developed recently, are an essential technology that plays a fundamental role in the success of natural language processing (NLP) field.
Many studies have published so far, and have clarified that incorporating neural language models as pre-trained models into target task-specific models can dramatically improve the performance compared to the case without incorporating pre-trained (neural) language models (PreLMs).
In other words, we show that PreLMs learned from large-scale text dataset can effectively serve as universal features for a wide variety of NLP tasks.

For PreLMs, several recent studies have verified and experimentally proven that the amount of training data and increasing the model size are the two major factors that can stably improve the performance, e.g., [[1]](https://aclanthology.org/N18-1202)[[2]](https://aclanthology.org/N19-1423)[[3]](http://jmlr.org/papers/v21/20-074.html)[[4]](https://aclanthology.org/2020.acl-main.703)[[5]](https://proceedings.neurips.cc/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html).
However, it is also well-known that the efficiency of the performance improvement is often approximately log-linear with respect to the amount of dataset and model size [[6]](https://arxiv.org/abs/2001.08361)[[7]](https://arxiv.org/abs/2010.14701).
In other words, if we want to achieve the same level of performance improvement as that obtained by increasing the amount of data from a certain amount of data, we need to increase the amount of data by a factor of 100.
This fact implies that a huge amount of training data is required to build a PreLM with higher performance.
Therefore, the computational resources required for training may become infeasible.
In fact, most of the PreLMs trained from large-scale dataset are released by large companies with ample computational resources, and it is very difficult for research organizations without much computational resources or research funds, such as many university laboratories, to build relatively high-performance PreLMs.

However, this situation may allow the research on new developments of PreLMs only in certain research institutions.
It is an inappropriate situation for open research if researchers cannot widely participate in the research of such an important fundamental research topic like PreLMs.
Therefore, we focus on the training data of PreLMs, and explore a subset that can train a language model with equal or better performance from the data used for training a large-scale PTNLM.
We refer to the representative subset from the original full training dataset as the "representative dataset" or "RepSet" for short.
If it is possible to extract a representative subset, it will be possible to conduct research on PreLMs with less realistic computational resources and research budgets, and it is expected that more researchers will participate and the field will develop more quickly.


## How to use

We provide a list of URLs extracted from C4 data.
A naive and straightfoward way to use this dataset is to download URL list and extract these dataset from original CommonCrawl dataset defined in C4.
Or, you can use the URL list via a small modification of TFDS.

