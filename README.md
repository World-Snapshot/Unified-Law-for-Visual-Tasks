# Unified-Law-for-Visual-Tasks

**"Unified Law for Visual Tasks"**, also known as **"The Four Laws of Computer Vision"**, is a technique that uses the simplest concepts to unify visual tasks. Physically, ["encoding all information onto the surface of the world + conformal symmetry"](https://link.springer.com/article/10.1023/A:1026654312961) -- flattens the world into a two-dimensional space, and visual generation is almost lossless world generation. 

This theory is equivalent to "predicting the next token will enable the model to understand a book, if it always correctly interprets/answers". However, you need some skills to convert all tasks into generation tasks. Because visuals do not have an easily obtainable answer like in the "Prompt-Answer" structure (The simplest training data structure): *You must come up with a way to fully utilize the encoded information in wsg. If you can't find a method to convert all tasks into a generative form, then you will have to train four kind of models separately using the wsg files.*

Next, we will describe to you, using both pictures and words (maybe nano code), why **all tasks can be transformed into a generating form**:

## Method

*The earliest concept of this part was released in the ["The Discussion: Answer questions from Computer Vision researchers"](https://github.com/orgs/World-Snapshot/discussions/1) section.*

1. **The Premise:** (advantages of the new format): The ordinary generation process goes from noise to RGB, that is, from A to M. However, our generation can be regarded as going from A to MN, where N represents additional information. 
2. **Crucial Observation:** If we consider completing WSG from RGB as an estimation task, and in order to convert the estimation into generation, we should focus on the generation capability. Then, we should think of a way to generate again without changing the RGB.
3. **Prior Knowledge:** The RF model can precisely restore RGB back to noise, but no one has figured out what the use of this is yet. Many people use it for image/video editing, which has contributed to the emergence of more powerful prompt generative models at present.
4. **Deduction:** Then our estimation can be regarded as going from M to A in reverse by RF, and then performing the process from A to MN again. Do you understand? In our view, if you want to achieve unified generation comprehension, your generation should be equal to comprehension/estimation, and both tasks should be accomplished simultaneously (This is an extremely ingenious idea. By reversing the RGB values, we can reveal the associated information without changing the "re-generated RGB"!).
5. **Therefore:** In a broader sense, we use RGB as a condition to obtain other information. At this time, **the estimation task = condition control**. **The recognition task based on RGB = a special condition task**. So, if we replace RGB with other channels, we get **condition control = RGB generation task based on conditions**. 

To sum up, our answers of derivation process are: 

- **previous  Generating = Generate RGB channels from text output**
- **previous  Estimation (understand, detect, segment) = Generate additional information from RGB channels**
- **previous  Conditional Control = Generate RGB from additional information channels**
- **previous  Reconstruction = Generate shape information from RGB channels** (If you do not use the core space, then it is an implicit reconstruction)

Therefore, we can say that **all previous computer vision tasks were special cases of the world snapshot model tasks**. In fact, we should estimate the material from color, estimate the roughness from the material, estimate the 3D human body from the 2D human skeleton, and estimate the rendered result from the Mesh. Any possible 256*256 scenario should be achievable, this will enable Computer Vision to expand countless times compared to before.

Their function is to inform people: 1. How the generated knowledge of the model can be utilized for understanding without re-training/add-dev. 2. How to theoretically unify all 2D visual tasks (Generating, Conditional Control, Estimation) and incorporate them into an interpretable framework. 3. LLM can unify everything into the *Prompt-Answer* format. Then our rules can uniformly transform all CV tasks into a generation form.

> What distinguishes us from the previous bidirectional models is that the previous bidirectional models were generally equivalent to training twice / parameters could not be reused / generation could not fully assist in understand. But for us, any form is generation. The stronger the generation ability is, the stronger the other abilities such as understanding, estimation, condition control, segmentation, and detection tasks will be. -- [Some random thoughts: 2th](https://github.com/orgs/World-Snapshot/discussions/1)

You can refer to these formulas as the **"Unified Law for Visual Tasks"** or **"The Four Laws of Computer Vision"**

## Knowledge related to physics

You can search for ["Physical Holographic Principle"](https://en.wikipedia.org/wiki/Holographic_principle) to obtain: 1. How our World Snapshot Model theory is supported by [physics](https://link.springer.com/article/10.1023/A:1026654312961) (This is the [most frequently cited](https://en.wikipedia.org/wiki/Holographic_principle#AdS/CFT_correspondence) article in the field of high-energy physics). 2. Information about surface area and the [transformation](https://en.wikipedia.org/wiki/Holographic_principle#Limit_on_information_density) of world information.

Overall, energy, matter and information are somehow equivalent. The volume of the universe may not exist. Completeness can be fully represented by a lower-dimensional hologram. Or, the essence of an image is no different from that of a world one dimension higher. They are inherently the same.

## Implementation

Our main proof and implementation are in [WSMs](https://github.com/World-Snapshot/WSMs), and the demonstration is in [ControlWave](https://github.com/World-Snapshot/ControlWave). 

The nano demonstration will be updated later.
