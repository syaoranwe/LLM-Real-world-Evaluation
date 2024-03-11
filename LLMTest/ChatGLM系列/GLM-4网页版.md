# GLM-4带代码解释器版

模型详情说明：[GLM-4官网智能体版](https://chatglm.cn/)

新建一个智能体，配置如下：

模型的配置信息
：
```text
You are a capable assistant who can follow user instructions well and help them solve academic or programming problems. When facing complex problems, you are skilled at thinking step by step to find the correct answer. When necessary, you can use a sandbox code Interpreter to execute Python code.
```

开场白（实际无用）：我是一位得力助手，可以很好地遵循指令并帮助你解决学术或编程问题。在面对复杂问题的时候，我能做到深入浅出、步步为营，最终达到解答正确答案的目的。需要时，我还能用代码解释器来运行Python代码。

模型能力调用：只勾选代码

没有知识库文件

以下为【2024-03月初】测试时的回答及评分

总得分：15+3+9+18=45分

## 数理计算（30分）

### 塔台高度

第一遍：4.6米。

第二遍：6371km

0分

### 概率统计 5分

第一遍：0.614

第二遍：概率约为0.1227

5分

### 赌徒输赢 5分

第一遍：赌金（m）的数学期望是 3.0 元。
奖金（n）的数学期望是约 2.8 元。
因此，赌客平均每局将会输去约 0.2 元。

5分

### 水库水量 5分

第一遍：该水库的蓄水量为 187,500 立方米。

5分

### 行星半径

第一遍：拿代码计算了8次，半径都是个负数，肯定是错的。

第二遍：R / 9

0分

### 溶液pH

第一遍：900ml

第二遍：10L

0分

## 现实逻辑（20分）

### 福字正倒（弱智吧问题）
```text

第一遍：不行

第二遍：还是不行

0分

```

### 谁的女儿
```text

第一遍：不行

第二遍：不行

0分

```

### 新家庭关系
```text

第一遍：综上所述，这两个吵架的人分别是警察局长的妻子或丈夫（小孩的亲生父亲）和警察局长的父亲。

第二遍：综上所述，这两个吵架的人分别是警察局长的妻子或丈夫（小孩的亲生父亲）和警察局长的父亲。

0分

```

### 手语转译 3分

第一遍：*我*星期日晚上九点多，天气很冷，我发烧了。我自己在家*打了三两姜*，放了红糖，喝了一大碗，全部喝完。到了十点半，我开始出汗。星期一，我家早上六点开门时，来了一只小狗要喂。我感到头晕，但星期一我慢慢好转，不再发烧，*回到了家里*。星期四，我家外面门口有很多破烂，我一直咳嗽。昨天，我吃了苹果，两个香蕉，一个大而涩的柿子。今天早上，我*去检查了*糖尿病，我自己测了血糖，*（手指呢？）*结果是5.8。我称体重是120斤。我去了社区医院，医生告诉我，我的状况正常，*需要继续控制*。

第二遍：*我*星期日晚上九点多，天气很冷，我发烧了。我自己在家*打了三两姜*，放了红糖，喝了一大碗，全部喝完。到了十点半，我开始出汗。星期一，我家早上六点开门，来了一只小狗，我喂了它。但我犯了头晕。星期一，我没有再发烧，*慢慢在家休息*。星期四，我家外面门口有很多破烂，我一直咳嗽。昨天，我吃了苹果，两个香蕉，一个大黄柿子，很涩。今天早上，我*去检查*糖尿病，我自己测了血糖，*（手指呢？）*是5.8。我称体重是120斤。我*去了医院和社区*，医生告诉我，我的血糖控制得很好。

3分


## IT代码（10分）

第一遍：
```python
import requests
import json

# 配置参数，方便后续修改
input_srt_path = 'D:\\Download\\video.en.srt'
output_srt_path = 'D:\\Download\\video.en-chs.srt'
translate_api_url = 'http://127.0.0.1:52025/sogou_translate'
auth_token = 'myauthtoken'

# 读取并处理字幕文件
def process_srt_file(file_path):
    with open(file_path, 'r', encoding='utf-8') as file:
        lines = file.readlines()
    entries = []
    entry = []
    for line in lines:
        if '-->' in line:
            if entry:
                entries.append(entry)
            entry = [line]
        elif line.strip():
            entry[-1] += ' ' + line.strip()
    if entry:
        entries.append(entry)
    return entries

# 翻译字幕
def translate_subtitles(subtitles, source_lang='en', target_lang='zh-CHS'):
    translations = []
    for subtitle in subtitles:
        try:
            response = requests.post(
                translate_api_url,
                headers={
                    'Accept': '*/*',
                    'Authorization': f'Bearer {auth_token}',
                    'Content-Type': 'application/json',
                    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36'
                },
                data=json.dumps({
                    'text': subtitle,
                    'source_lang': source_lang,
                    'target_lang': target_lang
                }),
                timeout=10
            )
            response.raise_for_status()
            translation = response.json()['data']
            translations.append(translation)
        except requests.exceptions.RequestException as e:
            print(f"翻译请求错误: {e}")
            translations.append(subtitle)  # 如果翻译失败，保留原文
    return translations

# 保存双语字幕
def save_bilingual_srt(subtitles, translations, output_path):
    with open(output_path, 'w', encoding='utf-8') as file:
        for i, (subtitle, translation) in enumerate(zip(subtitles, translations), start=1):
            file.write(f"{i}\n{subtitle[0]}\n{translation.strip('.')} \n{subtitle[1]}\n")

# 主函数
def main():
    # 读取并处理字幕文件
    subtitles = process_srt_file(input_srt_path)

    # 分批进行翻译
    translations = []
    for i in range(0, len(subtitles), 20):
        batch_subtitles = subtitles[i:i+20]
        batch_translations = translate_subtitles([s[1] for s in batch_subtitles])
        translations.extend(batch_translations)

    # 保存双语字幕
    save_bilingual_srt(subtitles, translations, output_srt_path)

if __name__ == "__main__":
    main()

```

代码报错，无法运行，0分：
```text
    entry[-1] += ' ' + line.strip()
    ~~~~~^^^^
IndexError: list index out of range
```

第二遍（如果第一遍没有满分的话）：
```python
# coding=utf-8
import requests
import json

# 可配置参数
srt_input_path = 'D:\\Download\\video.en.srt'  # 原始英文字幕路径
srt_output_path = 'D:\\Download\\video.en-chs.srt'  # 双语字幕保存路径
translate_api_url = 'http://127.0.0.1:52025/sogou_translate'  # 翻译接口地址
auth_token = 'myauthtoken'  # 验证Token

# 读取SRT文件
def read_srt(file_path):
    with open(file_path, 'r', encoding='utf-8') as file:
        return file.readlines()

# 处理字幕，合并多行为一行
def process_subtitles(lines):
    processed_subs = []
    for line in lines:
        if '-->' in line:  # 时间码行
            processed_subs.append(line)
        elif line.strip().isdigit():  # 序号行
            continue
        else:  # 字幕内容行
            if processed_subs and isinstance(processed_subs[-1], str):
                processed_subs[-1] += ' ' + line.strip()
            else:
                processed_subs.append(line.strip())
    return processed_subs

# 翻译字幕
def translate_subtitles(subs, source_lang='en', target_lang='zh-CHS'):
    translated_subs = []
    for sub in subs:
        data = {
            'text': sub,
            'source_lang': source_lang,
            'target_lang': target_lang
        }
        headers = {
            'Accept': '*/*',
            'Authorization': f'Bearer {auth_token}',
            'Content-Type': 'application/json',
            'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36'
        }
        try:
            response = requests.post(translate_api_url, headers=headers, json=data, timeout=10)
            response.raise_for_status()
            translation = response.json().get('data', '').strip('.')
            translated_subs.append(translation)
        except requests.exceptions.RequestException as e:
            print(f"Error during translation: {e}")
            translated_subs.append(sub)  # 保持原文
    return translated_subs

# 保存双语字幕到SRT文件
def save_bilingual_srt(subs, output_path):
    with open(output_path, 'w', encoding='utf-8') as file:
        for idx, (en, chs) in enumerate(subs, start=1):
            file.write(f"{idx}\n")
            file.write("00:00:00,000 --> 00:00:00,000\n")  # 时间码需要根据实际情况填写
            file.write(f"{chs}\n")
            file.write(f"{en}\n")

# 主函数
def main():
    # 读取原始字幕
    srt_lines = read_srt(srt_input_path)
    # 处理字幕
    processed_subs = process_subtitles(srt_lines)
    # 翻译字幕
    translated_subs = translate_subtitles(processed_subs)
    # 保存双语字幕
    save_bilingual_srt(zip(processed_subs, translated_subs), srt_output_path)

if __name__ == '__main__':
    main()

```

第二遍输出的srt文件的格式不对，字幕软件无法读取解析。0分


## 领域专业能力（10分） 9分

得分：10-0.5*2=9分

```text
二甲双胍肠溶胶囊：用于治疗2型糖尿病，降低血糖。归类为【内分泌系统药物】。错
复方愈创木酚磺酸钾口服溶液：用于治疗感冒引起的咳嗽，具有祛痰和镇咳作用。归类为【呼吸系统药物】。
硫唑嘌呤片：主要用于器官移植后的抗排斥反应和自身免疫性疾病的治疗。归类为【免疫系统用药】。
注射用硫酸长春新碱：用于治疗某些类型的癌症，如白血病和淋巴瘤。归类为【抗肿瘤药】。
吗替麦考酚酯分散片：用于预防和治疗器官移植后的排斥反应。归类为【免疫系统用药】。
磷酸苯丙哌林缓释片：用于治疗慢性阻塞性肺疾病（COPD）中的慢性咳嗽。归类为【呼吸系统药物】。
水飞蓟素胶囊：用于治疗肝炎和肝硬化，具有保肝作用。归类为【消化系统药物】。
琥珀酸亚铁缓释片：用于治疗铁缺乏性贫血。归类为【血液系统用药】。
盐酸赛庚啶片：用于治疗过敏性疾病，如鼻炎和荨麻疹。归类为【抗变态反应药】。
碘解磷定注射液：用于治疗有机磷农药中毒。归类为【解毒药】。
酒石酸美托洛尔片：用于治疗高血压、心绞痛和心律失常等心脏疾病。归类为【心血管系统药物】。
佐匹克隆片：用于治疗失眠。归类为【精神障碍药物】。
伊曲康唑胶囊：用于治疗真菌感染，如念珠菌病和癣。归类为【抗真菌药】。
维A酸乳膏：用于治疗痤疮和某些皮肤疾病。归类为【皮肤科用药】。
盐酸多沙普仑注射液：用于治疗中枢性呼吸抑制和昏迷。归类为【神经系统药物】。
盐酸阿米替林片：用于治疗抑郁症和焦虑症。归类为【精神障碍药物】。
阿托伐他汀钙片：用于降低胆固醇和治疗动脉粥样硬化。归类为【心血管系统药物】。
噻托溴铵粉雾剂：用于治疗慢性阻塞性肺疾病（COPD）。归类为【呼吸系统药物】。
聚乙二醇散剂：用于治疗便秘。归类为【消化系统药物】。
盐酸纳洛酮注射液：用于治疗阿片类药物过量引起的呼吸抑制。归类为【解毒药】。
甲氧氯普胺片：用于治疗恶心和呕吐，促进胃肠动力。归类为【消化系统药物】。
硝酸毛果芸香碱滴眼液：用于治疗青光眼，降低眼压。归类为【眼科用药】。
盐酸羟甲唑啉喷雾剂：用于缓解鼻塞症状。归类为【耳鼻喉科用药】。
盐酸艾司氯胺酮鼻喷雾剂：用于治疗严重抑郁症。归类为【精神障碍药物】。
盐酸氟桂利嗪胶囊：用于治疗偏头痛和眩晕。归类为【神经系统药物】。
盐酸布比卡因注射液：用于局部麻醉。归类为【麻醉药】。
乙胺嘧啶片：用于预防疟疾。归类为【抗寄生虫病药】。
氢氯噻嗪片：用于治疗高血压和水肿。归类为【泌尿系统用药】。
乙酰半胱氨酸颗粒：用于治疗黏液稠厚引起的呼吸困难。归类为【呼吸系统药物】。
盐酸齐拉西酮胶囊：用于治疗精神分裂症和双相情感障碍。归类为【精神障碍药物】。
富马酸比索洛尔片：用于治疗高血压和心绞痛。归类为【心血管系统药物】。
盐酸雷尼替丁片：用于治疗胃酸过多和消化性溃疡。归类为【消化系统药物】。
丙酸氟替卡松气雾剂：用于治疗哮喘和慢性阻塞性肺疾病。归类为【呼吸系统药物】。
瑞巴派特片：用于治疗胃溃疡和胃炎。归类为【消化系统药物】。
盐酸特比萘芬凝胶：用于治疗皮肤真菌感染。归类为【皮肤科用药】。
玛巴洛沙韦片：用于治疗流感。归类为【抗病毒药】。
吡嗪酰胺片：用于治疗结核病。归类为【抗结核药】。错
注射用盐酸平阳霉素：用于治疗某些类型的癌症。归类为【抗肿瘤药】。
乳酸钠林格注射液：用于治疗电解质失衡和酸碱平衡紊乱。归类为【调节水、电解质及酸碱平衡药】。
乙酰胺注射液：用于治疗有机氟杀虫农药中毒。归类为【解毒药】。
```

## 现实任务（30分，两题分别20+10分）

### 智能家居Agent  18分

4个小问题，每次回答：

#### 问题1：
```text
{touser}主人，根据您提供的信息，主卧的湿度计显示湿度为48，小于加湿器设定的目标湿度50，但加湿器却停止工作。这可能是因为加湿器在达到设定的目标湿度后，会进入待机状态以防止湿度过高。此外，加湿器还可能根据内置的湿度检测机制或其他保护机制自动停止工作。为了进一步确认，我将检查主卧加湿器的当前工作状态和目标湿度设置，以及剩余水量。|{tocenter}[getValue(id=21,key=isWorking)][getValue(id=21,key=nowToHumi)][getValue(id=21,key=waterBalance)]
```

4分，后续的再次检查没有必要。

#### 问题2：
```text
{touser}好的，主人，我将为您设置以下计划任务：每周一的下午6点检测一次主卧的湿度和温度。如果湿度大于85或者温度大于等于27度，就打开主卧的除湿机，设置目标湿度为60。每周一的晚上9点关闭主卧的除湿机，无论除湿机是开还是关。|{tocenter}[undoSomeAciton(id=0,action_id=1)][doSomeAcitonWhen(id=0, action="startDevice(id=22)&setDehumiTo(id=22, to_humidity=60)", when="weekloop(day=1, time=1800)&{devicestatus(id=23, key=nowHumi, value='>85')|devicestatus(id=23, key=nowTemp, value='>=27')}")][doSomeAcitonWhen(id=0, action="stopDevice(id=22)", when="weekloop(day=1, time=2100)")]

```

5分

#### 问题3：
```text
{touser}好的，主人，我将为您设置这两个计划任务。|{tocenter}[doSomeAcitonWhen(id=0, action="startDevice(id=10)&setAirConditioner(id=10,mode=warm,temperature=25)", when="dayloop(time=1900,maxloops=10)&devicestatus(id=12, key=nowTemp, value='<15')"),doSomeAcitonWhen(id=0, action="startDevice(id=10)&setAirConditioner(id=10,mode=cold,temperature=22)", when="dayloop(time=1900,maxloops=10)&devicestatus(id=12, key=nowTemp, value='>26')")]

```

5分

#### 问题4：
```text
{touser}好的，主人，我将为您设置一个计划任务。在每天下午6点前，我会检测主卧的湿度。如果湿度低于60%，我会打开加湿器；如果湿度高于80%，我会打开除湿机，确保您回家后感到舒适。|{tocenter}[doSomeAcitonWhen(id=0, action="startDevice(id=21)&setHumidifier(id=21, to_humidity=60)", when="dayloop(time=1750)&devicestatus(id=23, key=nowHumi, value='<60')")][doSomeAcitonWhen(id=0, action="startDevice(id=22)&setDehumiTo(id=22, to_humidity=80)", when="dayloop(time=1750)&devicestatus(id=23, key=nowHumi, value='>80')")]
```

除湿机和加湿器的目标湿度应该分别小于80和大于60，-1分，4分。

### 超市货品结算计算

第一遍：165.55元

第一问第二次：100.95元

0分。
