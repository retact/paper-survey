
---
author: "retact"
title: "Development of five-finger multi-DoF myoelectric hands with a power allocation mechanism"
date: "2021-04-16"
description: "Sample article showcasing basic Markdown syntax and formatting for HTML elements."
tags: [
    "AH"
]

---
## 1. どんなもの？
ロボットハンドのピンチ動作の冗長な自由度を利用した握力を向上させるPower allocation mechanismによって、
指先の力がこれを用いていないものと比べて64%上昇させることができ、3本指で1kgの物体を持ち上げた。
サイズや重量を大幅に変えることなく、自由度が高く安定した状態で握力を向上できる。
<!--more-->

## 2. 先行研究と比べてどこがすごいの？
[R.Kato, H.Yokoi, "Evaluation of Motor Recovery by Using Adaptive Myoelectric Hand", Journal of the Robotics Society of Japan, Vol.27, No.8, pp.102-108, ROBOTICS SOCIETY OF JAPAN, 1J2-7, Sep. 2010. In Japanese](https://www.researchgate.net/publication/272574108_Evaluation_of_Motor_Recovery_by_Using_Adaptive_Myoelectric_Hand)  
 では腱駆動と干渉駆動機構を備えた5本指のロボットハンドを提案しているが、DoFが独立した機構のため5本の指のサブセットでの握力が低いため、
サブセットの握力を向上させるallocation mechanismは軽量小型と、DoF把持力向上というトレードオフの関係とされている中で画期的なものとなっている。

## 3. 技術や手法の"キモ"はどこにある？

**・1つの指につき2つのアクチュエータと13DoFの18関節でで駆動する総重量1.1kgのロボットハンド**   
**・未使用の動力を配分線を介して駆動力を隣接する指に配分する干渉機構を用いることで動力を配分することで握力を向上させられる。
（2本指の把持動作と3本指の把持動作では、小指から人差し指への動力配分をしている)**  
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6615630/6630547/6630852/6630852-fig-3-source-small.gif)   
**・伝達するワイヤが伸びているときに力を伝達し、弛んでいるときに伝達しないH型の伝達機構によって指の結合状態が分断したりする。**  
 ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6615630/6630547/6630852/6630852-fig-4-source-small.gif)  
**・電力配分線の長さは独立して動かす間と結合している状態を作るために、サイバーグローブを用いてDoFリバフを計測し合力を考えて適切に設計する。**  
 ![Figure 7](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6615630/6630547/6630852/6630852-fig-7-source-small.gif)

  
## 4. どうやって有効だと検証した？
**・指先の力に関しては圧力センサを用いてpower allocation mechanismを使う前と比べ全体的に23-63%上昇している。**
**・ピックアンドプレースタスクにおいて、タスクの成功率が高くなっている。**
**・動力配分を行わないグリップオブジェクトは300gにたいして動力配分を行った3本指では1000gのグリップオブジェクトを把持できる。**

## 5. 議論はあるか？
**・親指はDoFを独立させるため、動力配分の対象外としている。**  
**・機構の構造上、非グリップの指を伸ばすと動力配分機構が分配を阻害するため、把持力を向上させるために握らない指を曲げなければならない。**  

## 6. 次に読むべき論文はあるか？

義手制作における設計の目的、基準、方法
・[C. Capriani, M. Controzzi, M.C. Carrozza, "Objectives, criteria and methods for the design of the SmartHand transradial prosthesis," Robotica 2010, vol. 28 pp. 919-927, 2010.](https://www.cambridge.org/core/journals/robotica/article/objectives-criteria-and-methods-for-the-design-of-the-smarthand-transradial-prosthesis/5FE55ACFEE3849366685EBB8610558C6)

### 論文情報・リンク

・ [Tatsuya Seki; Tatsuhiro Nakamura; Ryu Kato; Soichiro Morishita; Hiroshi Yokoi，"Development of five-finger multi-DoF myoelectric hands with a power allocation mechanism，" 2013 IEEE International Conference on Robotics and Automation，no.13851200，17 October 2013](https://ieeexplore.ieee.org/document/6630852)
