
$a_t$

###### 2020/3/1
| No. | Theme | Date | Title | Summary |  
| :-: | :-: | :-: | :-: | :-: |
1 | Fact Verification | 2020 | Fine-grained Fact Verification with kernel Graph Attention Network| 主要提出了KGAT模型，模型主要分为Evidence Reasoning和Evidence Selection。Graph中node由claim和evidence合成的pair，edge用与propagate node间的information。其中**Evidence Reasoning**部分：先用BERT求得初始的node representation，再用kernel Attention融合node间的关系得到最终的representation(v^p);**Evidence Selection**部分：先用claim和evidence计算一个translation matrix，从矩阵中使用kernel提取soft match feature求得Φ作为selection representation,再由此求得最终的P|
2 | Fact Verification | 2018 | FEVER:a large-scale dataset for Fact Extraction and VERification| 读这篇是想了解一下前一篇中的数据集的特点和难度所在，没有读得很细，（目前个人）感觉这篇文章中好多东西只是表明数据集建立过程的严谨、科学、可行性高等。之前的数据集一般较小，且存在机器可读性差，对于SUPPORTED、REFUTED类型没有返回evidence，种类有限等问题。FEVER与QA相关，但QA一般提供了确定答案所需要的信息，而FEVER做REFUTE需要找到缺失的信息，检索相关的evidence；与TE和NLI相比，验证claim的evidence要从document中retrieve确定的sentence。数据集的建立包括两个阶段：Claim Generation和Labelling，还包括注释和证实等task。最后进行了几项在该数据集上的task测试。其中的一些例子还是很有趣，比如其中一个关于贝克汉姆在曼联的claim，用于support的evidence提取出来是他在曼联进行了处子秀，但这个evidence其实是不够充分的，另外“曼联”也是个多义词，需要对一些航空公司等有关的信息进行筛选。主要收获就是对这部分工作有了更具体的理解，也增加了兴趣。|
3 | Ranking | 2017 | End-to-End Neural Ad-hoc Ranking with Kernel Pooling | 因为在读第一篇文章的时候，对kernel pooling，translation matrix以及提到的soft match理解的还是不够清楚，就读了这篇文章。模型结构和图示可以说相当清晰，首先将Query和Document words转换为distributed representations,然后使用Translation Matrix对所有的word进行了similarity描述，在此之上进行kernel pooling提取feature，取对数生成soft-TF特征，再用tanh函数结合linear层得到ranking score进行排序。 |
4 | Ranking | 2018 | Convolutioinal Neural Networks for Soft-Matching N-Grams in Ad-hoc Search | 在上一篇文章的阅读过程中就想到过，之前我学习到的pooling是在CNN中，先利用卷积提取高维特征，再pooling，有利于减少模型的参数数量。在K-NRM中，是利用kernel pooling summarize similarity特征。但生成Matrix的过程有点单一，感觉不能像CNN中的卷积一样提取更细致的特征和关联。而Cov-KNRM则正是在这一点进行了提升，增加了卷积生成n-gram representation的层次，提取了含义更加丰富的特征。 |
5 | Ranking | 2019 | Content-Based Weak Supervision for Ad-hoc Re-Ranking | 看年份觉得比前面两篇应该有提高，想了解一下更先进的方法。但确实没有读懂。对于伪相关(pseudo-relevant)和BM25可能还要再读一些了解一下才行。也可能因为文章里没有图，对方法的结构没有明确的了解吧。主要方法就是两种source的无监督学习，然后使用滤波器进行滤波。 |
