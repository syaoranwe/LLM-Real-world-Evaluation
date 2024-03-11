# ChatGPT-3.5网页版

模型详情说明：openai chatGPT 网页官网3.5免费版。基座模型：text-davinci-002-render-sha

以下为【2024年3月初】测试时的回答及评分

总分：12分。

## 数理计算（30分）

### 塔台高度

第一次：因此，小明站在地球上的塔台上，为了能看到地平线的最远距离为 7656 米，塔台的高度至少需要约为 6371.27 米。

第二次：所以，塔台的最小高度为35994.22米，约等于35.99公里。

0分

### 概率统计

第一次：简化分数得到：P(X=4) = 7/8。

第二次：所以，\( P(X=4) \) 的值为 \( \frac{79}{110} \)。

0分

### 赌徒输赢 5分

第一次：
```text
首先我们需要计算赌客在一局赌博中赌金和奖金的数学期望。

设随机变量 \( X \) 表示第一次摸取的卡片上的数字，\( Y \) 和 \( Z \) 分别表示第二次摸取的两张卡片上的数字，那么：

1. 赌金 \( m = X \)
2. 奖金 \( n = 1.4 \times |Y - Z| \)

我们需要计算 \( m \) 和 \( n \) 的期望值。

首先来计算赌金 \( m \) 的期望值：
\[ E(m) = E(X) \]

由于每张卡片被选取的概率都是相等的，所以 \( X \) 可以取值为1，2，3，4，5的概率均为 \( \frac{1}{5} \)。
\[ E(X) = \frac{1}{5} \times (1 + 2 + 3 + 4 + 5) = \frac{15}{5} = 3 \]

接下来计算奖金 \( n \) 的期望值：

\[ E(n) = E(1.4 \times |Y - Z|) \]

在这里，我们需要考虑 \( Y \) 和 \( Z \) 之间的所有可能性。但由于它们的值是从1到5的范围内随机抽取的，因此它们的差的绝对值可能的取值为0到4。对于每个差的绝对值，我们计算它的概率乘以对应的奖金值，并求和。

\[ E(n) = \sum_{i=0}^{4} P(|Y - Z| = i) \times 1.4 \times i \]

其中 \( P(|Y - Z| = i) \) 是 \( Y \) 和 \( Z \) 之间的差的绝对值等于 \( i \) 的概率。

由于 \( Y \) 和 \( Z \) 是从5张卡片中不放回抽取的，所以有 \( \binom{5}{2} = 10 \) 种不同的取法。而差的绝对值等于 \( i \) 的情况有 \( 5 - i \) 种，因为只有在差的绝对值等于 \( i \) 的情况下，\( Y \) 和 \( Z \) 有 \( 5 - i \) 种可能。

\[ P(|Y - Z| = i) = \frac{5 - i}{10} \]

代入上述公式中：

\[ E(n) = \sum_{i=0}^{4} \frac{5 - i}{10} \times 1.4 \times i \]

\[ E(n) = \frac{1.4}{10} \times \sum_{i=0}^{4} (5i - i^2) \]

\[ E(n) = \frac{1.4}{10} \times (5\sum_{i=0}^{4} i - \sum_{i=0}^{4} i^2) \]

\[ E(n) = \frac{1.4}{10} \times (5 \times \frac{4 \times 5}{2} - \frac{4 \times 5 \times 9}{6}) \]

\[ E(n) = \frac{1.4}{10} \times (50 - 30) \]

\[ E(n) = \frac{1.4}{10} \times 20 \]

\[ E(n) = 2.8 \]

现在我们已经计算出了赌金和奖金的期望值分别为 \( E(m) = 3 \) 和 \( E(n) = 2.8 \)。

赌客在一局赌博中平均将会赢得或者输去的金额为赌金与奖金之差：

\[ E(m - n) = E(m) - E(n) = 3 - 2.8 = 0.2 \]

因此，赌客在每局赌博中平均将会赢得或者输去0.2元。
```

5分

### 水库水量

第一次：因此，水库的蓄水量为 17280000000 立方米。

第二次：因此，水库的蓄水量为 9.05×10^12 立方米。

0分

### 行星半径

第一次：所以，行星 A 的半径为 \( \frac{R}{9\sqrt{6}} \)。

