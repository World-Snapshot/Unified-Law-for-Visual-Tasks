# Unified-Law-for-Visual-Tasks

**"Unified Law for Visual Tasks"**, also known as **"The Four Laws of Computer Vision"**, is a technique that uses the simplest concepts to unify visual tasks. Physically, "encoding all information onto the surface of the world + conformal symmetry" -- flattens the world into a two-dimensional space, and visual generation is almost lossless world generation. 

This theory is equivalent to "predicting the next token will enable the model to understand a book, if it always correctly interprets/answers". However, you need some skills to convert all tasks into generation tasks. Because visuals do not have an easily obtainable answer like in the "Prompt-Answer" structure (The simplest training data structure). 

Next, we will describe to you, using both pictures and words (maybe nano code), why all tasks can be transformed into a generating form:

## Background

*The earliest concept of this part was released in the ["The Discussion: Answer questions from Computer Vision researchers"](https://github.com/orgs/World-Snapshot/discussions/1) section.*

The ordinary generation process goes from noise to RGB, that is, from A to M. However, our generation can be regarded as going from A to MN, where N represents additional information. 

Then our estimation can be regarded as going from M to A in reverse, and then performing the process from A to MN again. Do you understand? In our view, if you want to achieve unified generation comprehension, your generation should be equal to comprehension/estimation, and both tasks should be accomplished simultaneously. 

Then, in a broader sense, we use RGB as a condition to obtain other information. At this time, **the estimation task = condition control**. **The recognition task based on RGB = a special condition task**. So, if we replace RGB with other channels, we get **condition control = generation task based on conditions**. 

To sum up, our answers of derivation process are: 

- **previous Generating = Generate RGB channels from text output**
- **previous Estimation (understand, detect, segment) = Generate additional information from RGB channels**
- **previous Conditional Control = Generate RGB from additional information channels**
- **previous Reconstruction = Generate shape information from RGB channels** (If you do not use the core space, then it is an implicit reconstruction)

Therefore, we can say that **all previous computer vision tasks were special cases of the world snapshot model tasks**. In fact, we should estimate the material from color, estimate the roughness from the material, estimate the 3D human body from the 2D human skeleton, and estimate the rendered result from the Mesh. Any possible 256*256 scenario should be achievable.

Their function is to inform people: 1. How the generated knowledge of the model can be utilized for understanding without re-training/add-dev. 2. How to theoretically unify all 2D visual tasks (Generating, Conditional Control, Estimation) and incorporate them into an interpretable framework. 3. LLM can unify everything into the *Prompt-Answer* format. Then our rules can uniformly transform all CV tasks into a generation form.

You can refer to these formulas as the **"Unified Law for Visual Tasks"** or **"The Four Laws of Computer Vision"**

## Implementation
