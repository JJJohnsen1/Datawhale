# 1 机器学习
## 1.1 特征提取
### *TF-IDF(term frequency–inverse document frequency)
 TF-IDF有两层意思，一层是"词频"（Term Frequency，缩写为TF），另一层是"逆文档频率"（Inverse Document Frequency，缩写为IDF）。
 $$TF(词频）= \frac{某个词在文档中出现的次数}{文档的总词数}$$
 $$IDF(逆文档频率）= log\frac{语料库文档总数}{出现该词的文档数+1}$$ 原教程没有加1，而如果一个词越常见，那么分母就越大，逆文档频率就越小越接近0。分母之所以要加1，是为了避免分母为0（即所有文档都不包含该词）。log表示对得到的值取对数。
 $$TF-IDF= TF×IDF$$可以看到，TF-IDF与一个词在文档中的出现次数成正比，与该词在整个语言中的出现次数成反比。所以，自动提取关键词的算法就很清楚了，就是计算出文档的每个词的TF-IDF值，然后按降序排列，取排在最前面的几个词。
### *BOW(bags of words)
BOW（Bag of Words）是一种常用的文本表示方法，其基本思想是假定对于一个文本，忽略其词序和语法、句法，仅仅将其看做是一些词汇的集合，而文本中的每个词汇都是独立的。简单说就是讲每篇文档都看成一个袋子（因为里面装的都是词汇，所以称为词袋，Bag of words即因此而来），然后看这个袋子里装的都是些什么词汇，将其分类。具体而言，词袋模型表示一个文本，首先会维护一个词库，词库里维护了每一个词到一个数值向量的映射关系。例如，最简单的映射关系是独热编码，假设词库里一共有四个词，今天、天气、很、不好，那么独热编码会将四个词分别编码为：
今天——（1,0,0,0）
天气——（0,1,0,0）
很   ——（0,0,1,0）
不好——（0,0,0,1）
而使用词袋模型，就会将上述这句话编码为：
  
  $$BOW(Sentence）= 
Embedding(今天) + Embedding(天气) + Embedding(很) + Embedding(不好) 
= (1,1,1,1）$$

### *停用词
停用词(Stop Words)是自然语言处理领域的一个重要工具，通常被用来提升文本特征的质量，或者降低文本特征的维度。<br>
详细介绍 ：https://zhuanlan.zhihu.com/p/335347401

# 2 深度学习
## 2.1 embedding 嵌入层
在学习RNN、Transformer和Bert算法模型中，我注意到数据进入encoder前都要先进入embedding层，再将输出数据输入encoder。那么Embedding层到底发挥了什么作用呢？<br>

在了解Embedding层之前，我们首先要学习**one-hot**。

当下，我们学习的模型的输入都只能为数字。每个输入的字母，单词甚至句子，都将对应为数字以便能够成为模型的输入。

**one-hot** 以我的理解来说就是一个字典，每个字（输入）给它赋予独一无二的一个编号。

最终，任何输入都可以构成一个稀疏矩阵。而在这时由于稀疏矩阵的特点，占用计算资源十分过度。于是，我们可以利用Embedding层将该稀疏矩阵进行**降维**，这样可以大大减少运算资源。

而在Bert中，Embedding层由TokingEmbedidng+segementEmbedding+positionEmbedding组成。

详细介绍 ：https://zhuanlan.zhihu.com/p/164502624

## 2.2 Encoder
Bert的Encoder和Transforms的Encoder一模一样，在此不做过多介绍。

详细介绍 ：https://zhuanlan.zhihu.com/p/338817680
# 3 大模型