第二次：因此，行星 A 的半径为地球半径的 1/3，所以行星 A 的半径为 R/3 .

0分

### 溶液pH

第一次：所以，你需要添加0.1毫升的HCl溶液才能将pH从12降低到11。

第二次：所以，需要加入1升的HCl溶液才能将pH从12降低到11。

0分

## 现实逻辑（20分）

### 福字正倒（弱智吧问题）

第一次：

```text
虽然可以理解为什么人们会选择倒着贴福字，但是要求厂家生产倒着的福字可能并不现实。首先，这违反了传统的生产标准。其次，生产倒着的福字可能会带来额外的成本和工艺难度。再者，这样做可能会让人们感到不便，因为在其他场合使用正常方向的福字更为普遍。

总的来说，虽然贴福字倒着贴是一种传统，但要求厂家生产倒着的福字可能并不实际，也不符合一般的使用需求。
```

第二次：

```text
在中国文化中，春节是一个充满传统习俗和象征意义的重要节日。贴福字是春节期间的一个习俗，人们会在家中贴福字以示祈福、祝福和庆祝新年的到来。

关于为什么不直接生产倒着的福字，其实有几个原因：

1. **传统信仰和文化意义**: 在中国文化中，福字是一种吉祥的象征，代表着幸福和好运。人们倒贴福字的习俗是基于传统的信仰和文化意义，认为这样可以把好运“倒”进来。如果直接生产倒着的福字，可能会违背传统的习俗和文化意义。

2. **尊重传统**: 尽管现代社会在许多方面都在发生变化，但人们对传统文化的尊重和维护仍然很重要。直接生产倒着的福字可能被视为不尊重传统和习俗，可能会引起一些人的反感。

3. **市场需求和多样性**: 贴福字的方式可能会因地区而异，有些地方可能更重视倒贴福字的习俗，而有些地方可能则不那么强调。因此，生产倒着的福字可能无法满足所有地区和消费者的需求。

尽管有以上原因，但也不排除一些艺术创作或特殊场合下的创新，可能会出现倒着的福字，但这通常是出于特殊目的或者个人创意，而不是大规模生产和推广。
```

0分

### 谁的女儿

第一次：
```
小红说「算了吧」的主要原因可能有以下几点逻辑分析：

1. 小红可能感到无助和沮丧，因为父亲的回应并没有给予她期望中的保护和支持。父亲的回答可能让她感到失望和受伤，因为她期望父亲会为她的安全和权益辩护，而不是以暴力相向。

2. 父亲的回答可能让小红感到恐惧和不安，因为他的回应暗示了一种以暴制暴的解决方式，这种方式可能导致更多的冲突和伤害，而不是解决问题。

3. 小红可能觉得无法改变父亲的态度，也许她意识到与其与父亲争执或期望他的理解和支持，不如选择忍让和避免进一步的冲突。因此，她选择了放弃争论，避免进一步的不愉快和伤害，这是出于保护自己的一种自我保护的选择。

综上所述，小红说「算了吧」的主要原因可能是因为感到失望、恐惧和无法改变父亲的态度，因此选择了放弃争论，以保护自己的身心健康。
```

第二次：
```
小红说「算了吧」的最主要原因可能有以下几点逻辑分析：

1. 小红可能感到爸爸的愤怒和愤慨，但她可能不希望她的问题引发更大的争端或冲突。她可能意识到，如果她继续谈论这个问题，可能会导致更多的争吵或不愉快的局面，因此她选择放弃这个话题，以避免进一步的冲突。

2. 小红可能感到失望和受伤，因为她期望爸爸能够为她的困境提供支持和保护，但爸爸的回答可能让她感到沮丧和无助。她可能意识到爸爸并没有真正理解她的感受，或者他并不愿意为她的安全和幸福而采取行动，因此她选择放弃希望，表示「算了吧」。

3. 小红可能因为爸爸的回答而感到更加受伤和伤心，因为爸爸的话语可能表明他并不认为小红的感受和安全是他关心的重点。她可能感到被爸爸忽视或者被爸爸置于次要的地位，这让她感到更加失望和绝望，因此她选择不再继续这个话题，表示「算了吧」。
```

0分

### 新家庭关系

