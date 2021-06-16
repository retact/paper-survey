---
author: "retact"
title: "A Low-Cost, Wireless, 3-D-Printed Custom Armband for sEMG Hand Gesture Recognition"
date: "2021-06-16"
description: "dA Low-Cost, Wireless, 3-D-Printed Custom Armband for sEMG Hand Gesture Recognition"
tags: [
    "AB",
    "EMG",
    "FE",
]

---

## 1. どんなもの？
1000Hzのサンプリングレートで10チャンネルの計測能力を持ち、60gで製作費が150ドルの安価なEMGアームバンドの提案。市販されているMyoアームバンドとLDA(Hudins' Time-Domain Featureset)による分類性能と生データ周波数データによってアームバンドの性能を比較している。また比較の際には22人の健常者に11のジェスチャーをそれぞれ4セット取得したデータセットを作っている。  

<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
様々な他チャンネル筋電図の取得デバイスがあるが、UltiumEMGやTrignoAvanty,DataLITEといったデバイスはサンプリングレートは高いものの、それぞれのチャンネルがバラバラになっており装着に手間がかかってしまう他、高価である。Myoアームバンドに関してはチャンネル数が少ないが値段も安く装着しやすいというメリットがあるが、サンプリングレートが少ない。そこで安価でかつサンプリングレートの高いアームバンドの開発をこの論文で行われている。accuracy scoreとしては全体的にMyoアームバンドよりも精度が良いアームバンドであることを示している。  

## 3. 技術や手法の"キモ"はどこにある？
 ● カスタムSoCを含むデータ取得から処理データ送信を行うPCB基盤  
  ・SoC-入力参照ノイズ2.2μVrms，分解能10ビット，ダイナミックレンジ6mVpp，帯域幅20〜500Hz  
  ・IMU-ICM-20948  
  ・MCU-MSP430F5328  
  ・wireless-nRF24L01  
  ・PMU-LDO(1.9v)LDO(1.2v)の小消費電力の実現で100mAのリポ  
 ![Figure 2](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g002-550.jpg)  
 ![Figure 3](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g003-550.jpg)  

 ● 3Dmodel
 合計10チャンネルで3種類の形の3Dmodelにより軽量でソケットが通しやすい形状にしてある。  
 ![Figure 4](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g005-550.jpg)  
 ● 比較した分類手法  
 LDAで特徴セットHudins' Time-Domain Featuresetを用いている。  
 よく使われる分類手法としてSVMなどがあるがSVMはハイパーパラメータを指定するため比較には向いていない。  
 H-TDはもっともよく使われている特徴セットであるため使用している。  
 また生データでは信号を状Channels X Samples（Myo Armbandでは8×50、3DC Armbandでは10×250)の画像としてConvNetにわたし分類する。  
 ![Figure 9](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g009-550.jpg)  
 周波数データはFFTで変換のち、4×8×11と4×10×51でConvに渡し、分類を行う。  
 ![Figure 10](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g010-550.jpg)  


## 4. どうやって有効だと検証した？
 ● 新しいデータセットを作成しMYOアームバンドと3DCプリンタで性能を比較する。  
 22人の健常者に11のパターンをそれぞれ5秒ずつ、計4セット(セットごとの間は5分)のデータ取得し、そのデータを元にそれぞれの分類手法によりアームバンドの精度を比べた。  
 ![Figure 7](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g007-550.jpg)  
 ![Figure 8](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g008-550.jpg)  
 結果としては全体的にAccuracy ScoreがMYOを上回っており、ChuckとPinch Gripの分類が混合行列より難しいことがわかった。  
 しかしLDA分類法においてのみ、Wilcoxon signed-rank検定で有意と判断された（p値=0.0309）  
 また、学習をセットごとに行うことによって、Myo Armbandよりもウォームアップ期間が長くなる可能性があることを示した。  
 ![Figure 11](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g011-550.jpg)  
 ![Figure 12](https://www.mdpi.com/sensors/sensors-19-02811/article_deploy/html/images/sensors-19-02811-g012-550.jpg)  
## 5. 議論はあるか？
 ● オンラインによる分類を行っていない。  
 ● 比較した手法が少ない。  
 ● クロストークによる信号のノイズを増大させるような過度に大きな電極を設計しないように注意する必要がある。   
 ● 接触面積を大きくすることで、電極のずれの影響を減らす。  
## 6. 次に読むべき論文はあるか？
使用したSoCについて  
-[G. Gagnon-Turcotte, C. Ethier, Y. De Köninck and B. Gosselin, "A 13μm CMOS SoC for simultaneous multichannel optogenetics and electrophysiological brain recording," 2018 IEEE International Solid - State Circuits Conference - (ISSCC), 2018, pp. 466-468, doi: 10.1109/ISSCC.2018.8310386.](https://ieeexplore.ieee.org/abstract/document/8310386?casa_token=mSwgdIZzLI0AAAAA:74mv5M8wzgB5rpoaadruEG5Ay3uiNZSVZYyMCvCOuM_65yanC5oq0vHfjHTiQbIN2wdkkFETOZlN)  

### 論文情報・リンク

- [Côté-Allard, U.; Gagnon-Turcotte, G.; Laviolette, F.; Gosselin, B. A Low-Cost, Wireless, 3-D-Printed Custom Armband for sEMG Hand Gesture Recognition. Sensors 2019, 19, 2811. https://doi.org/10.3390/s19122811](https://www.mdpi.com/484852)  
