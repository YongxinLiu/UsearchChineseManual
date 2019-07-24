# USEARCH —— 最简单易学的扩增子分析流程

USEARCH中文帮助文档(USEARCH Chinese manual)

![image](http://www.drive5.com/banner/usearch_home.jpg)

USEARCH官方英文主页：http://www.drive5.com/usearch/

本站经USEARCH作者Robert Edgar授权，由《宏基因组》公众号翻译的中文帮助文档和系列教程。


## USEARCH简介

USEARCH是最好用的扩增子分析流程，在体积仅1 MB的软件中实现了近200种扩增子分析常用功能，安装方便且运行速度快。截止19年7月24日，[Google学术统计引用9,835次](https://scholar.google.com/citations?user=RzVMRc0AAAAJ&hl=en)。

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

- 微信：yongxinliu

- 电话：13810163414

## 参考文献

1. Edgar RC: Search and clustering orders of magnitude faster than BLAST. Bioinformatics 2010, 26:2460-2461.
2. Edgar RC, Haas BJ, Clemente JC, Quince C, Knight R: UCHIME improves sensitivity and speed of chimera detection. Bioinformatics 2011, 27:2194-2200.
3. Edgar RC: UPARSE: highly accurate OTU sequences from microbial amplicon reads. Nature Methods 2013, 10:996.
4. Edgar RC, Flyvbjerg H: Error filtering, pair assembly and error correction for next-generation sequencing reads. Bioinformatics 2015, 31:3476-3482.
5. Callahan BJ, McMurdie PJ, Rosen MJ, Han AW, Johnson AJA, Holmes SP: DADA2: High-resolution sample inference from Illumina amplicon data. Nature Methods 2016, 13:581.
6. Amir A, McDonald D, Navas-Molina JA, Kopylova E, Morton JT, Zech Xu Z, Kightley EP, Thompson LR, Hyde ER, Gonzalez A, et al.: Deblur rapidly resolves single-nucleotide community sequence patterns. mSystems 2017, 2:e00191-00116.

