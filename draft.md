Cat bead sox file play
nohup bash run.sh
vim nohup.out

ntp.tuna.tsinghua.edu.cn

sudo apt-get update
sudo apt-get install ntpdate
sudo ntpdate ntp.tuna.tsinghua.edu.cn
sudo hwclock --localtime --systohc

clean conda: conda clean -t(more -h)
nvidia version: cat /proc/driver/nvidia/version
check cuda: https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html
install cuda: https://developer.nvidia.com/cuda-downloads?target_os=Linux
install pytorch: https://pytorch.org/

conda: https://zhuanlan.zhihu.com/p/190777953 https://www.jianshu.com/p/44cda13ce29f https://segmentfault.com/a/1190000022422496

