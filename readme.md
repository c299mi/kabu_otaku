# Kabu Otaku

Kabu Otakuプロジェクトは、東京証券取引所のプライム市場、スタンダード市場、およびグロース市場における銘柄の分析をするためのノートブック集です。

## 環境設定

### 必要なライブラリ

このプロジェクトでは、以下のPythonライブラリを使用しています。

- pandas
- matplotlib
- seaborn
- yfinance

必要なライブラリをインストールするには、以下のコマンドを実行してください。

'''
pip install pandas matplotlib seaborn yfinance
'''

### 日本語フォントの設定

日本語フォントが必要な場合は、システムにインストールされている日本語フォントのパスを設定してください。以下のコード内でフォントのパスを適切に置き換えてください。

'''
jp_font_path = '/usr/share/fonts/truetype/fonts-japanese-gothic.ttf'  # 実際の日本語フォントファイルのパスに置き換えてください
'''

## 使用方法

最初に日本証券所のウェブサイトから全上場銘柄のシートを取得し、`data`ディレクトリ内に`data_j.csv`として保存してください。
日本証券所のウェブサイト: [https://www.jpx.co.jp/markets/statistics-equities/misc/01.html](https://www.jpx.co.jp/markets/statistics-equities/misc/01.html)

### ノートブック

以下のノートブックを順次実行して、データを取得し分析します。

#### `ticker_scraper.ipynb`

日本証券所のウェブサイトより取得した`data_j.csv`から各市場（グロース、スタンダード、プライム）に属する銘柄コードを抽出してCSVファイルに保存するノートブックです。

#### `get_ohlc.ipynb`

`ticker_scraper.ipynb`で取得し保存した各市場の銘柄コードに基づき、銘柄のOHLCデータを取得するノートブックです。例として、東証グロース市場の銘柄の調整後終値データを取得し、`growth_adj_close_20240101_20240531.csv`として保存しています。

#### `growth_analysis.ipynb`

`get_ohlc.ipynb`で取得した調整後終値データを用いて、東証グロース市場のデータを分析するノートブックです。同様にして東証プライム市場と東証スタンダード市場のデータを分析を行ってください。

### プロジェクトのディレクトリ構造

'''
kabu_otaku/
├── data/
│   ├── data_j.csv
│   ├── growth_tickers.csv
│   ├── standard_tickers.csv
│   ├── prime_tickers.csv
│   └── growth_adj_close_20240101_20240531.csv
├── ticker_scraper.ipynb
├── get_ohlc.ipynb
└── growth_analysis.ipynb
'''

### ノートブックの実行手順

各ノートブックを順次開き、セルを上から順に実行。

    - `ticker_scraper.ipynb` を実行して銘柄コードを抽出し保存します。
    - `get_ohlc.ipynb` を実行して銘柄のOHLCデータを取得し保存します。
    - `growth_analysis.ipynb`、`prime_analysis.ipynb`、`standard_analysis.ipynb` を実行してデータを分析します。