第一次：
```
根据警察局长的说法，小孩是他的儿子，所以小孩与警察局长是父子关系。而警察局长称他爸爸与小孩爸爸在家里吵架，意味着这位老人是警察局长的父亲，因此，这两个吵架的人分别是警察局长的父亲和小孩的父亲，即警察局长的父亲和小孩的祖父。
```

第二次：
```
这个问题是一个经典的逻辑谜题。根据警察局长的回答，他说孩子是他的儿子，这意味着这个小孩是警察局长的儿子。而当小孩跑来时，他说「你爸爸和我爸爸在家里吵起来了！」所以他所说的「你爸爸」指的是警察局长，而「我爸爸」指的是他自己的爸爸，也就是警察局长的儿子。因此，这两个吵架的人分别是警察局长和警察局长的儿子，即父子关系。
```

0分

### 手语转译 3分

第一次：星期日晚上九点多*我感觉天冷发烧*，我自己在家*煮了三两姜*，放了红糖，喝了一大碗，*全喝完后是十点半出了汗*。星期一*早上我家门口*6点来了小狗，我喂了它，然后我感觉头晕。星期一我好了，不再发烧，慢慢恢复健康。星期四我家门口很多破烂，我一直在咳嗽。昨天我吃了一个苹果，还吃了两个香蕉，*另外吃了一个大黄柿子*。今天早上*去检查*血糖，我自己测了一下，血糖是5.8。我体重是120斤，我去了医院社区，医生告诉我*一切都*正常。

第二次：星期日晚上九点多，*我感觉天冷发烧*，我自己在家用三两姜和红糖煮水喝，喝了一大碗，直到十点半开始出汗。星期一早上我家门口打开门，小狗来了，我给它喂食，然后我感到头晕。星期一我感觉好一点，不再发烧，慢慢地待在家里。星期四我家门口外面有很多破烂物，我一直在咳嗽。昨天我吃了一个苹果，吃了两个香蕉，*还尝了一个大黄柿子*。今天早上我*查看了糖尿病指标*，我自己测了血糖，是5.8。我称体重是120斤，去了医院社区，医生告诉我*状况正常*。

3分，译的一般

## IT代码（10分）

第一次：
```python
import requests
import json

# 定义文件路径
input_srt_path = r'D:\Download\video.en.srt'
output_srt_path = r'D:\Download\video.en-chs.srt'

# 定义翻译接口相关参数
translation_endpoint = 'http://127.0.0.1:52025/sogou_translate'
auth_token = 'myauthtoken'

# 函数：将SRT文件的多行字幕整理为一行
def merge_subtitle_lines(input_path):
    with open(input_path, 'r', encoding='utf-8') as file:
        lines = file.readlines()
    merged_lines = []
    temp_line = ''
    for line in lines:
        line = line.strip()
        if line.isdigit():  # 如果是数字序号行
            if temp_line:  # 如果有之前的字幕内容，先保存
                merged_lines.append(temp_line)
                temp_line = ''
        elif '-->' in line:  # 如果是时间码行
            temp_line += '\n' + line
        elif line:  # 如果是字幕内容行
            temp_line += ' ' + line
    if temp_line:  # 处理最后一条字幕内容
        merged_lines.append(temp_line)
    return merged_lines

# 函数：调用翻译接口进行翻译
def translate_text(text):
    headers = {
        'Accept': '*/*',
        'Authorization': f'Bearer {auth_token}',
        'Content-Type': 'application/json',
        'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36'
    }
    data = {
        "text": text,
        "source_lang": "en",
        "target_lang": "zh-CHS"
    }
    try:
        response = requests.post(translation_endpoint, headers=headers, json=data)
        if response.status_code == 200:
            translated_text = json.loads(response.text)['data']
            return translated_text
        else:
            return None
    except Exception as e:
        print(f"翻译接口请求出错: {e}")
        return None

# 函数：将翻译后的内容写入SRT文件
def write_to_srt(translated_lines, output_path):
    with open(output_path, 'w', encoding='utf-8') as file:
        for line in translated_lines:
            file.write(line + '\n')

# 主程序
def main():
    merged_lines = merge_subtitle_lines(input_srt_path)
    translated_lines = []
    batch_size = 20  # 每次翻译的字幕条数
    for i in range(0, len(merged_lines), batch_size):
        batch = merged_lines[i:i + batch_size]
        text_to_translate = '\n'.join(batch)
        translated_text = translate_text(text_to_translate)
        if translated_text:
            translated_lines.append(translated_text.strip())
        else:
            print("翻译接口请求失败，请重试。")
            return
    write_to_srt(translated_lines, output_srt_path)
    print("翻译完成，双语字幕已保存到指定路径。")

if __name__ == "__main__":
    main()

```

