# COMS6998_FinalProject

#Noisy Transformers File: 

We first implement a GPT2-like language model to generate text. The training data looks like (y0, y1, y2) -> (y1, y2, y3) and we have 3 loss terms. The model will be trained on chunks of data from Hemingway's most well-known novel. The default setting below will produce a model with about 700K parameters. The model should be expected to work better and better as we make the sizes of the parameters (starting with d_model below) bigger and bigger. Collab should allow us to scale to a 10M parameter model without making us to pay.

At the end, after training, you'll decode with this model and generate text. Although there are specialized metric for this task (e.g. perplexity), we will simplify the comparisons by just considering training and validation accuracies.

The goal of this notebook is to incorporate from various angles noise structures that hypothetically would promise something interesting or surprising.


#Interpretability Modify Transformer File: 
Summary of this notebook:

Modifying transformers in a way that can be easily interpreted

1. In `Cache & Visualize Activations`, we tried using packages tailored  for transformers to visualize activations across layers of a trained model.

2. In `Use Hooks to Change Activations in a Layer`, we explored using Hooks  to modify a baseline transformer. This way, we can do ablation study not  just on the old & new models' global performance; we also can compare how  a single attention head of the old & new models matters to the end result. 

3. In `Activation Patching on the Indirect Object Identification Task`, we explored  a concrete task where we can visualize the effect of altering the model.  

4. In `Use Checkpoints to Detect Phase Transition in Training`, we explored inserting checkpoints in the training process, borrowed a new metric called induction loss,  and observed the training process to "suddenly perform much better" in the beginning  on the training process --- a phenomenon coined by the term phase transition. We can  extend this toy experiment by comparing the training trajectories of the old & new models. 
