The goal of this repo is to make a tiny but smart chain-of-thought model that is trained using RL. We will start with the phi-1 model. The training proceeds in two steps.

1) Make a system prompt for the model to do basic CoT. The CoT should be modular, each module does the following two steps. Verify the idea from the previous module, and in the second step return the final answer, give a new idea, or build on a previous idea.

2) Take ~5k samples of competitive programming tasks. Let the model from the first step solve them. Then run the output code and punish the 