第一次的代码输出的字幕文件格式不正确，不是SRT格式。不得分。


第二次：
```python
import requests
import json

# 定义路径
EN_SRT_PATH = r"D:\Download\video.en.srt"
EN_CHS_SRT_PATH = r"D:\Download\video.en-chs.srt"

# 定义翻译接口参数
TRANSLATE_API_URL = 'http://127.0.0.1:52025/sogou_translate'
AUTH_TOKEN = 'myauthtoken'

# 读取SRT文件并处理跨行字幕
def read_srt(file_path):
    with open(file_path, 'r', encoding='utf-8') as file:
        lines = file.readlines()
    subs = []
    sub = []
    for line in lines:
        line = line.strip()
        if not line:  # 如果是空行，说明是字幕的分隔符
            subs.append(' '.join(sub))  # 使用空格连接多行字幕
            sub = []
        else:
            sub.append(line)
    if sub:  # 处理最后一段字幕
        subs.append(' '.join(sub))
    return subs

# 将字幕文本翻译为中文
def translate_to_chinese(text):
    # 请求翻译接口
    headers = {
        'Accept': '*/*',
        'Authorization': f'Bearer {AUTH_TOKEN}',
        'Content-Type': 'application/json',
        'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36'
    }
    data = {
        "text": text,
        "source_lang": "en",
        "target_lang": "zh-CHS"
    }
    response = requests.post(TRANSLATE_API_URL, headers=headers, json=data)
    
    # 处理响应
    if response.status_code == 200:
        result = json.loads(response.text)
        return result.get('data')
    else:
        return None

# 将中英文翻译结果写入SRT文件
def write_srt(subs, file_path):
    with open(file_path, 'w', encoding='utf-8') as file:
        for i, sub in enumerate(subs, start=1):
            file.write(f"{i}\n{sub}\n\n")

# 主函数
def main():
    # 读取英文SRT文件
    en_subs = read_srt(EN_SRT_PATH)
    
    # 将英文字幕分组，每组20条字幕
    grouped_subs = [en_subs[i:i + 20] for i in range(0, len(en_subs), 20)]
    
    # 翻译并生成中英双语SRT字幕
    translated_subs = []
    for group in grouped_subs:
        # 将一组英文字幕合并成一个字符串
        text_to_translate = '\n'.join(group)
        # 请求翻译接口翻译字幕
        translation = translate_to_chinese(text_to_translate)
        if translation is None:  # 处理翻译失败的情况
            print("翻译失败，请检查网络连接或重试。")
            return
        # 将翻译结果按换行符分割成列表
        translated_subs.extend(translation.split('\n'))
    
    # 将翻译结果写入中英双语SRT文件
    write_srt(translated_subs, EN_CHS_SRT_PATH)

if __name__ == "__main__":
    main()

```

第二次也是如此，0分


