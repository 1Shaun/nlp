
# anhuidianxinzhidao 说明
- 下载地址： [百度网盘](https://pan.baidu.com/s/17Cj5tWHtVAVOz_--Bgb0Fg)  提取码：08F3
- 数据概览： 15.6 万条电信问答数据
- 推荐实验： FAQ 问答系统
- 数据来源： 快速问医网

## 1.加载数据


```python
import pandas as pd
```


```python
path = 'anhuidianxinzhidao_文件夹_所在_路径'
```


```python
pd_all = pd.read_csv(path + 'kuaisuwenyi.csv')
```

## 字段说明

| 字段<span class="Apple-tab-span" style="white-space:pre"></span> | 说明<span class="Apple-tab-span" style="white-space:pre"></span> |
| :-: | :-: |
| title<span class="Apple-tab-span" style="white-space:pre"></span> | 病人问题标题<span class="Apple-tab-span" style="white-space:pre"></span> |
| title_link<span class="Apple-tab-span" style="white-space:pre"></span> | 病人问题连接<span class="Apple-tab-span" style="white-space:pre"></span> |
| content<span class="Apple-tab-span" style="white-space:pre"></span> | 病人问题内容<span class="Apple-tab-span" style="white-space:pre"></span> |
| answer1<span class="Apple-tab-span" style="white-space:pre"></span> | 第一个医生回答<span class="Apple-tab-span" style="white-space:pre"></span> |
| Answer2<span class="Apple-tab-span" style="white-space:pre"></span> | 第二个医生回答<span class="Apple-tab-span" style="white-space:pre"></span> |


```python
pd_all.sample(n=20)
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>title_link</th>
      <th>content</th>
      <th>answer1</th>
      <th>answer3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>148991</th>
      <td>我得了影翅虫皮炎，请问能治好吗？</td>
      <td>http://www.120ask.com/question/61319194.htm</td>
      <td>医生，您好我得了影翅虫皮炎，医生给我配了硼酸洗液和头孢地尼胶囊，还有清热散结片。请问这些药管用吗？</td>
      <td>病情分析：隐翅虫皮炎是接触了隐翅虫毒液而引起的一种毒性皮炎。单纯以上那些药效果不明显的。指导...</td>
      <td>病情分析：隐翅虫皮炎是拍打死隐翅虫后隐翅虫体内的强酸性物质粘到那里那里就会引起强酸腐蚀性皮炎...</td>
    </tr>
    <tr>
      <th>96784</th>
      <td>面部皮炎症状有哪些？</td>
      <td>http://www.120ask.com/question/64337969.htm</td>
      <td>我今年刚找到工作，工作主要是面对电脑，最近工作也很忙，昨天我感觉自己的脸上出现了好多的小红疙...</td>
      <td>病情分析：面部皮炎一般是以皮疹，瘙痒为特点的，都是过敏导致的，考虑过敏性的皮炎的。指导意见：...</td>
      <td>病情分析：考虑皮肤炎症引起的现象，会有皮疹，皮肤起包，瘙痒破溃蜕皮的症状。指导意见：建议多饮...</td>
    </tr>
    <tr>
      <th>7503</th>
      <td>十一个月的宝宝得了荨麻疹！怎么办！得注意</td>
      <td>http://www.120ask.com/question/54283656.htm</td>
      <td>宝宝得了荨麻疹！我看着她好难受啊得怎么办啊有去看医生了！医生开了药吃和擦！但没什么作用！怎么办</td>
      <td>病情分析：你好，看了你的描述，基本了解情况。\n荨麻疹治疗就可以指导意见：吃点氯雷他定糖浆，...</td>
      <td>你好，荨麻疹是一种常见的过敏性皮肤病，跟个人体质免疫力也是有一定的联系，其病因由于起的快消失...</td>
    </tr>
    <tr>
      <th>45211</th>
      <td>有痔疮,大便拉血怎么回事</td>
      <td>http://www.120ask.com/question/65741330.htm</td>
      <td>病情描述：屁股上长了痔疮，拉屎还会拉出血，该怎么办，想去治疗一下了，我住在长沙，请问哪里治疗...</td>
      <td>病情分析：你好.痔疮是直肠下端,肛管,肛缘静脉丛的淤血,由静脉丛扩张,屈曲而形成的软性静脉团...</td>
      <td>痔疮是一种常见的肛肠疾病，有不少患者因为不是很了解痔疮，所以对于痔疮的治疗也比较盲目，得了痔...</td>
    </tr>
    <tr>
      <th>77271</th>
      <td>既然得了鼻咽癌需要怎么治疗？</td>
      <td>http://www.120ask.com/question/61810122.htm</td>
      <td>请问一下得了鼻咽癌这种病要怎么办？癌症听起来好恐怖，而且最近鼻涕流的不停，鼻涕带血、有经常性...</td>
      <td>指导意见：鼻咽癌肿瘤较大，若向上生长，侵犯颅底骨质会引起头疼，鼻咽部位周围有丰富的神经和血管...</td>
      <td>指导意见：你好，根据上述病情描述分析，考虑需要排除鼻咽癌，建议检查颌面部CT明确病情，早期肿...</td>
    </tr>
    <tr>
      <th>50384</th>
      <td>得了抑郁症要去精神病院治疗吗？</td>
      <td>http://www.120ask.com/question/39341247.htm</td>
      <td>同事小李最近一直闷闷不乐的，做什么事情都打不起精神来。一天到晚一个人呆在那里，叫他与我们一起...</td>
      <td>病情分析：抑郁症又称忧郁症，是以情绪低落为主要特征的一类心理疾病，其临床表现轻型病人外表如常...</td>
      <td>病情分析：抑郁症是一种常见的心境障碍，可由各种原因引起，以显著而持久的心境低落为主要临床特征...</td>
    </tr>
    <tr>
      <th>100593</th>
      <td>孕妇严重感冒怎么办</td>
      <td>http://www.120ask.com/question/13402820.htm</td>
      <td>主要症状:我现在怀孕4个半月了,鼻子堵塞,喉咙很痛,说话困难连吞口水痛,请问在不吃药的情况下...</td>
      <td>病情分析: 秋冬季天气干燥,气温变化大,易于患孕妇感冒,尤其是怀孕妇女自身免疫力下降,较一般...</td>
      <td>病情分析:你好,妊娠后,孕妇体内酶有一定的改变,对某些药物的代谢过程有一定的影响.药物不易解...</td>
    </tr>
    <tr>
      <th>141922</th>
      <td>宝宝拉墨绿色便便是怎么回事？</td>
      <td>http://www.120ask.com/question/62747953.htm</td>
      <td>宝宝拉墨绿色便便是怎么回事？我家女儿五个月了，之前好好的，最近拉粑粑的颜色是墨绿色的，除此之...</td>
      <td>你好，这种情况可能是你家宝宝对奶粉的能力不好。但是有些正常情况下粪便也有可能是墨绿色的。比如...</td>
      <td>你好，宝宝可能是肠胃消化不良引起的，妈妈要注意饮食，少让宝宝吃油腻煎炸和过硬的食物，忌食生冷...</td>
    </tr>
    <tr>
      <th>131579</th>
      <td>治疗癫痫病的药有特效药吗</td>
      <td>http://www.120ask.com/question/72333491.htm</td>
      <td>病情描述：大哥患上癫痫病已经有很多年了，但是一直都没有治好，有时候甚至出现抽搐、吐白沫、翻白...</td>
      <td>病情分析：你好，根据您对患者病情和症状的描述，癫痫病的治疗确实比较顽固，指导意见：建议患者在...</td>
      <td>指导意见：您好，可根据癫痫发作类型选用抗癫痫药物，一旦找到可以完全控制发作的药物和剂量，就应...</td>
    </tr>
    <tr>
      <th>55615</th>
      <td>慢性肾炎年前做了肾穿刺做完就出院了快递收到报告联系</td>
      <td>http://www.120ask.com/question/72378268.htm</td>
      <td>慢性肾炎年前做了肾穿刺做完就出院了快递收到报告联系原医院建议我转院所以报告也没人帮我解答，肾...</td>
      <td>病情分析：根据你所描述的情况，慢性肾炎，经肾穿诊断为基因突变型慢性肾炎。指导意见：没有家族史...</td>
      <td>病情分析：您好朋友根据您的描述，考虑您是肾部疾病导致一系列症状。指导意见：您好朋友根据您的描...</td>
    </tr>
    <tr>
      <th>119836</th>
      <td>手淫引起的阳痿可以自己恢复吗？</td>
      <td>http://www.120ask.com/question/12269585.htm</td>
      <td>看片不勃起了,只有用手了.我戒掉手淫可以恢复吗?医生帮帮我!</td>
      <td>阳萎可以康复的,你还可以采取以下几种方法会有帮助的:1,追踪想象法:想象知自己和妻子热恋时的...</td>
      <td>你好这位朋友,你的阳痿是由于你的手淫过度引起的,但是你必须戒除手淫才可以使你的阳痿得到恢复,...</td>
    </tr>
    <tr>
      <th>29747</th>
      <td>手淫过度，会阳痿吗？</td>
      <td>http://www.120ask.com/question/37580321.htm</td>
      <td>我每天都是需要手淫我才会得到满足的，而且我也没有女朋友的，我每天都是需要手淫，我最近这几天腰...</td>
      <td>病情分析：您好！根据您的描述，不排除是频繁手淫引发的阳痿现象，而尿道炎、前列腺炎、阴茎外伤等...</td>
      <td>您好，手淫本是成年男子的一种正常的自慰方法对于身体没有什么影响，只是过频过快了就会影响健康。...</td>
    </tr>
    <tr>
      <th>94929</th>
      <td>手脚脱皮怎么治疗</td>
      <td>http://www.120ask.com/question/15117731.htm</td>
      <td>我的手脚每年春天都会开始脱皮，先是有灼热、刺痛，继而出现红色小斑点，再变成针头大白点，而后变...</td>
      <td>病情分析:维生素C注射液搽涂患处，每日2次，3天一个疗程。对皮损的恢复有较好的效果。 方法：...</td>
      <td>病情分析:你好，这个是皮脂腺分泌少导致的缺水且欠保养所致.脱皮都有季节性,多在春末及夏季炎热...</td>
    </tr>
    <tr>
      <th>152178</th>
      <td>血糖高吃什么水果</td>
      <td>http://www.120ask.com/question/12798338.htm</td>
      <td>主要症状:有时全身发热发病时间:2009化验检查结果:血糖高0.06无</td>
      <td>糖尿病饮食应注意：主张低热量,低糖,低盐,低胆固醇饮食.增加膳食纤维,维生素,微量元素摄入,...</td>
      <td>病情分析：众所周知的，糖尿病是由于身体里的血糖过高，所以糖尿病人在吃的方面特别要注意，肯定了...</td>
    </tr>
    <tr>
      <th>136651</th>
      <td>肺癌靶向药哪里购买？</td>
      <td>http://www.120ask.com/question/66425045.htm</td>
      <td>肺癌晚期用哪类靶向药效果好？在哪类可以购买？价格如何？需要医生帮助提供远程诊断:怎样才能购买...</td>
      <td>你好，靶向治疗效果不好，治疗晚期肺癌传统中药有非常独特的疗效，建议你采用传统中药虫草、猪苓、...</td>
      <td>肺癌的靶向药物主要有易瑞沙、特罗凯、凯美纳可在医院购入但价格较贵，市场上也有其他产地的仿版具...</td>
    </tr>
    <tr>
      <th>113190</th>
      <td>孕妇一周一次验血，会造成贫血吗？</td>
      <td>http://www.120ask.com/question/20797629.htm</td>
      <td>多点点，医院的医生要求一周验血一次？我想问问一周一次验血，会不会造成贫血。会不会有影响？想我...</td>
      <td>病情分析:您说问的问题很有代表性，因为很多病人只要抽血的次数多一点就会有这样的顾虑。指导意见...</td>
      <td>病情分析:一般怀孕期间没有特殊情况的话，最好一个半月左右验一次血常规，看有没有贫血。指导意见...</td>
    </tr>
    <tr>
      <th>128681</th>
      <td>请问用钢锅炒菜有危害吗</td>
      <td>http://www.120ask.com/question/34773405.htm</td>
      <td>请问用钢锅炒菜有危害吗</td>
      <td>病情分析：你好，相对来说，铁锅可能好一点，因为煮菜时可以补充一些铁元素，不锈钢锅也不错。\n...</td>
      <td>病情分析：你好，你指的是不锈钢的炒锅吧，完全没有问题的，需要这样子做的指导意见：生活方式上面...</td>
    </tr>
    <tr>
      <th>21782</th>
      <td>癫痫病到底该怎么治疗</td>
      <td>http://www.120ask.com/question/60055287.htm</td>
      <td>病情描述：我妈妈10多岁的时候头部受伤，后来变成了癫痫，就一直治疗一直发，后来也有好多年慢慢...</td>
      <td>病情分析：你好，这位朋友，你的妈妈从小因为头外伤引起的癫痫，后来经药物治疗，症状好转停药要很...</td>
      <td>癫痫是一个发作性的疾病。主要是因为脑内的神经原群过度地异常放电，癫痫发性的脑功能的障碍。这种...</td>
    </tr>
    <tr>
      <th>46113</th>
      <td>我慢性中耳炎里面特别痒</td>
      <td>http://www.120ask.com/question/67653048.htm</td>
      <td>慢性中耳炎很多年，每年都发炎流脓和疼痛，但是会自然好。从去年就痛了不会好，又痒又痛，流脓流水...</td>
      <td>病情分析：你好，是中耳炎引起的症状；你可以服用龙胆泻肝丸，用双氧水清洗耳后指导意见：用左氧氟...</td>
      <td>病情分析：中耳炎一般是受到细菌的刺激，导致出现炎症反应，彩出现不舒服的情况。指导意见：平时注...</td>
    </tr>
    <tr>
      <th>54437</th>
      <td>请问：婴儿大便次数少怎么办？</td>
      <td>http://www.120ask.com/question/1631300.htm</td>
      <td>请问医生:我家宝宝已经五天没有大便了，平时一到两天一次大便，大便呈金黄色，粘稠，吃奶也挺好，...</td>
      <td>你宝宝如果是喝母乳的话,要从母亲的饮食里找原因,如果母亲食用过多的热性食物,同时少吃蔬菜少喝...</td>
      <td>我家宝宝在几个月的时候也是这种情况,记的有一次也是一个星期没大便,不过也没治疗,现在孩子两岁...</td>
    </tr>
  </tbody>
</table>
</div>


