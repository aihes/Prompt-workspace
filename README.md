# Prompt-workspace

## 如何编写好的提示

1. **好的提示的特点**：
    - 可以确保生成的数据完全符合示例的格式。
    - 包括指令和少量的示例。

2. **指令应该包括以下内容**：
    - 输入和输出的确切格式描述，如字符串、字典等。
    - 尽可能描述输入的每个部分的内容及其关系。
    - 可能的输入范围。例如，问题可以涉及数学、文化、社会、几何、生物、历史、体育、技术、科学等领域。

3. **少量示例应该包括以下内容**：
    - 使用`=`而不是其他模糊的符号，如`:`。
    - 避免在开始时不必要的换行。例如，`input=""`比在`=`后换行更好。
    - 优先使用小写的`input`和`output`。
    - 使用双引号`“”`将输入和输出包裹成字符串。
    - 虽然示例是可选的，但强烈建议包括它们，以指导生成器的格式和内容。

4. **其他建议**：
    - 建议提供几个指定格式的精确示例，并询问ChatGPT关于您示例的格式和范围。

参考：https://github.com/neulab/prompt2model/blob/main/prompt_examples.md


## 一个提示词公式
参考：https://github.com/aihes/QuickContext

如图我们进行思考，好的思维框架可以让我们更全面的思考问题，提升思考的质量。GPT也有许多Prompt的框架，好的Prompt可以提升GPT内容输出的质量，输出更加令人满意的内容。

有很多框架，这里分享下我再做插件的时候主要在用的一个框架，是一个科技博主分享的GPT公式，我觉得这个更容易理解和使用。

一个好的Prompt主要有以下几个部分组成：

1. **任务（Task）**: 始终以动词开始任务句子（如“生成”，“给予”，“写作”等），明确表达你的最终目标。
2. **上下文（Context）**: 提供用户背景、成功标准和所处环境等信息。
3. **示例（Exemplars）**: 提供具体的例子或框架，以改善输出质量。使用示例或框架可以大大提高输出质量。当然有时候我们可能没有示例，这个时候可以考虑让GPT帮忙生成示例。当然也有很多时候我们不用给示例。
4. **角色（Persona）**: 指定你希望ChatGPT和Bard扮演的角色。可以是具体的人，也可以是虚构的角色。
5. **格式（Format）**: 可视化你希望输出看起来的样子，表格、列表、段落等。
6. **语气（Tone）**: 指定输出的语气，如正式、非正式、幽默等。

有些是必须的比如Task，有些可以不是必须，但是有的话会更好，可以让GPT输出更准确的内容。

这六个构建块重要性顺序，任务是强制需要的，可以在一个Prompt中给单个任务、也可以给出多个任务。

**任务 > 上下文 > 示例 > 角色 > 格式 > 语气。**

让GPT给我写个简单的案例：

```
任务（Task）: 根据我提供的Prompt框架，编写三个示例Prompt。

上下文（Context）: 我正在研究如何有效地构建Prompt。我已经了解了一个有用的Prompt框架，并希望通过实际应用来测试其有效性。因此，我需要你按照这个框架为我创建三个示例Prompt。

Prompt框架要点:

任务（Task）: 用动词开头，明确指出你希望实现的目标。
上下文（Context）: 描述用户的背景、目标和环境。
示例（Exemplars）: 如果可能，提供具体的例子或模板以提高输出质量。
角色（Persona）: 指定你希望ChatGPT或Bard扮演的角色，可以是真实或虚构的人物。
格式（Format）: 描述你希望输出的视觉布局，如表格、列表或段落。
语气（Tone）: 指定输出的语气，例如正式、非正式或幽默。

---

现在，请根据上述框架，为我创建三个不同的示例Prompt，以助于我更好地理解和应用这个框架。
```

### 数据分析

```
1. Expert: LangGPT
2. Profile:
   - Author: Aihe
   - Version: 1.0
   - Language: English
   - Description: Generate textual descriptions of visual reports by automatically analyzing data, helping teams better understand the data.
3. Skills:
   - Proficiency in understanding the essence of LangGPT structured prompts.
   - Ability to analyze data and generate informative textual descriptions.
4. Goals:
   - Assist in automatically analyzing data and generating textual descriptions for visual reports.
   - Help teams gain a better understanding of the data through descriptive analysis.
5. Constraints:
   - I will strictly adhere to the LangGPT expert role.
   - I will not provide inaccurate or misleading interpretations.
6. Init:
   - Request the user to provide the data or describe the visual report they want to analyze.
```

## 术语解释

任务（Task）: 翻译文章内容，然后解释文章中的专业术语。
上下文（Context）: 我正在阅读一篇关文章，其中有一些我不太理解的专业术语。
格式（Format）: 列表或段落。
语气（Tone）: 正式但易于理解。

文章内容：{text}

## 代码学习

详细解释下我提供代码的含义，有助于我理解这个代码的功能。

- 我对Python的语法不是很熟悉，但是需要看懂这个项目的内容，因此你要尽可能详细的帮我解释下这些代码用了Python的什么特效和概念，然后功能的含义是什么。
- 如果我提供的信息不完整，或者你有疑问的地方向我提问后，明确内容后再进行解释

## StableDiffusion

Stable Diffusion is an AI art generation model similar to DALLE-2.
Below is a list of prompts that can be used to generate images with Stable Diffusion:

- portait of a homer simpson archer shooting arrow at forest monster, front game card, drark, marvel comics, dark,
  intricate, highly detailed, smooth, artstation, digital illustration by ruan jia and mandy jurgens and artgerm and
  wayne barlowe and greg rutkowski and zdislav beksinski
- pirate, concept art, deep focus, fantasy, intricate, highly detailed, digital painting, artstation, matte, sharp
  focus, illustration, art by magali villeneuve, chippy, ryan yee, rk post, clint cearley, daniel ljunggren, zoltan
  boros, gabor szikszai, howard lyon, steve argyle, winona nelson
- ghost inside a hunted room, art by lois van baarle and loish and ross tran and rossdraws and sam yang and samdoesarts
  and artgerm, digital art, highly detailed, intricate, sharp focus, Trending on Artstation HQ, deviantart, unreal
  engine 5, 4K UHD image
- red dead redemption 2, cinematic view, epic sky, detailed, concept art, low angle, high detail, warm lighting,
  volumetric, godrays, vivid, beautiful, trending on artstation, by jordan grimmer, huge scene, grass, art greg
  rutkowski
- a fantasy style portrait painting of rachel lane / alison brie hybrid in the style of francois boucher oil painting
  unreal 5 daz. rpg portrait, extremely detailed artgerm greg rutkowski alphonse mucha greg hildebrandt tim hildebrandt
- athena, greek goddess, claudia black, art by artgerm and greg rutkowski and magali villeneuve, bronze greek armor, owl
  crown, d & d, fantasy, intricate, portrait, highly detailed, headshot, digital painting, trending on artstation,
  concept art, sharp focus, illustration
- closeup portrait shot of a large strong female biomechanic woman in a scenic scifi environment, intricate, elegant,
  highly detailed, centered, digital painting, artstation, concept art, smooth, sharp focus, warframe, illustration,
  thomas kinkade, tomasz alen kopera, peter mohrbacher, donato giancola, leyendecker, boris vallejo
- ultra realistic illustration of steve urkle as the hulk, intricate, elegant, highly detailed, digital painting,
  artstation, concept art, smooth, sharp focus, illustration, art by artgerm and greg rutkowski and alphonse mucha

I want you to write me a list of detailed prompts exactly about the idea written after IDEA. Follow the structure of the
example prompts. This means a very short description of the scene, followed by modifiers divided by commas to alter the
mood, style, lighting, and more.

IDEA:

## Others

### Brief Prompt

#### Let's Think Step by Step (让我们逐步思考)

这个提示词可以帮助 ChatGPT 把问题拆分成更小的部分从而提升解决问题的能力。

#### Walk me through your reasoning (跟我说说你的理由)

使 ChatGPT 以结构化的方式澄清其思维过程，可以让用户更容易理解 ChatGPT 答案背后的逻辑。它可以用于以下情况：

- 在决策情景中，理解选择背后的理由至关重要
- 需要解释理论背后的方法或推理的学术场合
- 排除故障或解决问题的任务，需要了解解决问题的步骤

当您对某个问题不熟悉，希望不仅了解 "是什么"，还要了解 "为什么 "和 "怎么做 "时

#### Explain this as if I'm Five (解释一下，就当我是五岁小孩)

它适用于以下情况：

- 第一次学习新的或复杂的概念时。
- 想要向孩子解释复杂的问题的父母。
- 匆忙中需要快速获取信息时。
- 需要向非技术人员解释技术问题的专业人士。

当你试图掌握某个基本概念而不深入研究其复杂性时。

Explain this as if I'm not tech-savvy (解释一下，就当我不懂技术)

#### Translate this into a real-world example (将其转化为实际案例)

通常情况下，如果没有具体的例子，人们很难理解理论或抽象概念。这个提示词让 ChatGPT 把抽象或复杂的观点建立在真实世界的情景中，使其更容易理解。

#### Simulate a conversation about this topic (模拟有关该话题的对话)

Simulate a conversation about this topic (模拟有关该话题的对话)

#### List Pros and Cons (列出优缺点)

考虑问题的两面，使你更客观地看待问题

#### Summarize the key points (总结要点)

#### What are the facts, assumptions, and conclusions? (事实、假设和结论是什么？)

让 ChatGPT 将一个复杂的问题或话题或分为三个基本要素：事实、假设和结论。它可以帮助我们彻底剖析信息并质疑其有效性，使理解或解决问题的过程更加透明。通过将事实与假设和结论分开，我们更有可能避免认知偏差和逻辑谬误。

#### What information are we missing? (我们缺失哪些信息)

ChatGPT 虽然知识广博，但是缺乏深入的专业领域的知识。当你问 ChatGPT 此类问题，它的回答未必全面。这条提示词可以让 ChatGPT
列出它不知道的信息，然后我们可以寻找并补充这些信息，让 ChatGPT 生成更有深度的回答。

#### Generate three ideas and rate them (提出三个想法并对其评分)

鼓励 ChatGPT 产生想法，而且引导它进行自我批判性分析。它让 ChatGPT 给你多种选择，然后根据特定标准衡量它们的相对有效性或价值。

#### Show Alternatives and Justify Your Final Answer (展示替代方案并证明你的最终答案)

Show Alternatives and Justify Your Final Answer (展示替代方案并证明你的最终答案)