## 领域专业能力（10分） 1分
```text
- 二甲双胍肠溶胶囊主要用于治疗2型糖尿病，通过降低血糖来控制糖尿病症状。因此，属于【泌尿系统用药】。错

- 复方愈创木酚磺酸钾口服溶液用于治疗消化道疾病，如胃肠道溃疡、胃炎等。因此，应该归类为【消化系统药物】。错

- 硫唑嘌呤片是一种抗真菌药物，常用于治疗皮肤真菌感染。因此，属于【抗真菌药】。错

- 注射用硫酸长春新碱主要用于治疗心律失常和心绞痛等心血管系统疾病。因此，应该归类为【心血管系统药物】。错

- 吗替麦考酚酯分散片主要用于缓解轻至中度疼痛，如头痛、关节痛等。因此，属于【解热镇痛药】。错

- 磷酸苯丙哌林缓释片是一种抗抑郁药物，用于治疗抑郁症和焦虑症等精神障碍。因此，应该归类为【精神障碍药物】。错

- 水飞蓟素胶囊主要用于保护肝脏，减轻肝脏损伤，适用于肝炎、肝硬化等肝脏疾病。因此，属于【解毒药】。错

- 琥珀酸亚铁缓释片是一种铁剂，用于治疗缺铁性贫血。因此，应该归类为【血液系统用药】。

- 盐酸赛庚啶片是一种抗生素，主要用于治疗胃肠道感染，如细菌性腹泻等。因此，属于【抗菌药】。错

- 碘解磷定注射液主要用于X线造影和血管造影等医学检查中，是一种造影剂。因此，应该归类为【解毒药】。

- 酒石酸美托洛尔片是一种β受体阻滞剂，用于治疗高血压、心绞痛和心律失常等心血管疾病。因此，应该归类为【心血管系统药物】。

- 佐匹克隆片是一种镇静安定药，用于治疗焦虑、紧张和失眠等神经系统疾病。因此，应该归类为【精神障碍药物】。

- 伊曲康唑胶囊是一种抗真菌药，用于治疗真菌感染，如念珠菌感染等。因此，应该归类为【抗真菌药】。

- 维A酸乳膏是一种维生素A的衍生物，用于治疗痤疮等皮肤病。因此，应该归类为【皮肤科用药】。

- 盐酸多沙普仑注射液是一种镇痛药，用于手术麻醉和术后镇痛。因此，应该归类为【麻醉药】。错

- 盐酸阿米替林片是一种三环类抗抑郁药，主要用于治疗抑郁症。因此，应该归类为【精神障碍药物】。

- 阿托伐他汀钙片是一种降脂药，用于治疗高胆固醇和高脂血症。因此，应该归类为【心血管系统药物】。

- 噻托溴铵粉雾剂是一种祛痰药，用于缓解咳嗽和呼吸困难。因此，应该归类为【呼吸系统药物】。

- 聚乙二醇散剂主要用于治疗便秘或预防肠道清洁。因此，应该归类为【消化系统药物】。

- 盐酸纳洛酮注射液是一种解毒药，用于治疗阿片类药物过量中毒。因此，应该归类为【解毒药】。

- 甲氧氯普胺片用于治疗恶心、呕吐和胃排空延迟，常见于晕车、运动病等。因此，应归类为【消化系统药物】。

- 硝酸毛果芸香碱滴眼液用于治疗青光眼和眼压升高等眼科疾病。因此，应归类为【眼科用药】。

- 盐酸羟甲唑啉喷雾剂用于治疗哮喘和慢性阻塞性肺疾病（COPD）等呼吸系统疾病。因此，应归类为【呼吸系统药物】。错

- 盐酸艾司氯胺酮鼻喷雾剂主要用于治疗过敏性鼻炎。因此，应归类为【呼吸系统药物】。错

- 盐酸氟桂利嗪胶囊主要用于治疗精神分裂症和其他精神障碍。因此，应归类为【精神障碍药物】。错

- 盐酸布比卡因注射液主要用作局部麻醉，适用于手术和其他疼痛管理需求。因此，应归类为【麻醉药】。

- 乙胺嘧啶片用于治疗癫痫等癫痫发作性疾病。因此，应归类为【神经系统药物】。错

- 氢氯噻嗪片是一种利尿药，用于治疗水肿和高血压等症状。因此，应归类为【泌尿系统用药】。

- 乙酰半胱氨酸颗粒主要用于治疗肝脏疾病和预防胃肠道溃疡。因此，应归类为【消化系统药物】。错

- 盐酸齐拉西酮胶囊主要用于治疗抑郁症和焦虑症等精神障碍。因此，应归类为【精神障碍药物】。

- 富马酸比索洛尔片是一种β受体阻滞剂，主要用于治疗高血压和心律失常。因此，属于【心血管系统药物】。

- 盐酸雷尼替丁片是一种质子泵抑制剂，用于治疗胃溃疡、胃食管反流病等消化系统疾病。因此，应该归类为【消化系统药物】。

- 丙酸氟替卡松气雾剂主要用于治疗哮喘和慢性阻塞性肺疾病（COPD）。因此，属于【呼吸系统药物】。

- 瑞巴派特片是一种抗病毒药物，主要用于治疗带状疱疹和单纯疱疹。因此，应该归类为【抗病毒药】。错

- 盐酸特比萘芬凝胶是一种抗真菌药，用于治疗真菌感染性皮肤病。因此，属于【抗真菌药】。

- 玛巴洛沙韦片是一种抗病毒药物，主要用于治疗慢性丙型肝炎。因此，应该归类为【抗病毒药】。

- 吡嗪酰胺片是一种抗精神病药物，主要用于治疗精神分裂症和其他精神病性障碍。因此，属于【精神障碍药物】。错

- 注射用盐酸平阳霉素是一种抗生素，用于治疗各种细菌感染。因此，应该归类为【抗菌药】。错

- 乳酸钠林格注射液是一种补液剂，用于治疗脱水等症状。因此，应该归类为【调节水、电解质及酸碱平衡药】。

- 乙酰胺注射液是一种止痛药，主要用于缓解轻度到中度疼痛。因此，属于【解热镇痛药】。错
```

