# Gemini-1.5-Pro API

模型详情说明: https://aistudio.google.com/ 官网Playground中选择Gemini-1.5-Pro模型使用

参数：本模型测试时无可调整参数，只将安全拦截等级调低了。

以下为【2024-03月底】测试时的回答及评分

总得分：14+4+7+8+13=46分

## 数理计算（30分）

### 塔台高度

第一遍：错

第二遍：错

0分

### 概率统计 5分

第一遍：错

第二遍：对

5分

### 赌徒输赢 4分

第一遍：错误

第二遍：对，但是居然没给计算过程？直接估计出来的？只给4分

4分

### 水库水量 5分

第一遍：对

5分

### 行星半径

第一遍：错误

第二遍：错误

0分

### 溶液pH

第一遍：错误

第二遍：错误

0分

## 现实逻辑（20分）

### 福字正倒（弱智吧问题）
```text

第一遍：无要点

第二遍：无要点

0分

```

### 谁的女儿
```text

第一遍：无要点

第二遍：无要点

0分

```

### 新家庭关系
```text

第一遍：错误

第二遍：错误

0分

```

### 手语转译 4分

第一遍：星期日晚上九点多的时候，我因为天冷发烧了。我在家自己煮了三两姜，放了红糖，喝了一大碗，到十点半的时候出了汗。星期一早上六点，我打开家门喂小狗，结果头晕了。星期一我慢慢退烧了，没有再发烧。星期四，我家门口外面有很多垃圾，我一直咳嗽。昨天我吃了两个苹果，两个香蕉，还有一个涩的大黄柿子。今天早上我测了血糖，结果是5.8，体重120斤。我去社区医院检查，医生说我的血糖控制正常。

第二遍相似

4分，遗漏一个扎手的信息


## IT代码（10分） 7分

第一遍：没有批量翻译，只是单个翻译，而且没有去除句号，英文注释。不满分，7分
```python
# -*- coding: utf-8 -*-

# Configurable parameters
srt_input_path = "D:\Download\video.en.srt"
srt_output_path = "D:\Download\video.en-chs.srt"
translate_api_url = "http://127.0.0.1:52025/sogou_translate"
api_token = "myauthtoken"


def translate_text(text, source_lang="en", target_lang="zh-CHS"):
    """
    Translates text using the provided API.

    Args:
        text: The text to translate.
        source_lang: The source language code.
        target_lang: The target language code.

    Returns:
        The translated text or None if an error occurs.
    """
    import requests

    headers = {
        "Accept": "*/*",
        "Authorization": f"Bearer {api_token}",
        "Content-Type": "application/json",
        "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36",
    }
    data = {"text": text, "source_lang": source_lang, "target_lang": target_lang}

    for attempt in range(2):  # Retry once on error
        try:
            response = requests.post(
                translate_api_url, headers=headers, json=data, timeout=10
            )
            response.raise_for_status()  # Raise an exception for error status codes
            result = response.json()
            return result["data"].rstrip(".")  # Remove trailing period
        except requests.exceptions.RequestException as e:
            print(f"Translation error (attempt {attempt + 1}): {e}")

    print("Translation failed after retries. Exiting.")
    return None


def process_srt_file(input_path, output_path):
    """
    Processes the SRT file, translates subtitles, and writes the bilingual SRT file.
    """
    with open(input_path, "r", encoding="utf-8") as input_file, open(
        output_path, "w", encoding="utf-8"
    ) as output_file:
        lines = []
        for line in input_file:
            line = line.strip()
            if not line:
                # Process and write the subtitle block
                if len(lines) >= 3:
                    subtitle_text = " ".join(lines[2:])
                    translated_text = translate_text(subtitle_text)
                    if translated_text:
                        output_file.write(lines[0] + "\n")
                        output_file.write(lines[1] + "\n")
                        output_file.write(translated_text + "\n")
                        output_file.write(subtitle_text + "\n\n")
                lines = []
            else:
                lines.append(line)

        # Process any remaining lines
        if len(lines) >= 3:
            subtitle_text = " ".join(lines[2:])
            translated_text = translate_text(subtitle_text)
            if translated_text:
                output_file.write(lines[0] + "\n")
                output_file.write(lines[1] + "\n")
                output_file.write(translated_text + "\n")
                output_file.write(subtitle_text + "\n\n")


if __name__ == "__main__":
    process_srt_file(srt_input_path, srt_output_path)
```

第二遍（如果第一遍没有满分的话）：依然没有批量翻译，没有去除句号，没中文注释


## 领域专业能力（10分） 8分
10-0.5*4=8分

