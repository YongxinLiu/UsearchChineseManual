# USEARCH —— 最简单易学的扩增子分析流程

USEARCH中文帮助文档(USEARCH Chinese manual)

![image](http://www.drive5.com/banner/usearch_home.jpg)

USEARCH官方英文主页：http://www.drive5.com/usearch/

本站经USEARCH作者Robert Edgar授权，由《宏基因组》公众号翻译的中文帮助文档和系列教程。

所有软件版本的下载链接：https://github.com/rcedgar/usearch_old_binaries/，备用下载链接见"软件下载"

## USEARCH简介

USEARCH是最好用的扩增子分析流程，在体积仅1 MB的软件中实现了近200种扩增子分析常用功能，安装方便且运行速度快。截止24年8月1日，[Google学术统计引用20960次](https://scholar.google.com/citations?user=RzVMRc0AAAAJ&hl=en)。

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

`0afb1df880a0bf3933d2ded3e2d33d16` [usearch11.0.667_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch11.0.667_i86linux32)   
`fa050a3029d33b7b25036a2cc8c6da97` [usearch11.0.667_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch11.0.667_i86linux64)   
`f91fa82a9cb7dab629c2906884b20558` [usearch11.0.667_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch11.0.667_i86osx32)   
`9d3d2cf73deb1880976643e5abfe371d` [usearch11.0.667_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch11.0.667_i86osx64)   
`6eeac51da9576dd240cd08e4662b5bbf` [usearch11.0.667_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch11.0.667_win32.exe)   
`d7ffd84f5d2aed3ad9ce2fb75a3e8ea6` [usearch11.0.667_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch11.0.667_win64.exe)   

`64841bcb4d473f0428084d15446e6dfc` [usearch10.0.240_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.240_i86linux32)   
`e4bcddca49a248b1721b4f68804e0197` [usearch10.0.240_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.240_i86linux64)   
`321e0ba7ed7f639218c3829771cb66ae` [usearch10.0.240_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.240_i86osx32)   
`8c9c5b32e55bfbe6b0b11210d05da5ff` [usearch10.0.240_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.240_i86osx64)   
`b64097fb8be15a926f6e495d078d7f0f` [usearch10.0.240_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.240_win32.exe)   
`fe9294ae277d1bf4b5ce8d63cce80540` [usearch10.0.240_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.240_win64.exe)   
`662ac854622d3ba3e632fa8a3b959cdd` [usearch10.0.259_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.259_i86linux32)   
`d610820e32c95c9a8bc70957d33f6ee4` [usearch10.0.259_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch10.0.259_i86linux64)   

`9bf24886a17010c3f8d454a0e6896d63` [usearch9.2.64_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.2.64_i86linux32)   
`8bcb11d7044c4dfdd3c57a57f936248c` [usearch9.2.64_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.2.64_i86linux64)   
`5fe9d522d11f96471fa28c36f5a6f8f4` [usearch9.2.64_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.2.64_i86osx32)   
`65651d7faac1bf9342974f888c6ad928` [usearch9.2.64_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.2.64_i86osx64)   
`b458785cc7c11f072a914950e31f4605` [usearch9.2.64_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.2.64_win32.exe)   
`83cdfea44929518114e41f566f13737c` [usearch9.2.64_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.2.64_win64.exe)   

`ecec88a87ec0786d52de5624d2a78582` [usearch9.1.13_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.1.13_i86linux32)   
`c17e2ae0a94bcfd57951195321f74917` [usearch9.1.13_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.1.13_i86linux64)   
`bdbf3124fcbfba484d83272304d25dce` [usearch9.1.13_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.1.13_i86osx32)   
`f407db9658955770394ba928c130ed4a` [usearch9.1.13_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.1.13_i86osx64)   
`69974a162e9e4428d6d246dfeb19e3ac` [usearch9.1.13_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.1.13_win32.exe)   
`ae56f2497058891d865dd185e8df814c` [usearch9.1.13_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.1.13_win64.exe)   

`660e59902b583815a14293b9d8ccd5c1` [usearch9.0.2132_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.0.2132_i86linux32)   
`098d0d79f22eb1d4951c7d04bbe77cb3` [usearch9.0.2132_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.0.2132_i86linux64)   
`52066e3e1a32ea4730b2c3edc52cd42b` [usearch9.0.2132_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.0.2132_i86osx32)   
`62e601d76411b9a6eb444e0b39c42de3` [usearch9.0.2132_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.0.2132_i86osx64)   
`f08c8593b1fea583a52d7278c18dfdc0` [usearch9.0.2132_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.0.2132_win32.exe)   
`091c7c95a892710fe424f6705caaf50d` [usearch9.0.2132_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch9.0.2132_win64.exe)   

`1fc7b91bad6eba3518d719e74d018007` [usearch8.1.1861_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.1.1861_i86linux32)   
`92918968647fbf5fa19137b9b0e81e40` [usearch8.1.1861_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.1.1861_i86linux64)   
`683cca4bcde4a6cda7fd2d2e350c14eb` [usearch8.1.1861_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.1.1861_i86osx32)   
`a05d8bc8c2587582f3f4a0f3e01f71c2` [usearch8.1.1861_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.1.1861_i86osx64)   
`46a11d3c0033da314e21be048319c0a3` [usearch8.1.1861_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.1.1861_win32.exe)   
`b415b1beb35cdc1075c6fd17cc3ea279` [usearch8.1.1861_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.1.1861_win64.exe)   

`4e6cc08aeec659429eaca001048ce118` [usearch8.0.1623_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.0.1623_i86linux32)   
`ec74da76901b294d985618d1d4d5f3a1` [usearch8.0.1623_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.0.1623_i86linux64)   
`d32063e05dfc4539e11b92aa3b659be5` [usearch8.0.1623_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.0.1623_i86osx32)   
`5e79e05964e9a6f9d643f59ce735f138` [usearch8.0.1623_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.0.1623_i86osx64)   
`5545c39059cd8866c64d7cd9faf171cf` [usearch8.0.1623_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.0.1623_win32.exe)   
`880edaddd81dfe34f460f35d3a421903` [usearch8.0.1623_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch8.0.1623_win64.exe)   

`63a4cb03f15d73d1eace358f06e6abd8` [usearch7.0.1090_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch7.0.1090_i86linux32)   
`b8b7a28c9529c209efebe2ca0c5c7154` [usearch7.0.1090_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch7.0.1090_i86linux64)   
`d4f1c15f268514c731b93a94518c284a` [usearch7.0.1090_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch7.0.1090_i86osx32)   
`8f79492d1c250139192650577b75393b` [usearch7.0.1090_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch7.0.1090_i86osx64)   
`9aa6fa87aadb513a529d70bddf2be5bc` [usearch7.0.1090_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch7.0.1090_win32.exe)   
`02c1699e4667615d69261eb24bd91173` [usearch7.0.1090_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch7.0.1090_win64.exe)   

`6eed4cd3cc523fc07794ab2d2b36350d` [usearch6.1.544_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch6.1.544_i86linux32)   
`d248e220dd179e7248214a708d124a58` [usearch6.1.544_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch6.1.544_i86linux64)   
`05a5cabd635200099cef58217aa96716` [usearch6.1.544_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch6.1.544_i86osx32)   
`6bd41183b03d0d0c711282bfb91146a7` [usearch6.1.544_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch6.1.544_i86osx64)   
`d4ff4ca3837b9eff8275efa3fe1b39ae` [usearch6.1.544_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch6.1.544_win32.exe)   

`74b92294c50d03cc3c3ad19c49d38f19` [usearch5.2.236_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.236_i86linux32)   
`28996779d458c5433a9e03030a8dae8c` [usearch5.2.236_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.236_i86linux64)   
`34a58b517456feb60338d144d46e6772` [usearch5.2.236_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.236_i86osx32)   
`90b44c3f6dcf3e04e114fddec5b110f5` [usearch5.2.236_i86osx64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.236_i86osx64)   
`14dee3a4aadd4b59fa25d64ec9ce329e` [usearch5.2.236_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.236_win32.exe)   
`00982a1bf0ab98f10d5b3baadc685a87` [usearch5.2.236_win64.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.236_win64.exe)   

`3ccbc951f78b8cc20494a01b9da70ec1` [usearch5.2.32_i86linux32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.32_i86linux32)   
`50b5c4eb53f50809dbc58cde4890497c` [usearch5.2.32_i86linux64](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.32_i86linux64)   
`92d4d1d92c5dd73dd5f78270b38aed8b` [usearch5.2.32_i86osx32](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.32_i86osx32)   
`914e50543d44f8df8ecc1d855baa35a6` [usearch5.2.32_win32.exe](http://www.imeta.science/github/UsearchChineseManual/bin/usearch5.2.32_win32.exe)   


## 参考文献

1. Edgar RC: Search and clustering orders of magnitude faster than BLAST. Bioinformatics 2010, 26:2460-2461.
2. Edgar RC, Haas BJ, Clemente JC, Quince C, Knight R: UCHIME improves sensitivity and speed of chimera detection. Bioinformatics 2011, 27:2194-2200.
3. Edgar RC: UPARSE: highly accurate OTU sequences from microbial amplicon reads. Nature Methods 2013, 10:996.
4. Edgar RC, Flyvbjerg H: Error filtering, pair assembly and error correction for next-generation sequencing reads. Bioinformatics 2015, 31:3476-3482.
5. Callahan BJ, McMurdie PJ, Rosen MJ, Han AW, Johnson AJA, Holmes SP: DADA2: High-resolution sample inference from Illumina amplicon data. Nature Methods 2016, 13:581.
6. Amir A, McDonald D, Navas-Molina JA, Kopylova E, Morton JT, Zech Xu Z, Kightley EP, Thompson LR, Hyde ER, Gonzalez A, et al.: Deblur rapidly resolves single-nucleotide community sequence patterns. mSystems 2017, 2:e00191-00116.




