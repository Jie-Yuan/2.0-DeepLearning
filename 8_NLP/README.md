<h1 align = "center">:rocket: 自然语言处理 :facepunch:</h1>

---
colibricore

https://mp.weixin.qq.com/s/_cViS49o6iZgwgbxJqti0Q

https://github.com/Jie-Yuan/finch

https://github.com/crownpku/awesome-chinese-nlp

http://ai.baidu.com/tech/nlp

http://web.stanford.edu/class/cs224n/syllabus.html

抽取三元组
https://github.com/twjiang/fact_triple_extraction

https://github.com/Jie-Yuan/Information-Extraction-Chinese

https://mp.weixin.qq.com/s?__biz=MzU2NjAxNDYwMg==&mid=2247484322&idx=1&sn=3c7e70bd80ed74a3fa71438dc33656a1&chksm=fcb3a447cbc42d51e2d2849875b67cb946c36a32d566102f0bbf19477f3c22d30d3036d8cd1c&scene=0#rd
## 1. 分词
> 最大匹配/最少词数/概率最大/统计语言模型
- 歧义
  - 交集型歧义
  - 组合型歧义
- 未登录词（新词）

统计语言模型：对于任意两个词语 w1 、 w2 ，统计在语料库中词语 w1 后面恰好是 w2 的概率 P(w1, w2) 。这样便会生成一个很大的二维表。再定义一个句子的划分方案的得分为 P(∅, w1) · P(w1, w2) · … · P(wn-1, wn) ，其中 w1, w2, …, wn 依次表示分出的词。我们同样可以利用[动态规划][21]求出得分最高的分词方案。这真是一个天才的模型，这个模型一并解决了词类标注、语音识别等各类自然语言处理问题。至此，中文自动分词算是有了一个漂亮而实用的算法。

## 2. 标注
- 标注
    - b（核心实体首词）
    - m（核心实体中）
    - e（核心实体末词）
    - s（单词成核心实体）
    - x（非核心实体部分）
  
- 隐马尔科夫模型（HMM）
- 最大熵模型（ME）
- 条件随机场模型（CRF）




---
## [Word2Vec][1]
- Skip-Gram: 从一个文字来预测上下文
- Bag-of-Words(CBOW): 从上下文来预测一个文字
## [GloVe][2]
## WordRank


## [fastText][4]
- [Pre-trained word vectors][41]
- https://github.com/facebookresearch/fastText
- https://github.com/salestock/fastText.py
---
## 工具
### [spaCy][61]
### [easyEmbed][62]
### [ShallowLearn][63]
### [ngram2vec][64]
### [glove-python][65]: http://www.foldl.me/2014/glove-python/
### [flashtext][66]: 比正则快http://dwz.cn/6YUkG7
### [Synonyms][67]
### Pinyin2Hanzi: 拼音转汉字
### [snownlp][5]: 情感分析
### jieba: 分词
### TextGrocery: 文本分类
### [preprocessing][68]: 字符串预处理
### foolnltk
### rake-nltk
### textblob

---
## 组织
- THUNLP
- FudanNLP


---
[1]: x
[2]: http://blog.csdn.net/sinat_26917383/article/details/54847240

[21]: http://blog.csdn.net/xgf415/article/details/52662389

[4]: http://www.jianshu.com/p/b7ede4e842f1
[5]: https://github.com/isnowfy/snownlp
[41]: https://github.com/facebookresearch/fastText/blob/master/pretrained-vectors.md

[61]: https://github.com/explosion/spaCy
[62]: https://github.com/yanaiela/easyEmbed
[63]: https://github.com/giacbrd/ShallowLearn
[64]: https://github.com/zhezhaoa/ngram2vec
[65]: https://github.com/maciejkula/glove-python
[66]: https://github.com/vi3k6i5/flashtext
[67]: https://github.com/huyingxi/Synonyms
[68]: https://github.com/SpotlightData/preprocessing
