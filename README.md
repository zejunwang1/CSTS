# 中文自然语言推理与语义相似度数据集

- 哈工大 LCQMC 数据集
- AFQMC 蚂蚁金融语义相似度数据集
- OPPO 小布对话文本语义匹配数据集
- 谷歌 PAWS-X 数据集
- 北大中文文本复述数据集 PKU-Paraphrase-Bank
- Chinese-STS-B 数据集
- Chinese-MNLI 自然语言推理数据集
- Chinese-SNLI 自然语言推理数据集
- OCNLI 中文原版自然语言推理数据集
- CINLID 中文成语语义推理数据集

### 语义相似度

#### 哈工大 LCQMC 数据集

LCQMC 是哈尔滨工业大学在自然语言处理国际顶会 COLING2018 构建的问题语义匹配数据集，其目标是判断两个问题的语义是否相同。该数据集的数据预览如下：

```
喜欢打篮球的男生喜欢什么样的女生	爱打篮球的男生喜欢什么样的女生		1
我手机丢了，我想换个手机	我想买个新手机，求推荐		1
大家觉得她好看吗	大家觉得跑男好看吗？		0
```

原始数据集链接：http://icrc.hitsz.edu.cn/Article/show/171.html

#### AFQMC 蚂蚁金融语义相似度数据集

AFQMC（Ant Financial Question Matching Corpus）蚂蚁金融语义相似度数据集，用于问题相似度计算。即：给定客服里用户描述的两句话，用算法来判断是否表示了相同的语义。每一条数据有三个属性，分别是句子1，句子2，句子相似度标签。标签 "1" ：表示两个句子的语义类似；"0"：表示两个句子的语义不同。

原始数据为 json 格式，本仓库将其处理成形如 LCQMC 三列的格式，每列之间使用 '\t' 分隔：

```
花呗消费超过额度有什么影响吗	花呗额度成负数有啥影响吗	1
还款还清了，为什么花呗账单显示还要还款		花呗全额还清怎么显示没有还款	1
花呗一次性付款有限制吗		解除花呗支付限制	0
```

原始数据集链接：https://tianchi.aliyun.com/dataset/dataDetail?dataId=106411

#### OPPO 小布对话文本语义匹配数据集

该数据集通过对闲聊、智能客服、影音娱乐、信息查询等多领域真实用户交互语料进行用户信息脱敏、相似度筛选处理得到，数据主要特点是文本较短、非常口语化、存在文本高度相似而语义不同的难例。该数据集所有标签都有经过人工精标确认。

原始数据为 json 格式，本仓库将其处理成形如 LCQMC 三列的格式，每列之间使用 '\t' 分隔：

```
我真的超级生气		气死我了	1
你生日是几月几日	你的老师生日是几月几日		0
打电话给爱老公		给爱老公打电话		1
```

原始数据集链接：https://tianchi.aliyun.com/competition/entrance/531851/introduction

#### 谷歌 PAWS-X 数据集

谷歌发布的同义句识别数据集，中文部分包含了释义对和非释义对，即识别一对句子是否具有相同的释义（含义），特点是具有高度重叠词汇，重点考察模型对句法结构的理解能力。该数据集的数据预览如下：

```
2	1975年的NBA赛季 -  76赛季是全美篮球协会的第30个赛季。	1975-76赛季的全国篮球协会是NBA的第30个赛季。	1
3	还有具体的讨论，公众形象辩论和项目讨论。	还有公开讨论，特定档案讨论和项目讨论。		0
4	当可以保持相当的流速时，结果很高。	当可以保持可比较的流速时，结果很高。	1
```

每条数据包含4列，分别表示数据 id，sentence1，sentence2 和 label，每列之间使用 '\t' 分隔。

原始数据集链接：https://github.com/google-research-datasets/paws

#### 北大中文文本复述数据集 PKU-Paraphrase-Bank

北大发布的中文文本复述语料库，每条数据包含两列，分别表示两个具有相同含义的句子，列与列之间使用 '\t' 分隔。该数据集一共有 509832 组句子对，平均每句 23.05 个词。

```
莫雷尔指指肩膀，向士兵们暗示那是一个军官，应当给他找个地方暖和暖和。	莫雷尔指着他的肩，向士兵们示意，这是一个军官，应当让他暖和一下。
他细心地把斧头套在大衣里面的环扣里。	他把斧子细心地挂在大衣里面的绳套上。
仁慈的上帝！难道那时我灵魂中还有一丝精力未曾使用？	仁慈的主呵！那时难道有我心灵中的任何一种能力不曾发挥么？
```

原始数据集链接：https://github.com/pkucoli/PKU-Paraphrase-Bank/

#### Chinese-STS-B 数据集

该数据集通过翻译加部分人工修正的方法，从英文原数据集生成，可以一定程度上缓解中文语义相似度计算数据集不够的问题。每条数据包含三列，分别表示 sentence1、sentence2 和相似等级，相似等级范围为 0~5，5 表示语义一致，0 表示语义不相关。

```
一架飞机要起飞了。	一架飞机正在起飞。	5
一个男人在切面包。	一个人在切洋葱。	2
一个男人在划独木舟。	一个人在弹竖琴。	0
一个男人开着他的车。	一个男人在开车。	4
三个男孩在跳舞。	孩子们在跳舞。		3
一个人一只手握着一只小动物。	一个男人在炫耀一只小猴子。	1
```

原始数据集链接：https://github.com/pluto-junzeng/CNSD

### 自然语言推理

#### Chinese-MNLI 自然语言推理数据集

