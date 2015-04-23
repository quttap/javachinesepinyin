## 1、Checkout ##

http://code.google.com/p/javachinesepinyin/source/checkout

## 2、Download Corpus ##
javachinesepinyin使用了两份语料：LCMC中文与拼音的对应语料和宏爵财经资讯提供的一份新闻语料。
### 2.1、LCMC语料 ###
src/main/resources/corpus/LCMC，随源码下载，其中包含了若干文本文件，其中的拼音已经被处理成无声调（四声）。

### 2.2、新闻语料 ###
javachinesepinyin使用的新闻语料news-1.idx.gz<br />
http://code.google.com/p/javachinesepinyin/downloads/detail?name=news-1.idx.gz&can=2&q=#makechanges

## 3、编译 ##
可以使用IDE netbeans进行编译<br />
如成功则build出来javachinesepinyin.jar、javachinesepinyin-${version}-bundle.zip

## 4、HMM模型 ##
首先准备语料，解压news-1.idx.gz和javachinesepinyin-${version}-bundle.zip，得到文件news-1.idx。
```
gzip -d news-1.idx.gz
cp news_1.idx corpus/LCMC
```
### 4.1、训练拼音转汉字和汉字转拼音模型 ###
```
cd bin
./train.sh ../corpus/LCMC
```
将生成ptw.m和wtp.m文件。

## 5、运行 ##
在生成m文件之后，可以运行javachinesepinyin了。
```
cd bin
./run.sh
```