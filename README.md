# jupyter-examples
Tellus Jupyter上で衛星データを分析するJupyter Notebookのサンプルです。以下の点に注意の上、ご利用ください。


## 注意点
* このnotebookはTellus Jupyter上での動作のみを想定しています
* `~/examples` 内では上書き保存することができません。編集する場合は `~/work` ディレクトリへコピーしてから実行することをおすすめします。
* このnotebookで取得する全てのデータはTellus上での利用に限定されます
* このnotebookで利用するTellus APIには一部サンプル目的のものが含まれます。これは予告なく変更される場合がございます。
* このnotebookでの分析の正確性については一切保証いたしません


## Notebook一覧
* 光学画像の基礎分析1（雪判定）:
  Tellusから光学画像（AVNIR-2）を取得し、雪のの範囲特定を行います
* 光学画像の基礎分析2（雪質分析）:
  Tellusから光学画像（AVNIR-2）を取得し、雪質の判定を行います
* SAR画像の基礎分析（雪判定）
  TellusからSAR画像（PALSAR-2）を取得し、雪の範囲特定を行います


## APIについて
現在、本環境から利用できるAPIを順次追加しています。Tellus Jupyter内での通常の利用については制限ありません。
データをTellus Jupyter外で利用する場合は、データによって一部制限があります。詳しくは[各データポリシー](https://www.tellusxdp.com/ja/dev/data)をご覧ください。

提供中のAPIについては[こちら](https://www.tellusxdp.com/ja/dev/api)も併せてご覧ください。

|種類|内容|エンドポイント|パラメータ|補足|
|----|----|--------------|----------|----|
|OpenStreetMap|XYZで指定された位置・ズームのOpenStreetMapのタイル画像を返します|https://gisapi.tellusxdp.com/osm/{z}/{x}/{y}.png||XYZ方式|
|AVNIR-2 (true color)|XYZで指定された位置・ズームでtrue color合成されたAVNIR-2のタイル画像を返します|https://gisapi.tellusxdp.com/true/{z}/{x}/{y}.png||XYZ方式|
|AVNIR-2 (natural color)|XYZで指定された位置・ズームでnatural color合成されたAVNIR-2のタイル画像を返します|https://gisapi.tellusxdp.com/natural/{z}/{x}/{y}.png||XYZ方式|
|AVNIR-2 (band1 blue)|XYZで指定された位置・ズームのAVNIR-2 band1のタイル画像を返します|https://gisapi.tellusxdp.com/av2ori/band1/{z}/{x}/{y}.png||XYZ方式|
|AVNIR-2 (band2 green)|XYZで指定された位置・ズームのAVNIR-2 band2のタイル画像を返します|https://gisapi.tellusxdp.com/av2ori/band2/{z}/{x}/{y}.png||XYZ方式|
|AVNIR-2 (band3 red)|XYZで指定された位置・ズームのAVNIR-2 band3のタイル画像を返します|https://gisapi.tellusxdp.com/av2ori/band3/{z}/{x}/{y}.png||XYZ方式|
|AVNIR-2 (band4 nir)|XYZで指定された位置・ズームのAVNIR-2 band4のタイル画像を返します|https://gisapi.tellusxdp.com/av2ori/band4/{z}/{x}/{y}.png||XYZ方式|
|AVNIR-2 (brend)|XYZで指定された位置・ズームでパラメータに基づいて合成されたAVNIR-2のタイル画像を返します|https://gisapi.tellusxdp.com/blend/{z}/{x}/{y}.png?opacity=1&r=4&g=3&b=2&rdepth=1&gdepth=1&bdepth=1&preset=ndvi|`opacity`: 透過度 (default: `1`)<br>`r`: Redに対応させるバンド (default: `3`)<br>`g`: Greenに対応させるバンド (default: `2`)<br>`b`: Blueに対応させるバンド (default: `1`)<br>`rdepth`: Redの濃さ (default: `1`)<br>`gdepth`: Greenの濃さ (default: `1`)<br>`bdepth`: Blueの濃さ (default: `1`)<br>`preset`: `true`, `false`, `natural`, `ndvi` のいずれか。`ndvi`の場合、`opacity`以外のパラメータは無視されます。(default: `false`)|XYZ方式|

XYZ方式とは、ズームとタイル座標を指定する方式です。[詳細やそれぞれの値を決める方法についてはこちら](https://maps.gsi.go.jp/development/siyou.html)をご覧ください。

