# Visual Dialog

*Abhishek Das, Satwik Kottur, Khushi Gupta, Avi Singh, Deshraj Yadav, José M. F. Moura, Devi Parikh, Dhruv Batra.* **CVPR 2017**

## Summary

The paper introduces the task of Visual Dialog, which requires an AI agent to hold a meaningful dialog with humans in natural, conversational language about a visual content. This can be considered as the visual analogue of the Turing Test.

- Given an image, a dialog history, and a question about the image, the AI agent has to ground the question in image, infer context from history, and answer the question accurately.
- The model consists of an encoder that creates an encoding using the image, the dialog history and the question, followed by a decoder that uses the encoding to come up with the best possible answer.
- 3 types of encoders are given in the paper: Late Fusion (LF) Encoder, Hierarchical Recurrent Encoder (HRE) and Memory Network (MN) Encoder. There are 2 types of decoder: Generative and Discriminative. Generative decoders are more practical in the real world but tend to have lower accuracy than their discriminative counterparts.
- For each question there are 100 possible answers given. 100 = Ground Truth Answer + Answers to 50 Similar Question + 30 Most Popular Answers in the Dataset + Answers to Random Questions in the Dataset.
- The paper proposes a retrieval-based evaluation protocol for Visual Dialog where the AI agent is asked to sort a list of candidate answers and evaluated on metrics such as mean reciprocal-rank of the human response.

## Strengths

- Visual Dialog can be considered as an advancement of the VQA task.
- Performance on the visual dialog task can be considered as a good measure of an agents ability to semantically reason the visual world.

## Weaknesses / Notes

- The proposed methods do not work well with longer conversational exchanges.