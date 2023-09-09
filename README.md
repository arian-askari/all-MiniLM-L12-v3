# Injecing BM25/DPR score into all-MiniLM-L12-v2 improves its effectiveness! (A New version of MiniLM re-ranker)

## Motivation
Over 700,000 downloads of the all-MiniLM-L12-v2 in the last month, particularly in the era of Large Language Models, shows that the demand for this model is very real, and it's what drove me to create something even more powerful. Building on our paper, "Enhancing BERT-Based Re-Rankers with BM25," We thought, "Why not put this idea to good use?"

## Objective
The mission is simple: to contribute to the community by offering a more effective MiniLM re-ranker. We hope that this upgrade will benefit you in practical ways, making it easier to achieve outstanding results. 

## Pre-trained models
To address diverse needs and scenarios, we have trained four different variations of the minilm model:

1. **minilm-v2.1-bm25added**: This model is designed for users who want to effortlessly upgrade to a more effective minilm without any modifications. In this variation, we've incorporated BM25 scores into the loss function, similar to knowledge distillation proposed by  Hofstätter et al. While it is less challenging to implement than options 2-4, it still outperforms minilm-v2 in terms of effectiveness. Please refer to the table at the end of this post for a detailed comparison.

2. **minilm-v3-bm25**: If you have access to BM25 scores for both the query and candidate documents, this model allows you to seamlessly inject these scores into the input. This approach is particularly beneficial when working with cases that rely on both BM25 and DPR, as BM25 alone can yield a more effective model. However, combining BM25 and DPR scores, as in option 4, can offer the highest level of effectiveness.

3. **minilm-v3-dpr**: For users with access to DPR scores for the query and candidate documents, this model facilitates the straightforward injection of DPR scores into the input. While this option is less challenging to implement and computationally more affordable, it offers the second-best level of effectiveness.

4. **minilm-v3-bm25dpr**: The most powerful option, this model is designed for users who have access to both DPR and BM25 scores and can inject both into the input. This approach delivers the highest level of effectiveness and is especially valuable for pipelines already utilizing BM25 and DPR in their initial stage setup.

## Evaluation

For the evaluation of these model variations, we employed the following setup: reranking on top of top-1000 retreieved documents by BM25. However, it's worth noting that option 4 could benefit from a more precise setup where the initial ranking involves the top 1000 candidates ranked by an ensemble of BM25 and DPR scores. If you choose this option in the future, please feel free to request a pull merge.

## Results table

(Note: BM25 scores are normalized as explained in our paper.)

Comming soon


## Conclusion

We are excited to introduce these enhanced minilm models, which offer a spectrum of options for users with varying needs and access to different score types. Whether you seek a straightforward upgrade or the utmost effectiveness through score injection, our minilm-v3 models are here to empower your natural language processing tasks. We invite you to explore these models and select the one that best suits your requirements.
