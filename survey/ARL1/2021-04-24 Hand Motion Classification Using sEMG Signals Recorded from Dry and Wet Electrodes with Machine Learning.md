---
title:  "Hand Motion Classification Using sEMG Signals Recorded from Dry and Wet Electrodes with Machine Learning"
date:   2021-04-24
categories: EMG 
---

## 1. どんなもの？
乾式を開発し,市販の湿式電極をLDA、QDA、線形SVM、ガウスSVM、二次SVM、決定木、KNN分類器を用いて分類したところ、乾式と湿式ではあまり精度は変わらなかった。そのなかでも、ガウシアンSVMでの分類は96%に達している。開発した乾式電極は、柔軟性、伸縮性、長期使用が可能であることも特徴である。

## 2. 先行研究と比べてどこがすごいの？
 ● これまでは皮膚インピーダンスを改善するために導電性ゲルをしようしていたが、経過時間が上がるにつれ、インピーダンスが上昇し、使い捨てである他、皮膚疾患を持っている人にもつかえなかったが、今回の乾式電極は洗浄性と再利用性に優れている。これまで行われてきた分類方法を用いて乾式電極で計測したEMGを分類しても湿式と同様の結果が得られた。

## 3. 技術や手法の"キモ"はどこにある？
 ● 乾式電極の基盤には伸縮性を実現するためにポリマーが用いられている。  
 ● 導電層には金メッキで加工された銅板が用いられている。またポリイミドをもちいて両面フレックスへの伝達を助けている。  
 ● 特徴量抽出ではEMG信号の絶対値の平均。波形の長さ。信号が振幅軸を横切る回数。EMGの傾き変化の回数を用いている。  
  


## 4. どうやって有効だと検証した？
 ● 分類器に欠けた後、湿式乾式での分類精度を比較する。  

## 5. 議論はあるか？

## 6. 次に読むべき論文はあるか？

### 論文情報・リンク

- [M. Fazeli, F. Karimi, V. Ramezanian, A. Jahanshahi and S. Seyedin, "Hand Motion Classification Using sEMG Signals Recorded from Dry and Wet Electrodes with Machine Learning," 2020 28th Iranian Conference on Electrical Engineering (ICEE), 2020, pp. 1-4, doi: 10.1109/ICEE50131.2020.9260578.](https://ieeexplore.ieee.org/document/9260578)
