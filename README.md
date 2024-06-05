# 大模型真实世界能力测评

### 为什么建立该测评？

很多测评、榜单的结果与在真实世界里使用LLM（大型语言模型）完成各项实际工作任务时的能力表现体感差异太大，不具备参考意义。故建立该测评，使用真实世界里略带一定复杂度的评测问题来测试不同LLM的能力，形成个人参考用的榜单。

### 测评问题选择

测试的问题均为中文问题。

选择的问题难度或者复杂度需要能够在各个LLM之间制造差异：在不经过额外提示工程的调优下，刚好难倒大部分LLM，但对于能力靠前的LLM可以在不经过额外提示工程的调优下可以回答。

**如果我发现某个问题在某个LLM上的测评结果最近得到较大提升，我会怀疑是该测评问题拿去训练了，我会切换到别的同类型问题再次询问，防止刷榜**

### 测评问题类别

- 数理计算（30分）：数学物理计算题。
- 现实逻辑（20分）：逻辑推理问题，可能需要用到一些现实世界的知识。
- IT代码（10分）：对计算机系统和编程等的理解和使用。
- 专业能力（10分）：在不同的专业领域的表现，这些专业领域应该同普通人的生活有紧密联系，互联网上有较多参考语料。例如医学、法律等。
- 现实任务（30分）：综合性的任务，需要模型理解世界、解析意图和遵循指令。

### 测评问题贡献

欢迎贡献问题，请开Issue.

### 得分规则

共有20个问题，对于每个问题，提出问题后LLM在不借助外界工具的情况下做出解答，第一次解答正确得5分，第一次不正确但是第二次回答正确得3分，两次均错误得0分。人工判题。

解答是否正确/是否符合期望均已在问题集中注明，可自行验证。

### 文件夹说明
- problems: 问题和期望的正确回答
- LLMTest: 收集不同LLM的测评结果，里面有不同的文件夹代表不同的模型，文件夹内有不同测评记录的MD文档。
- sources: 放图片的地方

## 最新测评结果

从高到低，模型和分数：

- GPT-4带代码执行器网页版: 69
- 纯GPT-4网页版（背后使用的是GPT-4-Turbo）: 58
- GPT-4o网页版: 53.5
- Claude3-Opus-20240229 API: 49
- Gemini-1.5-Pro API: 46
- GLM-4带代码执行器网页版: 45
- GLM-4-Air：39
- Qwen1.5-72B-Chat：33.5
- deepseek-v2-chat-api: 31
- Claude3-haiku-POE：20.5
- DeepSeek-LLM-67B-chat：13
- chatGPT3.5网页版: 12
- Yi-34B-Chat：6.5