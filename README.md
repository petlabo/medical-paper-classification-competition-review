# medical-paper-classification-competition-review
signate「医学論文の自動仕分けチャレンジ」感想戦

<h3>はじめに</3><br>
9月末までsignateにて、「医学論文の自動仕分けチャレンジ」という、論文のデータ群から医学論文を抽出するコンペに参加した。コンペでは、bert+NNを用いてモデルを作成した。<br>
今回は、BERTの代わりに、<strong>tf-idf</strong>を用いて医学論文の偏りのあるデータ群の二値分類を行う。その際に「学習データのサンプリング方法によって精度は変わるのか」、「モデル学習時のmetricによって精度が変わるのか」といった観点から再度検証した。<br>
結論としては、f7値を目標に予測を行う場合には、非サンプリング、undersamplingの手法が有効であった。一方でf0.1値を目標に予測を行う場合には、over,undersamplingを組み合わせたsmoteennが有効であった。<br>
metricの検証では、aucとbinary_loglossを比較した。aucよりもloglossをmetricに設定することで、f値の精度上昇がおおむね見込めるものの、精度が拮抗した場合もあるため、両方の精度を見ることが望ましいと考えた。
