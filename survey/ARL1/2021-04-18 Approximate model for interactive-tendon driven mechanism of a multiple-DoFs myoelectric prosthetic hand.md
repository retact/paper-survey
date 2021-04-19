---
title:  "Approximate model for interactive-tendon driven mechanism of a multiple-DoFs myoelectric prosthetic hand"
date:   2021-04-21
categories: PH EMG
---

## 1. どんなもの？
インタラクティブな腱駆動機構の筋電義手の開発とその評価。形状モデルと関節トルクの平衡モデルに基づいた腱駆動機構の制御方法の近似モデルとキャリブレーションについて。ロボットハンドの角度関係は1次関数で近似ができ、ロボットハンドの関節角度と腱ワイヤーのけん引の長さはSIN関数で近似できるPIP,DIPの角度が小さい場合MPの動きを10%以下の動きで制御可能であり、また近似モデルを用いることでDIP、PIPのの関節の動きを9-15%の誤差で制御でき、インタラクティブな腱駆動機構の義手開発に可能性がある！
　
## 2. 先行研究と比べてどこがすごいの？
 ●  これまでの筋電義手のアクチュエータや伝達機構は筋肉に相当するものではなく、重くなり、把持力を向上させるのが難しかったが、小型アクチュエータの力を効率的に指に配分し、インタラクティブな腱駆動による筋電義手を開発したこと。
 　
## 3. 技術や手法の"キモ"はどこにある？
 ● MP関節のみ動かすワイヤとMP,PIP,DIPを動かすワイヤを動かす2つのアクチュエータを用いて把持力を向上させる。  
 ![Figure 2](https://github.com/takutosoeda/paper-survey/blob/main/img/Approximate%20model%20for%20interactive-tendon%20driven%20mechanism%20of%20a%20multiple-DoFs%20myoelectric%20prosthetic%20hand/figure2.gif?raw=true)  
 ● Servohornによって可変的にけん引するアクチューエータを用いている。  
 ![Figure 3](https://github.com/takutosoeda/paper-survey/blob/main/img/Approximate%20model%20for%20interactive-tendon%20driven%20mechanism%20of%20a%20multiple-DoFs%20myoelectric%20prosthetic%20hand/figure3.gif?raw=true)  
 ● [電力配分機構](http://www.jslst.org/documents/Conference/2011/html/pdf/paper_178.pdf)により指先の力を最大で60%上昇させた。  
 ● 2つのワイヤーと2つの伸展用のワイヤー構造によるけん引長さを決める幾何モデル  
 ![Figure 6](https://github.com/takutosoeda/paper-survey/blob/main/img/Approximate%20model%20for%20interactive-tendon%20driven%20mechanism%20of%20a%20multiple-DoFs%20myoelectric%20prosthetic%20hand/figure6.gif?raw=true)  
 ● アクチュエータへの入力と腱ワイヤーのけん引長さの関係の近似モデルによって義手を制御する。 
 


## 4. どうやって有効だと検証した？
 ● 近似モデルによるパフォーマンスにより、入力角度と出力角度を実験的に評価  
 ● IPが小さいときのMPの入出力は10%未満で線形でIPが大きい場合非線形になる  
 ● IPの関係はほぼ線形になる。  
 ![Figure 11](https://github.com/takutosoeda/paper-survey/blob/main/img/Approximate%20model%20for%20interactive-tendon%20driven%20mechanism%20of%20a%20multiple-DoFs%20myoelectric%20prosthetic%20hand/figure11.gif?raw=true)  
  

## 5. 議論はあるか？
 ● ロボットハンドの挙動に応じた近似モデルの補正項の追加  
 ● キャリブレーション方法の再検討  
   
## 6. 次に読むべき論文はあるか？
 ● [E. A. Biddiss and T. T. Chau, "Upper limb prosthesis use and abandonment: A survey of the last 25 years", Prosthetics and Orthotics International, vol. 31, no. 3, pp. 236-257, September 2007.]*(https://pubmed.ncbi.nlm.nih.gov/17979010/)

### 論文情報・リンク

- [T. Seki, Y. Jiang and H. Yokoi, "Approximate model for interactive-tendon driven mechanism of a multiple-DoFs myoelectric prosthetic hand", IEEE International Conference on Robotics and Biomimetics, pp. 999-1004, 2014.](https://ieeexplore.ieee.org/document/7090463#sec5)
