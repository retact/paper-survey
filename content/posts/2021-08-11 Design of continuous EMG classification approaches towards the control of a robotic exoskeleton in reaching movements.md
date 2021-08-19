
---
author: "retact"
title: "Design of Continuous EMG Classification Approaches Towards the Control of a Robotic Exoskeleton in Reaching Movements"
date: 2021-08-11
draft: false
description: "Design of continuous EMG classification approaches towards the control of a robotic exoskeleton in reaching movements"
tags: [
    "EMG"
]

---

## 1. どんなもの？
 実用段階では連続的なオンライン制御が行われていない中，8人の健常者の上腕の筋電図を用いて８種類の動きを分類する擬似オンラインアプリケーションを開発し，その精度を70％以上としている．またこの論文では3つのウィンドウサイズによる分類精度の影響についても述べられている．
<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
 ● 現在のリハビリに用いられる筋電インターフェースの多くはEMGの振幅に基づいて単一DoFのアクチュエータを制御することに焦点を当てているが，この論文では複数の連続的な制御を試みている．また，複数の動作におけるものの先行研究はEMGをトリガーとして用いるものであったため，そのためフィードバックをしながらリハビリを行う試みは新規性がある．    

## 3. 技術や手法の"キモ"はどこにある？
 ● 使用した分類アルゴリズムはLIBSVMで使用した特徴量はwave lengthである.

 ● 動きの検知をする2値分類器で動きを検出した後に，reach，returnのそれぞれ４分類の2つの分類器に分けた分類手法と，8クラスの分類器に分けた分類手法を比較している.  
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8001594/8009210/8009234/8009234-fig-3-source-small.gif)  
 ● 分類精度を比較することにより，適切なウィンドウサイズを出している．その結果,
動きの検出には200ms，意図した方向には1sのウィンドウサイズを用いた分類を行っている．  
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8001594/8009210/8009234/8009234-fig-2-source-small.gif)  

## 4. どうやって有効だと検証した？
 ● 右利き5人の8人の健常者により，それぞれ200回の試行を通じて，200ms,500ms,1sの中での最適な解析窓長さと分類手法を比較した結果，最大で78％の分類精度を得ることができた．  
 ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8001594/8009210/8009234/8009234-fig-4-source-small.gif)  
 ![Figure 5](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8001594/8009210/8009234/8009234-table-1-source-large.gif)  
 
## 5. 議論はあるか？
 ● リアルタイム制御の可能性を示すために健常者および脳卒中患者を対象に、この筋電インターフェースをオンラインで使用する実験を行う必要がある．  
 ● 他のウィンドウサイズの検証を行っていない.  
## 6. 次に読むべき論文はあるか？
 EEG-EMG-BMI  
[A hybrid EEG-EMG BMI improves the detection of movement intention in cortical stroke patients with complete hand paralysis](https://ieeexplore.ieee.org/document/8512711)  


### 論文情報・リンク

- [N. Irastorza-Landa et al., "Design of continuous EMG classification approaches towards the control of a robotic exoskeleton in reaching movements," 2017 International Conference on Rehabilitation Robotics (ICORR), 2017, pp. 128-133, doi: 10.1109/ICORR.2017.8009234.](https://ieeexplore.ieee.org/document/8009234)