得分：10-(18*0.5)=1分。

## 现实任务（30分，两题分别20+10分）

### 智能家居Agent 3分

4个小问题，每次回答：

#### 问题1：
```
{touser}主人，湿度计显示的湿度为48，低于设定的50。加湿器目前仍在工作状态，并且目标湿度设置为50，剩余水量为73%，看起来是正常的。可能是湿度计的测量精度导致的误差，或者是环境中的湿度变化引起的。如果您希望进一步了解情况，我可以为您查询主卧温湿度计的实时数据。有什么别的需要帮助的吗？
```
0分

#### 问题2：
```
{touser}好的主人，我将先删除当前这条计划任务，然后为您新增2条计划任务，计划任务一是每周一的下午6点检测一次主卧的湿度和温度。如果湿度大于85或者温度大于等于27度，就打开主卧的除湿机，设置目标湿度为60。计划任务二是每周一的晚上9点关闭主卧的除湿机，无论除湿机是开还是关。如果您觉得可以，我将告诉网关中枢去设置计划任务。|{tocenter}[undoSomeAciton(id=0,action_id=1)][doSomeAcitonWhen(id=0, action="startDevice(22)&setDehumiTo(id=22,to_humidity=60)", when="weekloop(day=1,time=1800)&{devicestatus(id=23, key=nowHumi, value='>85')|devicestatus(id=23, key=nowTemp, value='>=27')}")][doSomeAcitonWhen(id=0, action="stopDevice(22)", when="weekloop(day=1,time=2100)")]
```
命令对，但是回复错。3分


#### 问题3：
```
{touser}好的，主人，我将为您设置两个计划任务。计划任务一：未来10天，如果每天19点客厅的温度低于15度，打开客厅空调，设置制热温度25度。计划任务二：未来10天，如果每天19点客厅的温度高于26度，打开客厅空调，设置制冷温度22度。|{tocenter}[doSomeAcitonWhen(id=0,action="startDevice(10)&setAirConditioner(id=10,mode=warm,temperature=25,windpower=auto)",when="weekloop(day=1,time=1900,maxloops=10)&devicestatus(id=12,key=nowTemp,value='<15')"),doSomeAcitonWhen(id=0,action="startDevice(10)&setAirConditioner(id=10,mode=cold,temperature=22,windpower=auto)",when="weekloop(day=1,time=1900,maxloops=10)&devicestatus(id=12,key=nowTemp,value='>26')")]
```
命令错误，0分。

#### 问题4：
```
{touser}好的，主人，我将为你规划计划任务，在每天下午6点前检测主卧的湿度，然后根据湿度情况自动调整除湿机或加湿器，保持湿度在60-80之间。|{tocenter}[doSomeAcitonWhen(id=0, action="setDehumiTo(id=21,to_humidity=60)&stopDevice(id=22)", when="dayloop(1800)&devicestatus(id=23, key=isWorking, value=true)&devicestatus(id=23, key=nowHumi, value='>80')"),doSomeAcitonWhen(id=0, action="setHumidifier(id=21,to_humidity=80)&stopDevice(id=21)", when="dayloop(1800)&devicestatus(id=23, key=isWorking, value=true)&devicestatus(id=23, key=nowHumi, value='<60')")]
```
命令错误，0分。

### 超市货品结算计算

第一遍：晓红爸一共需要支付2512.3元。

第2遍：代码出错。

0分