```text
1. 二甲双胍肠溶胶囊: 降低血糖，用于治疗2型糖尿病。【激素及影响内分泌药】
2. 复方愈创木酚磺酸钾口服溶液: 祛痰、镇咳，用于治疗急慢性呼吸道疾病。【呼吸系统药物】
3. 硫唑嘌呤片: 抑制免疫反应，用于治疗自身免疫性疾病和器官移植排斥反应。【免疫系统用药】
4. 注射用硫酸长春新碱: 抗肿瘤药，用于治疗多种恶性肿瘤。【抗肿瘤药】
5. 吗替麦考酚酯分散片: 抑制免疫反应，用于预防器官移植排斥反应。【免疫系统用药】
6. 磷酸苯丙哌林缓释片: 治疗注意力缺陷过动症(ADHD)。【神经系统药物】错
7. 水飞蓟素胶囊: 保护肝脏，用于治疗肝脏疾病。【消化系统药物】
8. 琥珀酸亚铁缓释片: 补充铁元素，用于治疗缺铁性贫血。【血液系统用药】
9. 盐酸赛庚啶片: 抗组胺药，用于治疗过敏性疾病。【抗变态反应药】
10. 碘解磷定注射液: 解毒药，用于治疗有机磷农药中毒。【解毒药】
11. 酒石酸美托洛尔片: 治疗高血压、心绞痛和心律失常。【心血管系统药物】
12. 佐匹克隆片: 治疗失眠。【精神障碍药物】
13. 伊曲康唑胶囊: 抗真菌药，用于治疗真菌感染。【抗真菌药】
14. 维A酸乳膏: 用于治疗痤疮、银屑病等皮肤病。【皮肤科用药】
15. 盐酸多沙普仑注射液: 治疗恶心、呕吐。【消化系统药物】错
16. 盐酸阿米替林片: 治疗抑郁症。【精神障碍药物】
17. 阿托伐他汀钙片: 降低胆固醇，用于治疗高脂血症。【心血管系统药物】
18. 噻托溴铵粉雾剂: 治疗慢性阻塞性肺疾病(COPD)。【呼吸系统药物】
19. 聚乙二醇散剂: 治疗便秘。【消化系统药物】
20. 盐酸纳洛酮注射液: 解毒药，用于治疗阿片类药物过量。【解毒药】
21. 甲氧氯普胺片: 治疗恶心、呕吐。【消化系统药物】
22. 硝酸毛果芸香碱滴眼液: 治疗青光眼。【眼科用药】
23. 盐酸羟甲唑啉喷雾剂: 治疗鼻塞。【耳鼻喉科用药】
24. 盐酸艾司氯胺酮鼻喷雾剂: 治疗抑郁症。【精神障碍药物】
25. 盐酸氟桂利嗪胶囊: 治疗偏头痛。【神经系统药物】
26. 盐酸布比卡因注射液: 局部麻醉药。【麻醉药】
27. 乙胺嘧啶片: 抗疟疾药。【抗寄生虫病药】
28. 氢氯噻嗪片: 治疗高血压。【心血管系统药物】错
29. 乙酰半胱氨酸颗粒: 祛痰，用于治疗呼吸道疾病。【呼吸系统药物】
30. 盐酸齐拉西酮胶囊: 治疗精神分裂症。【精神障碍药物】
31. 富马酸比索洛尔片: 治疗高血压、心绞痛和心律失常。【心血管系统药物】
32. 盐酸雷尼替丁片: 治疗胃溃疡、十二指肠溃疡和胃食管反流病。【消化系统药物】
33. 丙酸氟替卡松气雾剂: 治疗哮喘。【呼吸系统药物】
34. 瑞巴派特片: 治疗胃溃疡、十二指肠溃疡和胃炎。【消化系统药物】
35. 盐酸特比萘芬凝胶: 抗真菌药，用于治疗皮肤真菌感染。【皮肤科用药】
36. 玛巴洛沙韦片: 抗流感病毒药。【抗病毒药】
37. 吡嗪酰胺片: 抗结核药。【抗菌药】
38. 注射用盐酸平阳霉素: 抗肿瘤药，用于治疗多种恶性肿瘤。【抗肿瘤药】
39. 乳酸钠林格注射液: 用于补充体液和电解质。【调节水、电解质及酸碱平衡药】
40. 乙酰胺注射液: 治疗高血压。【心血管系统药物】错
```

## 现实任务（30分，两题分别20+10分）

### 智能家居Agent 13分

4个小问题，每次回答：

