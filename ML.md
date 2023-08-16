# 1. 赛题概览
### 1.1 介绍
本次大赛提供了讯飞开放平台海量的应用数据作为训练样本，参赛选手需要基于提供的样本构建模型，预测用户的新增情况。

### 1.2 数据集
赛题数据由约62万条训练集、20万条测试集数据组成，共包含13个字段。其中uuid为样本唯一标识，eid为访问行为ID，udmap为行为属性，其中的key1到key9表示不同的行为属性，如项目名、项目id等相关字段，common_ts为应用访问记录发生时间（毫秒时间戳），其余字段x1至x8为用户相关的属性，为匿名处理字段。target字段为预测目标，即是否为新增用户。

### 1.3 评分指标
本次竞赛的评价标准采用f1_score，分数越高，效果越好<br>
f1_score介绍 : https://blog.csdn.net/qq_14997473/article/details/82684300

# 2. 任务一
### 2.1 选择模型















