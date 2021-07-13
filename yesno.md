# 搭建你的第一个CAT项目

我们将一步步利用CAT和yesno数据搭建一个语音识别项目，请确保您已经完成了CAT的安装和环境配置。

## 文件准备

1. 在egs下创建目录yesno

2. 编写以下两个个文件

   - path.sh

     ```shell
     # CAT toolkit
     export CAT_ROOT=../../
     export PATH=$CAT_ROOT/src/ctc_crf/path_weight/build:$PATH
     export PATH=$PWD/ctc-crf:$PATH
     # Kaldi
     export KALDI_ROOT=${KALDI_ROOT:-/home/hpl/workspace/kaldi}
     [ -f $KALDI_ROOT/tools/env.sh ] && . $KALDI_ROOT/tools/env.sh
     export PATH=$PWD/utils/:$KALDI_ROOT/tools/openfst/bin:$PWD:$PATH
     [ ! -f $KALDI_ROOT/tools/config/common_path.sh ] && echo >&2 "The standard file $KALDI_ROOT/tools/config/common_path.sh is not present -> Exit!" && exit 1
     . $KALDI_ROOT/tools/config/common_path.sh
     export LC_ALL=C
     # Data
     export DATA_ROOT=data/yesno
     ```

     配置全局的环境变量，分别配置CAT、kaldi、数据集的环境变量，代码来源为wsj项目下的同名文件。

     创建完后可以在终端里运行一遍`. ./path.sh`方便接下来配置。

   - cmd.sh

     ```shell
     export train_cmd=run.pl
     export decode_cmd=run.pl
     export mkgraph_cmd=run.pl
     export cuda_cmd=run.pl
     ```

     这里也是沿用自kaldi的并行化工具，适应不同的环境可以配置queue.pl等以及不同的参数。此处使用run.pl即可。

3. 创建链接到kaldi以及cat工具包的目录，便于代码的编写以及迁移

   ```shell
   ln -s ../../scripts/ctc-crf ctc-crf
   ln -s $KALDI_ROOT/egs/wsj/s5/utils utils
   ln -s $KALDI_ROOT/egs/wsj/s5/steps steps
   ```

4. 创建local目录，存放本项目专用的数据处理，训练等脚本文件

5. 创建run.sh，在run.sh中完成我们整个工作流程的编写

   ```shell
   #!/bin/bash
   
   # Copyright 2018-2021 Tsinghua University
   # Author: Siwei Li
   # yesno for CAT
   
   # environment
   . ./cmd.sh
   . ./path.sh
   
   #set 
   H=`pwd`  # home dir
   n=12     # parallel jobs=$(nproc)
   stage=1  # set work stages
   stop_stage=9
   yesno=$DATA_ROOT  #data root
   
   . utils/parse_options.sh
   
   NODE=$1
   if [ ! $NODE ]; then
     NODE=0
   fi
   
   if [ $NODE == 0 ]; then
     if [ $stage -le 1 ] && [ $stop_stage -ge 1 ]; then
       echo "stage 1: *"
       # work
     fi
   
     #more stages
   fi
   ```

## 数据预处理

1. 在local目录下创建文件prepare_data.sh

   

