The goal of this repo is to make a tiny but smart chain-of-thought model that is trained using RL. We will start with the phi-1 model. The training proceeds in two steps.

![Chain of thoug](sources/CoT.png)

1) Make a system prompt for the model to do basic CoT. The CoT should be modular, each module does the following two steps. Verify the idea from the previous module, and in the second step return the final answer, give a new idea, or build on a previous idea.

2) Take ~5k samples of competitive programming tasks. Let the model (from the first step) solve them. Then run the output code on some testset and punish the model if the code is not correct. If the output is correct, we reward the model. We should probably introduce a [KL-term](https://arxiv.org/pdf/2009.01325) to make sure the model retains the CoT structure, but maybe this is not even needed. We will start with simple tasks and only increase difficulty if the model solved ~90% of the previous difficulty level. We can feed in a problem multiple times, which is why we probably don't need that much training data. We should also incorporate the output length into the loss function to avoid solutions that are too long.