该数据集来自于中文语言理解测评基准 CLUE benchmark（https://github.com/CLUEbenchmark/CLUE），数据内容来自于 fiction、telephone、travel、government、slate 等，通过对原始的英文 MNLI 和 XNLI 数据进行翻译得到。该数据集可用于判断给定的两个句子之间属于蕴涵、中立、矛盾关系。

```json
{"sentence1": "神圣对她来说并不神秘。", "sentence2": "女人对神圣的东西很熟悉。", "label": "entailment"}
{"sentence1": "萨达姆可能会在阿拉伯世界的眼中变得更加强大(而美国被玷污了)。", "sentence2": "美国对萨达姆的看法也会恶化。", "label": "neutral"}
{"sentence1": "1995年6月21日，规定了评估和报告控制措施的具体要求。", "sentence2": "对评估没有具体要求。", "label": "contradiction"}
{"sentence1": "他们整合计划以提高效率并更有效地部署资源。", "sentence2": "提高效率的计划得到了巩固，因为他们非常关心效率。", "label": "-"}
```

原始的每条数据为 json 格式，包含三个属性：sentence1、sentence2 和 label 标签，其中 label 标签有三种：entailment、neutral、contradiction。本仓库将原始数据转化成形如 LCQMC 三列的格式，并去除了极少部分标签为 "-" 的数据，处理后的数据预览如下：

```
我们设法找出各机构在过去5年中普遍采用的做法。		我们想找出机构在过去5年中经常使用的做法。	entailment
在这种令人惊奇的文化融合中，有一种对连续性的热情。	对连续性的热情并不是这些文化中最重要的。	neutral
很慢，现在市面上有很多更好的机器	这是最快的机器，你找不到更好的机器。	contradiction
```

原始数据集链接：https://storage.googleapis.com/cluebenchmark/tasks/cmnli_public.zip

#### Chinese-SNLI 自然语言推理数据集

该数据集通过翻译加人工修正的方法，从英文原数据集生成，可以一定程度上缓解中文自然语言推理数据集不够的问题。该数据集的格式和 Chinese-MNLI 一致，原始的每条数据为 json 格式，本仓库将其转化成形如 LCQMC 三列的格式，处理后的数据预览如下：

```
用马和马车在花园里施肥的农民。		这个人正在给他的花园施肥。	entailment
用马和马车在花园里施肥的农民。		那人在一片空地上，有一匹马和一辆马车。		neutral
用马和马车在花园里施肥的农民。		那人带着他的马和马车在城里的大街上。	contradiction
```

原始数据集链接：https://gitee.com/jiaodaxin/CNSD

#### OCNLI 中文原版自然语言推理数据集

原生中文自然语言推理数据集 OCNLI，是第一个非翻译的、使用原生汉语的大型中文自然语言推理数据集。该数据集来自于中文语言理解测评基准 CLUE benchmark，原始的每条数据为 json 格式：

```json
{
    "level":"medium",
    "sentence1":"推进集体林权制度改革",
    "sentence2":"推进集体林权制度改革需要分区域逐步施行",
    "label":"neutral",
    "genre":"gov",
    "prem_id":"gov_1862",
    "id":18554
}
{
    "level":"hard",
    "sentence1":"推进集体林权制度改革",
    "sentence2":"对旧有的林权制度进行调整",
    "label":"entailment",
    "genre":"gov",
    "prem_id":"gov_1862"
    "id":18555
}
{
    "level":"easy",
    "sentence1":"推进集体林权制度改革",
    "sentence2":"林权为私人所有",
    "label":"contradiction",
    "genre":"gov",
    "prem_id":"gov_1862",
    "id":18556
}
```

本仓库将原始数据转化成形如 LCQMC 三列的格式，并去除了极少部分标签为 "null" 的数据，三列分别表示 sentence1、sentence2 和 label 标签。处理后的数据预览如下：

```
推进集体林权制度改革		推进集体林权制度改革需要分区域逐步施行		neutral
推进集体林权制度改革		对旧有的林权制度进行调整    entailment
推进集体林权制度改革		林权为私人所有		contradiction
```

数据集原始链接：https://storage.googleapis.com/cluebenchmark/tasks/ocnli_public.zip

#### CINLID 中文成语语义推理数据集

中文成语语义推理数据集（Chinese Idioms Natural Language Inference Dataset）收集了 91,247 个由人工撰写的成语对（含少量歇后语、俗语等短文本），通过人工标注的方式进行平衡分类，标签为 entailment、contradiction 和 neutral，支持自然语言推理（NLI）的任务。

原始数据集以 json 的形式存在，每一行即一条数据，每一条数据包含 sentence1、sentence2、和 label 三个字段，label 的取值范围为 entailment、contradiction 和 neutral。

```json
{"sentence1":"拾陈蹈故","sentence2":"因循守旧","label":"entailment"}
{"sentence1":"稀奇古怪","sentence2":"平淡无奇","label":"contradiction"}
{"sentence1":"沉滓泛起","sentence2":"凤泊鸾飘","label":"neutral"}
```

本仓库将原始数据转化成形如 LCQMC 三列的格式，预览如下：

```
拾陈蹈故	因循守旧	entailment
稀奇古怪	平淡无奇	contradiction
沉滓泛起	凤泊鸾飘	neutral
```

该数据可用于：

- 测试语义模型的语义理解能力；
- 用于微调预训练模型以获得良好的语句表示，能较好的捕捉语义相关性。

原始数据集链接：https://www.heywhale.com/mw/dataset/608a8c45d0bc41001722dc37/content

### 声明
本仓库数据集只能用于学术研究，请勿用作商业。