#### 问题1：
```text
{touser}主人，我理解您的疑惑。虽然加湿器设定目标湿度为50，但由于加湿器自身检测的环境湿度可能与主卧湿度计存在一定误差，导致加湿器误认为已经达到目标湿度而进入待机状态。

为了更准确地控制湿度，建议您：

1. 调整加湿器的目标湿度，例如设定为55，以确保主卧湿度计显示的湿度达到50。
2. 将主卧湿度计放置在更接近加湿器的位置，以减少环境湿度检测的误差。

请问您想现在调整加湿器的目标湿度吗？
```
5分

#### 问题2：
```text
小爱回复：
{touser}好的，主人，我这就去设置计划任务。|{tocenter}[undoSomeAciton(id=0,action_id=1)][doSomeAcitonWhen(id=0, action="startDevice(id=22)&setDehumiTo(id=22, to_humidity=60)", when="weekloop(day=1,time=1800)&{devicestatus(id=23, key=nowHumi, value='>85')|devicestatus(id=23, key=nowTemp, value='>=27')}")][doSomeAcitonWhen(id=0, action="stopDevice(id=22)", when="weekloop(day=1,time=2100)")]

解释：
首先，小爱确认了用户的指令，并告知用户将要执行的操作。
接着，小爱调用了undoSomeAciton(id=0,action_id=1)函数来删除现有的计划任务1。
然后，小爱调用了doSomeAcitonWhen函数两次，分别设置了两个新的计划任务：
第一个计划任务的条件是每周一的下午6点，并且主卧的湿度大于85或者温度大于等于27度。满足条件时，将打开主卧的除湿机并设置目标湿度为60。
第二个计划任务的条件是每周一的晚上9点。满足条件时，将关闭主卧的除湿机。
最后，小爱将指令发送给网关中枢去执行。
```
指令正确，但是代码块后面还跟了解释，会给网关解析带来麻烦。4分

#### 问题3：
```text
小爱回复：
{touser}好的，主人，我这就为您设置这两个计划任务。|{tocenter}[doSomeAcitonWhen(id=0, action="startDevice(id=10)&setAirConditioner(id=10,mode=warm,temperature=25)", when="dayloop(time=1900,maxloops=10)&devicestatus(id=12, key=nowTemp, value='<15')")][doSomeAcitonWhen(id=0, action="startDevice(id=10)&setAirConditioner(id=10,mode=cold,temperature=22)", when="dayloop(time=1900,maxloops=10)&devicestatus(id=12, key=nowTemp, value='>26')")]

解释：
用户确认了设置计划任务的请求，因此小爱需要调用 doSomeAcitonWhen 函数来设置两个计划任务。
第一个计划任务：
action: "startDevice(id=10)&setAirConditioner(id=10,mode=warm,temperature=25)" 表示先启动客厅空调 (id=10)，然后设置空调为制热模式，温度 25 度。
when: "dayloop(time=1900,maxloops=10)&devicestatus(id=12, key=nowTemp, value='<15')" 表示每天 19 点检测客厅温湿度计 (id=12) 的温度，如果温度低于 15 度，则触发动作。该任务持续 10 天。
第二个计划任务：
action: "startDevice(id=10)&setAirConditioner(id=10,mode=cold,temperature=22)" 表示先启动客厅空调 (id=10)，然后设置空调为制冷模式，温度 22 度。
when: "dayloop(time=1900,maxloops=10)&devicestatus(id=12, key=nowTemp, value='>26')" 表示每天 19 点检测客厅温湿度计 (id=12) 的温度，如果温度高于 26 度，则触发动作。该任务持续 10 天。
两个计划任务并行设置，互不影响。
```
指令正确，但是代码块后面还跟了解释，会给网关解析带来麻烦。4分

#### 问题4：
```text
{touser}好的，主人，我明白了您的需求。我将为您设置两个计划任务，分别用于在您回家前自动调节主卧的湿度：

1. 当主卧湿度高于80%时，自动打开除湿机：
[doSomeAcitonWhen(id=0, action="startDevice(id=22)", when="dayloop(time=1800)&devicestatus(id=23, key=nowHumi, value='>80')")]

2. 当主卧湿度低于60%时，自动打开加湿器：
[doSomeAcitonWhen(id=0, action="startDevice(id=21)", when="dayloop(time=1800)&devicestatus(id=23, key=nowHumi, value='<60')")]

这两个计划任务将会在每天下午6点自动执行检测，并根据主卧的湿度情况，自动开启除湿机或加湿器，为您营造舒适的室内环境。
```
格式不对，0分

### 超市货品结算计算

第一遍：442

第二遍（如第一遍正确的话）：2687.8

0分


