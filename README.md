# jupyter-examples
Tellus Jupyter上で衛星データを分析するJupyter Notebookのサンプルです。以下の点に注意の上、ご利用ください。


## 注意点
* このnotebookはTellus Jupyter上での動作のみを想定しています
* `~/examples` 内では上書き保存することができません。編集する場合は `~/work` ディレクトリへコピーしてから実行することをおすすめします。
* このnotebookで取得する全てのデータはTellus上での利用に限定されます
* このnotebookでの分析の正確性については一切保証いたしません


## Notebook一覧
* Tellus API利用サンプル:  
  Tellusから光学画像（AVNIR-2）を取得し、簡単な画像処理を行います


## ライブラリについて
代表的なライブラリはインストール済みですが、追加でインストールすることも可能です。
Jupyter Notebook画面の `New` > `Terminal` からターミナルを開き、`conda` や `pip` コマンドでインストールを行ってください。
なお、現在root権限は提供しておりません。

※ ただし、今後のアップデートで環境の互換性は保証していませんのでご注意ください。追加したライブラリなどは別途記録しておくことをおすすめします。

### インストール済みの主なライブラリ
* `numpy=1.13`
* `matplotlib=2.2`
* `pandas=0.23`
* `scipy=1.1`
* `scikit-learn=0.20`
* `scikit-image=0.14`
* `tensorflow=1.12`
* `keras=2.2`


## APIについて
現在、本環境から利用できるAPIを順次追加しています。Tellus Jupyter内での通常の利用については制限ありません。
データをTellus Jupyter外で利用する場合は、データによって一部制限があります。詳しくは[各データポリシー](https://www.tellusxdp.com/ja/dev/data)をご覧ください。

提供中のAPI詳細については[こちら](https://www.tellusxdp.com/ja/dev/api)をご覧ください。

※ XYZ方式とは、ズームとタイル座標を指定する方式です。[詳細やそれぞれの値を決める方法についてはこちら](https://maps.gsi.go.jp/development/siyou.html)をご覧ください。

