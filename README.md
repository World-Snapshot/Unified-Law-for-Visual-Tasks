# Unified-Law-for-Visual-Tasks

**"Unified Law for Visual Tasks"**, also known as **"The Four Laws of Computer Vision"**, is a technique that uses the simplest concepts to unify visual tasks. Physically, ["encoding all information onto the surface of the world + conformal symmetry"](https://link.springer.com/article/10.1023/A:1026654312961) -- flattens the world into a two-dimensional space, and visual generation is almost lossless world generation<sup title="This is the methodology and motivation of our world snapshot model">1</sup>.

This theory is equivalent to "predicting the next token will enable the model to understand a book, if it always correctly interprets/answers". However, you need some skills to convert all tasks into generation tasks. Because visuals do not have an easily obtainable answer like in the "Prompt-Answer" structure (The simplest training data structure): *You must come up with a way to fully utilize the encoded information in wsg. If you can't find a method to convert all tasks into a generative form, then you will have to train four kind of models separately using the wsg files.*

Next, we will describe to you, using both pictures and words (maybe nano code), why **all tasks can be transformed into a generating form**<sup title="This is the motivation for proposing these laws">2</sup>:

## Method

*The earliest concept of this part was released in the ["The Discussion: Answer questions from Computer Vision researchers"](https://github.com/orgs/World-Snapshot/discussions/1) section.*

1. **The Premise:** (advantages of the new format): The ordinary generation process goes from noise to RGB, that is, from A to M. However, our generation can be regarded as going from A to MN, where N represents additional information. 
2. **Crucial Observation:** If we consider completing WSG from RGB as an estimation task, and in order to convert the estimation into generation, we should focus on the generation capability. Then, we should think of a way to generate again without changing the RGB.
3. **Prior Knowledge:** The RF model can precisely restore RGB back to noise, but no one has figured out what the use of this is yet. Many people use it for image/video editing, which has contributed to the emergence of more powerful prompt generative models at present.
4. **Deduction:** Then our estimation can be regarded as going from M to A in reverse by RF, and then performing the process from A to MN again. Do you understand? In our view, if you want to achieve unified generation comprehension, your generation should be equal to comprehension/estimation, and both tasks should be accomplished simultaneously (This is an extremely ingenious idea. By reversing the RGB values, we can reveal the associated information without changing the "re-generated RGB"!).
5. **Therefore:** In a broader sense, we use RGB as a condition to obtain other information. At this time, **the estimation task = condition control**. **The recognition task based on RGB = a special condition task**. So, if we replace RGB with other channels, we get **condition control = RGB generation task based on conditions**. 

To sum up, our answers of derivation process are: 

- **(Lex. I.) previous  Generating = Generate RGB channels from Text output**
- **(Lex. II.) previous  Estimation (understand, detect, segment) = Generate Additional Information from RGB channels**
- **(Lex. III.) previous  Conditional Control = Generate RGB from Additional Information channels**
- **(Lex. IV.) previous  Reconstruction = Generate Organized Shape Information from RGB channels** (If you do not use the core space, then it is not an [RIVE](https://world-snapshot.github.io/doc/index.html?page=S5_blogs/00_world_model.md#definition) reconstruction)

<details>
<summary>Another expression of the Unified Law</summary>

- **(Lex. I.) previous Generating: A generation process that From Text to RGB**
- **(Lex. II.) previous Estimation (understand, detect, segment): A generation process that From RGB to Additional Information**
- **(Lex. III.) previous Condition control: A generation process that From Additional Information to RGB**
- **(Lex. IV.) previous Reconstruction: A generation process that From RGB to Organized Shape Information**

All the visual tasks are actually generating tasks.

</details>

Therefore, we can say that **all previous computer vision tasks were special cases of the world snapshot model tasks**. In fact, we should estimate the material from color, estimate the roughness from the material, estimate the 3D human body from the 2D human skeleton, and estimate the rendered result from the Mesh. Any possible 256*256 scenario should be achievable, this will enable Computer Vision to expand countless times compared to before.

Their function is to inform people: 1. How the generated knowledge of the model can be utilized for understanding without re-training/add-dev. 2. How to theoretically unify all 2D visual tasks (Generating, Conditional Control, Estimation) and incorporate them into an interpretable framework. 3. LLM can unify everything into the *Prompt-Answer* format. Then our rules can uniformly transform all CV tasks into a generation form.

> What distinguishes us from the previous bidirectional models is that the previous bidirectional models were generally equivalent to training twice / parameters could not be reused / generation could not fully assist in understand. But for us, any form is generation. The stronger the generation ability is, the stronger the other abilities such as understanding, estimation, condition control, segmentation, and detection tasks will be. -- [Some random thoughts: 2th](https://github.com/orgs/World-Snapshot/discussions/1)

You can refer to these formulas as the **"Unified Law for Visual Tasks"** or **"The Four Laws of Computer Vision"**

## Knowledge related to physics

You can search for ["Physical Holographic Principle"](https://en.wikipedia.org/wiki/Holographic_principle) to obtain: 1. How our World Snapshot Model theory is supported by [physics](https://link.springer.com/article/10.1023/A:1026654312961) (This is the [most frequently cited](https://en.wikipedia.org/wiki/Holographic_principle#AdS/CFT_correspondence) article in the field of high-energy physics). 2. Information about surface area and the [transformation](https://en.wikipedia.org/wiki/Holographic_principle#Limit_on_information_density) of world information.

Overall, Physical scientists believe energy, matter and information are somehow equivalent. The volume of the universe may not exist. The complete universe can be fully represented by a lower-dimensional hologram. Or, the essence of the world is no different from that of the image one dimension lower. They are inherently the same.

## Discussion

- During our development process, we gradually realized that the transition from visual information to textual information is a process from low-level abstract information to high-level abstract information. Just like how MSE gradually transforms into CE Loss. 
- In practical visual applications, the mutual conversion between low-dimensional, low-channel, and highly abstract latent representations (SD VAE) is more appropriately carried out in a predictive manner (the results of the text also confirm this); while high-dimensional, high-channel, and low-abstraction latent representations (Flux VAE, RAE) are more suitable for mutual conversion and translation in the form of conditional image generation and masking. 
- Therefore, the visual and textual elements are theoretically unified. This falls under the extension of our visual unified laws: For instance, if you decide to use more low-level abstract variables as your target for generation, this to some extent shifts the pressure of VAE onto the generation process. Considering that the generation model is quite powerful, it is generally beneficial. Suppose we consider visual information as high-channel and high-abstraction things, it is like tokens that need to be trained with the CE Loss. At this time, perhaps the more abstract, the better, provided that there is sufficient data. VAE is equivalent to a tokenizer.
- Based on our experience, there is no explicit connection path available between data of different levels of abstraction. This is another essential difference between visual and textual forms, and even the reason for the differences in each modality. I call this the principle of modal incompatibility.

## Implementation

Our main proof and implementation are in [WSMs](https://github.com/World-Snapshot/WSMs), and the demonstration is in [ControlWorld](https://github.com/World-Snapshot/ControlWorld). 

The nano demonstration will be updated later.
