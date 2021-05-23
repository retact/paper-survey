---
title:  "An Investigation of Temporally Inspired Time Domain Features for Electromyographic Pattern Recognition"
date:   2021-05-22
categories:EMG FE
---

## 1. どんなもの？
ピーク検出から導出された時間的な新しい特徴量について2つ紹介しており、この時間的特徴量精度は自己回帰係数，ヒストグラム，ゼロクロスなどといった一般的に用いられる時間的特徴よりも，それぞれ8％，11％，17％優れている分類精度を示している。またHudginsの時間領域の特徴と比較して，ロバストな特徴セットの一部として追加情報を提供することが示さレている。  

## 2. 先行研究と比べてどこがすごいの？
 ● 平均絶対値（MAV），波形長（WL），ゼロクロス（ZC），スロープ・サイン・チェンジ（SSC），自己回帰係数（AR），ヒストグラム（HIST）などの特徴量によってパターン認識が行われてきたが、動作タスクになると複雑で非定常な筋電分類は難しい。また周波数特徴に関しても追加の計算コストや汎用性の低下を招くため実用的ではないため、時系列情報から導出された特徴に基づく時間領域の特徴をっつうじて分類精度を向上させた。  

## 2.1 知ったこと思ったこと
 ● バーストとはおそらくバースト信号のことで時間領域のごく一部にのみ、信号（正弦波、方形波、三角波など）が存在し、それ以外の領域には信号が存在しないもののことを指している。  
 ● エンベロープは信号の包括線のことを指し、信号のレベル変動を知りたいときに役に立つ。  
 ● ARは時系列モデリングの特徴
## 3. 技術や手法の"キモ"はどこにある？
 ● データ処理とセグメンテーション  
  1000Hzにダウンサンプリングされ，電力線干渉，アーチファクト，高周波ノイズを除去するために，次数4のデジタルバターワース有限インパルス応答（FIR）フィルタを用いて，ノッチ（50Hz）およびバンドパス（20-500Hz）フィルタリングが行われる。また、特徴抽出とパターン分類のために，125ミリ秒でオーバーラップした250ミリ秒の解析ウィンドウを用いてセグメント化する  
  
 ● EMG信号の時間的エンベロープを作成  
 時間に応じた筋活動を表現し，EMGバーストの局所的な特徴をより明確にする  
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8471725/8512178/8513427/phiny1-23141964-small.gif)  
 　first burst時系列では，前処理したEMGデータを2乗した後，64msのハミング窓関数を持つ移動平均FIRフィルタに通し,Peak Valley時系列では，EMGデータを2msのハミング窓を持つ移動平均FIRフィルタに通す。  
 ● peaks/valleysの局所的な特性を計算するため、  
 （1）振幅値，（2）振幅エクスカーション，（3）突出度，（4）幅，（5）相対時間値などの特性タイプを検討した。  
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8471725/8512178/8513427/phiny2-23141964-small.gif)  
 ● 抽出された特徴量の時系列から要約統計量を計算
  ○ peak time series  
  最大値と平均値でそれぞれの特徴量においてAMxP, EMxP, PMxP, WMxP, TMxP,AMnP, EMnP, PMnP, WMnP, TMnP  
  ○ valley time series  
  AMxV，EMxV，PMxV，WMxV，TMxV,AMnV，EMnV，PMnV，WMnV，TMnV  

  ![Figure3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8471725/8512178/8513427/phiny3-23141964-small.gif)  
  特徴量の中で最も高い性能を示したのはPMnVおよびPMnP特徴量であり，次いでAMnVおよびAMnP特徴量であり、PMnVおよびPMnPは，一般的に使用されているZCおよびSSCを約17〜22％，AR時系列モデリングを約8％，HISTを約11％（いずれもp＜0.05）上回る性能を示した。  
 ● SVM分類器を用いて交差検証分類率によってそれぞれの分類精度を評価している。
 ● 比較特徴量はMAVとWL,ZC, SSC,4次のAR,HIST  
 ● SFSによって使用する特徴量を決定する。
 Hudginsの特徴セット（MAV，WL，ZC，SSC)を再構築して、WL、ZC、PMnV、およびARの特徴量セットでは、データセットによっては上回る精度を示した。  
 ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8471725/8512178/8513427/phiny.t2-23141964-small.gif)  


## 4. どうやって有効だと検証した？
 ● 68名の健常者と経橈骨切断者が手、手首、指、把持動作を行った複数のEMGデータを用いて、提案した特徴量の性能を評価した.
## 5. 議論はあるか？
 ● 比較している特徴量セットが少ない。  
 ● 動的なデータセットを使えていない。  
 ● 純な静的収縮と複雑な動的収縮の両方で見られるEMG活性化の時間的シーケンスにおいて、EMGパターン認識のための未開発の可能性が残っている  
## 6. 次に読むべき論文はあるか？
-[Arvind Gautam, Madhuri Panwar, Archana Wankhede, Sridhar P. Arjunan, Ganesh R. Naik, Amit Acharyya, Dinesh K. Kumar, "Locomo-Net: A Low -Complex Deep Learning Framework for sEMG-Based Hand Movement Recognition for Prosthetic Control", Translational Engineering in Health and Medicine IEEE Journal of, vol. 8, pp. 1-12, 2020.](https://ieeexplore.ieee.org/document/9197671)  

### 論文情報・リンク

- [A. Phinyomark and E. Scheme, "An Investigation of Temporally Inspired Time Domain Features for Electromyographic Pattern Recognition," 2018 40th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), 2018, pp. 5236-5240, doi: 10.1109/EMBC.2018.8513427.
](https://ieeexplore.ieee.org/document/8513427)

