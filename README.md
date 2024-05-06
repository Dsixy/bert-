# bert-
自然语言处理pj
用于Doney来存储PJ的生产过程

# 任务目标：
电信诈骗分类

# 思路：
使用bert-chinese-base预训练模型作为基线
## 具体model可以使用hugging_face上的开源bert模型

No1使用了MLM预训练+FreeLB对抗训练+多模型融合

## 目前思路为：
1.	采用现成大语言模型bert-chinese-base
2.	使用MLM做领域内自回归模型做预训练（这个需要网上找一些电信诈骗之类的文本，用于做领域内学习）
3.	用output_embedding用triplet_loss之类的pair做训练
4.	使用softmax做最后微调
对于训练数据要做一些处理，比如将原有脱敏数据去掉的地方换成<mask>之类的。但是要额外产生一些embedding，可能反而适得其反
