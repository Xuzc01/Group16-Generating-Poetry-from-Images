# 图片描述生成（诗歌）

## 目录
1. [项目简介](#项目简介)
2. [难点分析](#难点分析)
3. [模型结构](#模型结构)
4. [所用数据集](#所用数据集)
5. [实验结果](#实验结果)
6. [参考文献](#参考文献)
7. [使用说明](#使用说明)

## 项目简介
&emsp;&emsp;从图像中自动生成自然语言已经引起广泛关注，本项目更进一步来研究由**图像自动生成诗歌**（多行）创作。不同于普通的图片描述，诗歌描述可能不那么注重于描述图片所代表的事实本身，而是倾向于从图像中的物体、场景和情感中捕捉更深层次的意义和诗意符号（如从猎鹰中捕捉骑士，从进食中捕捉狩猎和战斗，从站立中捕捉等待）。本项目通过使用策略梯度进行对抗训练将任务进一步拆解，最终虽然再韵律等传统的诗歌技巧等方面仍不成熟，但仍然具有一定的是个结构和风格。   

## 难点分析
1. **多模态处理**：与由主题生成诗歌相比，该任务是一个跨模态任务。一个直观的想法是由图像提取主题再生成诗歌，但是这样会造成信息丢失。
2. **任务主观性**：与caption相比，该任务是一个更加主观的任务，因为一张图像可能对应多种诗歌，而caption更侧重描述image中的客观事实。
3. **格式要求**：诗歌的格式和风格与自然语言不同。本文生成的是自由诗（English free verse），对韵律等无要求。
   
## 模型结构

![1](https://github.com/user-attachments/assets/c25f6cec-5f9a-48d3-ace0-766fce09da18)

 **（1)深度耦合视觉-诗歌嵌入模型**：用于从图像中学习诗歌表征。
 
 **（2)策略梯度优化的多对抗训练过程**：基于RNN的生成器作为代理，两个判别网络为策略梯度提供奖励。



## 所用数据集
1. **Multi-Modal Poem dataset (MultiM-Poem)**：由图像和人工标注的诗句组成
![2(1)](https://github.com/user-attachments/assets/0976ab2f-1079-4d2e-83ea-0d099e4884f1)

2. **Uni-Modal Poem dataset (UniM-Poem)**:最大的诗句语料库
![2(2)](https://github.com/user-attachments/assets/b6530648-0490-4e58-9818-a367dd729912)

3. **MultiM-Poem (Ex)**：通过训练好的嵌入模型，对MultiM-Poem通过相似度扩展并去除冗余而来

## 实验结果

### 1.**分类报告**


## 参考文献
- 参考文献：[Bei Liu, Jianlong Fu, Makoto P. Kato, and Masatoshi Yoshikawa. 2018. Beyond Narrative Description: Generating Poetry from Images by Multi-Adversarial Training. ](https://arxiv.org/pdf/1804.08473)   


## 使用说明
1. [点此下载模型](https://github.com/Xuzc01/Generating-Poetry-from-Images/edit/main/README.md)，并放到code/model/目录下：
   
2. 本项目仅支持Linux系统：

