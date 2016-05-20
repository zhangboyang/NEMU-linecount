# NEMU 代码行数统计工具
使用 git 历史来统计 NEMU 代码行数变化情况的小工具。

## 示例
### 绘图结果
![example](/example.png)

### 图例解释
nemu-total, kernel-total, game-total 分别代表 nemu, kernel, game 部分的新添加的代码行数。
total 是以上三个部分，新添加的代码行数之和。
total-space 是以上三个部分，新添加的空白行数之和。

## 使用方法
首先需要安装 gnuplot 程序，以 ubuntu 为例：
```sh
apt-get install gnuplot
```
将 linecount.sh 和 plotlinecount.gnu 放入 NEMU 的根目录下。
进入 NEMU 根目录，执行以下命令来生成代码统计数据文件 lcdata.txt，该过程耗时较长：
```sh
./linecount.sh > lcdata.txt
```
执行以下命令来绘图
```sh
gnuplot -e "lcfile='lcdata.txt'" plotlinecount.gnu 
```

