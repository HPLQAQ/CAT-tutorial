# CAT入门

CAT是一个基于CTC-CRF的语音识别端到端工具包，项目地址：https://github.com/thu-spmi/CAT

这篇文档从环境配置，第一个CAT项目(yesno)两个部分介绍了CAT的入门使用。



## 环境配置

以下文档介绍了CAT安装配置的流程以及一些常用的工具

[environment](./environment.md)

在配置安装好环境之后，你可以尝试运行一次yesno项目的run.sh，如果最后输出

```
Decoding done.
%WER * [ * ] */wer_*
```

说明你的环境配置成功了。

[yesno项目](https://github.com/HPLQAQ/CAT/tree/dev/egs/yesno)

## 第一个CAT项目

以下文档介绍了使用CAT利用yesno数据集搭建yesno项目并进行识别的流程。

[yesno.md](./yesno.md)

这份文档仅对项目流程进行了初步的介绍，推荐阅读kaldi tutorial，《kaldi语音识别实战》（作者：陈果果）（重点第3、5章）进一步了解数据处理过程。