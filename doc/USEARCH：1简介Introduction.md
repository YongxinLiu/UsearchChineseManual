[TOC]

![image](http://bailab.genetics.ac.cn/markdown/usearch/fig/usearch_home.png)

USEARCH官方英文主页：http://www.drive5.com/usearch/

本站经USEARCH作者Robert Edgar授权，由《宏基因组》公众号翻译的中文帮助文档和系列教程。

## USEARCH简介

USEARCH是最好用的扩增子分析流程，在体积仅1 MB的软件中实现了近200种扩增子分析常用功能，安装方便且运行速度快。截止19年8月30日，[Google学术统计引用10,056次](https://scholar.google.com/citations?user=RzVMRc0AAAAJ&hl=en)。

USEARCH作者是Robert Edgar独立研究员(Independent Investigator)在本领域开发了一系列经典算法和软件，如扩增子分析流程USEARCH[1]、嵌合体检测软件UCHIME[2]、OTU聚类和代表性序列鉴定算法UPARSE[3]、和测序数据错误过滤和校正的去噪算法UNOISE[4]等。这些新算法和软件的推出，极大的提高了扩增子数据分析的速度和准确度。USEARCH不仅分析速度快，而且软件可用性强，可有效降低入门学习成本并节约宝贵时间。

进一步阅读，欢迎点击下方链接，阅读宏基因组公众号关于USEARCH的历史文章。

- [扩增子分析神器USEARCH简介](http://mp.weixin.qq.com/s/oJDfShs7gXCkOzYfa_winQ)
- [USEARCH v11新功能介绍](https://mp.weixin.qq.com/s/QH9nfISLEhSeem3eyUDRFQ) 
- [USEARCH最新版v11命令大全](https://mp.weixin.qq.com/s/x0_cuEpldcl4KDvqPLm8yw) 
- [OTU表抽平otutab_rare](https://mp.weixin.qq.com/s/5gCzizOwfl2kme7TxWjz4Q) 
- [核心OTU鉴定otutab_core](https://mp.weixin.qq.com/s/48QqyY5pRW2WZn_gnOX0Xg)

### USEARCH的优点

- 体积小巧：QIIME系统软件大小上G，而USEARCH只有1M的大小完成了市面上的大多数分析功能；
- 安装方便：软件无依赖关系，下载后添加环境变量即可运行；
- 运行速度快：R语言在大数据面前太低效，USEARCH采用C编写，数据处理速度为R的20倍。鉴定ASV的核心算法UNOISE3也比主流软件DADA2[5]快100倍，delbur快10倍以上[6]，详见 [主流非聚类方法dada2,deblur和unoise3介绍与比较](http://mp.weixin.qq.com/s/hU4AavhMQcebNhBtMUg1tw)；
- 跨平台：绝大多数软件只能在Linux上运行。USEARCH支持三大主流操作系统，不仅在Linux服务上跑的溜，而且在你的Windows/Mac笔记本上也可以轻松分析多达上千个样本的扩增子大数据。

## 软件下载

### 32位版软件下载

32位版USEARCH对个人用户免费下载，请访问以下地址自助免费申请

http://www.drive5.com/usearch/download.html

### 专业版购买

USEARCH 64位版，分为商业版和学术版(需要提供学术邮箱)。

- 商业版，原价$1,485美刀(~￥10,208元)，现价10,000元，可开发票(不含税)
- 学术版，原价$885美刀(~￥6,083元)，现价6,000元，可开发票(不含税)

软件支持Linux / Mac OSX / Windows三大主流系统，可任选自己常用工作环境。

通过中文站购买专业版，即可享受价格优惠，又方便开发票单位报销，同时享受中文专业技术VIP群交流资格和获得专业解答。

### 联系方式

- 邮箱：宏基因组公众号 metagenome@126.com

- 微信：meta-genomics

- 电话：17001263056


## v11新功能

就在2018年7月末，USEARCH(Ultra-fast sequence analysis)扩增子分析神器迎来了其第11个大版本，

具体有哪些新功能呢？

详见此页：

http://www.drive5.com/usearch/manual/whatsnewv11.html

主要新增了6大新功能，21个新命令，下面进行简介。

### 新特征

- 机器学习：主要包括随机森林、多次交叉验证、OTU分类重要性，包括的命令有森林训练、森林分类和森林交叉验证

![image](http://bailab.genetics.ac.cn/markdown/soft/usearch/classifier.gif)

- 改进嵌合体检测
- 新增了两种Alpha多样性指数： Mirror estimator、 Singleton-free (FE) estimator
- Octave plot(八度图)展示Alpha多样性，方便观察样本品中真实序列、测序错误和嵌合体数量

![image](http://bailab.genetics.ac.cn/markdown/soft/usearch/octave_yow.gif)
- 样品组间多样性比较

![image](http://bailab.genetics.ac.cn/markdown/soft/usearch/charlie.jpg)

- 同一性交驻验证特征预测的准确率

![image](http://bailab.genetics.ac.cn/markdown/soft/usearch/cvi.gif)

### 新命令

1. calc_lcr_probs: Calculate lowest common rank probabilities 计算序列物种分类各级概率
1. cluster_tree: Construct clusters from tree using distance cutoff 基于树文件聚类
1. distmx_split_identity: Split distance matrix into test/training pair for CVI 拆分距离矩阵为测试和训练集
1. fastx_syncpairs: Sort forward and reverse reads into the same order 双端序列找成队并排序
1. fastx_trim_primer: Remove primer-binding sequence from FASTx file 引物匹配并切除
1. forest_classify: Classify data using random forest 随机森林分类预测
1. forest_train: Train random forest classifier 随机森林分类器建立
1. nbc_tax: Predict taxonomy using RDP Naive Bayesian Classifier algorithm 采用RDP算法预测分类学物种注释
1. otutab_binary: Convert OTU table with counts to presence(1) / absence(0) 转换OTU表为二元(有、无)形式
1. otutab_forest_classify: Classify samples using random forest 样品随机森林分类
1. otutab_core: Identify core microbiome in OTU table 鉴定OTU表中核心微生物组
1. otutab_forest_train: Train random forest classifier on OTU table 基于OTU表的随机森林训练
1. otutab_otus: Extract OTU labels from OTU table 提取OTU表中的OTUs
1. otutab_rare: Sub-sample OTU table to same number of reads per sample 抽样标准化OTU表
1. otutab_samples: Extract sample labels from OTU table 提取OTUs表中样品名
1. otutab_select: Identify OTUs which are informative (correlate with metadata) 鉴定更有信息的OTUs,，即组间差异OTUs
1. otutab_xtalk: Identify cross-talk using improved algorithm (UNCROSS2) 改进算法鉴定嵌合
1. search_pcr2: In-silico PCR, search for matches to primer pair 电子PCR，基于引物匹配扩增区
1. subtree: Extracts subtree under given node 提取树中指定结点的子树
1. tabbed2otutab: Convert read mapping file (read+OTU) to OTU table 单行表格转换为OTU表
1. tree_subset: Extract subset of tree for given set of leaf labels 根据树叶标签提取子集


## 译者简介

**刘永鑫**，博士。2008年毕业于东北农大微生物学，2014年于中科院遗传发育所获生物信息学博士，2016年博士后出站留所工作，任宏基因组学实验室工程师。目前主要研究方向为宏基因组数据分析和植物微生物组，QIIME 2项目参与人。目前在***Science、Nature Biotechnology***等杂志发表论文十余篇。2017年7月创办“宏基因组”公众号，目前分享宏基因组、扩增子原创文章400余篇，代表博文有[《扩增子图表解读、分析流程和统计绘图三部曲(21篇)》](https://mp.weixin.qq.com/s/u7PQn2ilsgmA6Ayu-oP1tw)、[《Nature综述：手把手教你分析菌群数据(1.8万字)》](https://mp.weixin.qq.com/s/F8Anj9djawaFEUQKkdE1lg)、[《QIIME2中文教程(18篇)》](https://mp.weixin.qq.com/s/IZLjdkRq2-36DJ9X792_MA)等，关注人数5.6万+，累计阅读900万+。

## 猜你喜欢

- 10000+: [菌群分析](https://mp.weixin.qq.com/s/F8Anj9djawaFEUQKkdE1lg)  
[宝宝与猫狗](http://mp.weixin.qq.com/s/K3y3an-EaX8iaytmxdzHqA) [提DNA发Nature](http://mp.weixin.qq.com/s/lO5uiMjixJ6aYTjPX-IyaQ) [实验分析谁对结果影响大](http://mp.weixin.qq.com/s/cL_IAoPFfmelKMPMgltrfA)  [Cell微生物专刊](https://mp.weixin.qq.com/s/fN0gpD3bZJDXSp8x4ck-3Q) [肠道指挥大脑](https://mp.weixin.qq.com/s/pZO20VGl3Tf_OtFIbZ-zWw)
- 系列教程：[微生物组入门](http://mp.weixin.qq.com/s/sQyl5EctXFB95Oxg8YIasg) [Biostar](http://mp.weixin.qq.com/s/JL-n2nD6YL8vwuRtTVmQlQ) [微生物组](http://mp.weixin.qq.com/s/li7SdZVaCEyFQF8h6MMh2A)  [宏基因组](http://mp.weixin.qq.com/s/bcyvhFrNr6niqD13rQfZeg) 
- 专业技能：[生信宝典](http://mp.weixin.qq.com/s/2b3_8Vvv7McqCkEfUszW3A) [学术图表](http://mp.weixin.qq.com/s/SCT4oso_vI0UNIJZTaG95g) [高分文章](http://mp.weixin.qq.com/s/kD-x7K4hI5KMgGXikyLt0Q) [不可或缺的人](http://mp.weixin.qq.com/s/1nf7vwyvC3oemkTq_pu87A) 
- 一文读懂：[宏基因组](http://mp.weixin.qq.com/s/Vsm6BJgqsSvxEenIBrGVLw) [寄生虫益处](https://mp.weixin.qq.com/s/hX0K9TOLPnrZ6f8lUoSYag) [进化树](https://mp.weixin.qq.com/s/GV8rU3FZdc8Y-x931k_yrQ)
- 必备技能：[提问](http://mp.weixin.qq.com/s/xCif04bqZB14Z4OvesK0SQ) [搜索](http://mp.weixin.qq.com/s/wn2bqIPgT5UD-GP1qzkJFA)  [Endnote](http://mp.weixin.qq.com/s/SPblPs5ByPdb2C400kIK3w)
- 文献阅读 [热心肠](http://mp.weixin.qq.com/s/1uBeAQ0utxuzTTtfUx_UXA) [SemanticScholar](https://mp.weixin.qq.com/s/gaQiUrRqLpfTXzjyfbua6A) [Geenmedical](https://mp.weixin.qq.com/s/hc8g64aHN7qv8YhVfrsuvQ)
- 扩增子分析：[图表解读](http://mp.weixin.qq.com/s/oiVHO2S1JgYrKXPDU6fH2g) [分析流程](http://mp.weixin.qq.com/s/KrYyy3jjzAL0rQzVfV6h4A) [统计绘图](http://mp.weixin.qq.com/s/6tNePiaDsPPzEBZjiCXIRg) 
- [16S功能预测](http://mp.weixin.qq.com/s/sztbvfdf9wa-3HJXc_m8TQ)   [PICRUSt](https://mp.weixin.qq.com/s/LWtiwBbUCAadMZPaKKDMag)  [FAPROTAX](http://mp.weixin.qq.com/s/J8EwJD_PTDhqRaD7kXlK1A)  [Bugbase](https://mp.weixin.qq.com/s/1WdysPZWo0H6NSYiNpcMUQ) [Tax4Fun](http://mp.weixin.qq.com/s/dzsh44ue93xnAs7gTde7wg)
- 在线工具：[16S预测培养基](http://mp.weixin.qq.com/s/YIrDqNvDX0XMazCGxhH1Lg) [生信绘图](http://mp.weixin.qq.com/s/O0QAQyfxnrXlFLw268B7lg)
- 科研经验：[云笔记](http://mp.weixin.qq.com/s/OnwhWlq3cTycf-W1rxgV7g)  [云协作](http://mp.weixin.qq.com/s/W5By9mZ5PI57_xFfZ_JXiw) [公众号](http://mp.weixin.qq.com/s/hd0sdBDAMqMJsXQs0pIjUg)
- 编程模板: [Shell](http://mp.weixin.qq.com/s/YevGR79NnBAF-xtrqL8gAA)  [R](http://mp.weixin.qq.com/s/OQiE882jM6pVwqTiIjyZ1Q) [Perl](http://mp.weixin.qq.com/s/u2ZmTo-z6cbN-L6KVLYNwg) 
- 生物科普: [肠道细菌](http://mp.weixin.qq.com/s/3T768LA6MWujF4yuzK4MKQ) [人体上的生命](http://mp.weixin.qq.com/s/_DUI6tOYTEq0Wu7K7iRTxw) [生命大跃进](http://mp.weixin.qq.com/s/O_0Il0G_v_aSwkUH_noZVA)  [细胞暗战](http://mp.weixin.qq.com/s/M35ebWAelDIK5Iqib06JzA) [人体奥秘](https://mp.weixin.qq.com/s/xlCdN8il1hcutkYK-42fAQ)  


## 写在后面

为鼓励读者交流、快速解决科研困难，我们建立了“宏基因组”专业讨论群，目前己有国内外5000+ 一线科研人员加入。参与讨论，获得专业解答，欢迎分享此文至朋友圈，并扫码加主编好友带你入群，务必备注“姓名-单位-研究方向-职称/年级”。技术问题寻求帮助，首先阅读[《如何优雅的提问》](http://mp.weixin.qq.com/s/H9gkepap0hy3NNskOkO44w)学习解决问题思路，仍末解决群内讨论，问题不私聊，帮助同行。
![image](http://bailab.genetics.ac.cn/markdown/life/yongxinliu.jpg)

学习扩增子、宏基因组科研思路和分析实战，关注“宏基因组”
![image](http://bailab.genetics.ac.cn/markdown/life/metagenome.jpg)

![image](http://bailab.genetics.ac.cn/markdown/train/1809/201807.jpg)

点击阅读原文，跳转最新文章目录阅读
https://mp.weixin.qq.com/s/5jQspEvH5_4Xmart22gjMA