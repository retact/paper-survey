---
title:  "A Soft-Robotic Approach to Anthropomorphic Robotic Hand Dexterity"
date:   2021-04-17
categories: AH
---

## 1. どんなもの？
ソフトロボットハンドBCL-26ではGRASP分類法や親指の器用さにおいて機能的な器用さを実現し、すべての指の独立制御を可能にした。
フレキシブルケーブル、弾性リンクなどを用いて実現した受動的なしなやかさ（パッシブコンプライアンス）を導入することによって本来機械的に要求される要件を大幅き軽減することができ、
指の可動域が大幅に上昇した。26自由度のロボットハンドについて性能検証した。ただし、ソフトアクチュエータにおけるスピードについては限界がある。

## 2. 先行研究と比べてどこがすごいの？
 ●　ソフトロボットハンドは固有の柔軟さによって、統合されたセンシング、衝撃体制、物体適応性などがある。  
 
 ●　これまでのロボット工学においては機械的な複雑さと機能的な可能性を含んだDixterityによって評価されていたが、Gransping texonomy（把持分類）,
 Thumb Dexterity（親指）,Manipulation taxonomy（6自由度の基本操作）によって評価した。  
  
 ●　BCL-26は，人間の手の器用さ50項目（GRASP分類33項目，Kapandjiテスト11項目，手の中の操作分類6項目）をすべてクリアすることができた。
  
 ●　既存のソフトウェアアクチュエータは緩やかな曲げ動作を行っていたが、V型チェンバとX型チェンバによって鋭い曲げ動作を実現した。
   
## 3. 技術や手法の"キモ"はどこにある？
 ●　Elastomeric-chamberと空気駆動のアプローチを再投資、複数のチャンバを用いて手の設計を行っている。  
 ●　解析モデル、有限要素モデリング（FEM）を用いてV,Xチャンバーは，曲げ半径を大幅に縮小し手の限られたスペースに組み込むことを可能にした  
 ![Figure 1](https://github.com/takutosoeda/paper-survey/blob/main/img/A%20Soft-Robotic%20Approach%20to%20Anthropomorphic%20Robotic%20Hand%20Dexterity/figure1.gif?raw=true)  
   
 ●　各アクチュエータが非線形であり、かつ多くの自由度制御を行うため32個の独立した空気圧作動チャンネルを持つ作動コンソールを制作  
 ![Figure 3](https://github.com/takutosoeda/paper-survey/blob/main/img/A%20Soft-Robotic%20Approach%20to%20Anthropomorphic%20Robotic%20Hand%20Dexterity/figure3.gif?raw=true)  
   
 ●　カスケード制御によって単一関節を制御により5回の繰り返しのRMS誤差が2度，すなわち最大可動域の1.9％と非常に正確
   

## 4. どうやって有効だと検証した？
 ●　Grasping Taxonomy(33種)すべて成功  
 ![Figure 4](https://github.com/takutosoeda/paper-survey/blob/main/img/A%20Soft-Robotic%20Approach%20to%20Anthropomorphic%20Robotic%20Hand%20Dexterity/figure4.gif?raw=true)  
  
 ●　Thumb Dexterity(Kapandji thumb testに11点)  
  
 ●　In-Hand Manipulation  
 ![Figure 5](https://github.com/takutosoeda/paper-survey/blob/main/img/A%20Soft-Robotic%20Approach%20to%20Anthropomorphic%20Robotic%20Hand%20Dexterity/figure5.gif?raw=true)

## 5. 議論はあるか？
 ● ソフトアクチュエータが剛体構造部品を駆動するハイブリットアプローチについて  
 ● ソフトアクチュエータのスピードの限界を伸ばす。  
 
## 6. 次に読むべき論文はあるか？
人間とロボットの器用な操作の分類について  
[ I. M. Bullock, R. R. Ma and A. M. Dollar, "A hand-centric classification of human and robot dexterous manipulation", IEEE Trans. Haptics, vol. 6, no. 2, pp. 129-144, Apr. 2013.](https://ieeexplore.ieee.org/document/6298887)

### 論文情報・リンク

- [J. Zhou et al., "A soft-robotic approach to anthropomorphic robotic hand dexterity", IEEE Access, vol. 7, pp. 101483-101495, 2019.](https://ieeexplore.ieee.org/document/8786814/citations?tabFilter=papers#citations)
