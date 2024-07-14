# 作ったもの

## データ分析

- [部屋の階数は家賃にどれだけ影響を与えるのか？](https://suzuna.me/posts/rent-by-floor/)
  - 約12万件の東京23区の賃貸物件のSUUMOの家賃データを用いて、階層ベイズモデルで家賃相場をモデリングしました。
  - 築年数、駅からの徒歩分数、部屋の階数による家賃への影響を推定するとともに、最寄り駅別の家賃相場を示すことができました。
  - 実装: R, Stan
- [カルマンフィルタで株式のベータ値を推定する](https://suzuna.me/posts/stock-beta/)
  - マーケット全体と比べた個別株式の値動きの大きさを示す「ベータ値」を、線形・ガウスな状態空間モデルで定式化してカルマンフィルタ（フルスクラッチで実装）で推定しました。
  - 実装: Python
- [TOPIXのボラティリティをStochastic Volatilityモデル + R + Stanで推定する](https://suzuna.me/posts/stochastic-volatility-model/)
  - TOPIXのボラティリティを、Stochastic Volatilityモデルという非線形な状態空間モデルをStanで実装することで推定しました。
  - 実装: R, Stan

## Webアプリ

各Webアプリは、デプロイしている環境でのコールドスタートのため、初回起動時に数十秒かかることがあります。ご容赦ください。

- [Time-Varying Beta Chart](https://dev-streamlit-s5ootw75ka-an.a.run.app/)
  - 「カルマンフィルタで株式のベータ値を推定する」の分析をWebアプリ化しました。
  - 銘柄コードを入力すると、株価の取得とカルマンフィルタでのベータ値推定を行います。
  - 技術構成 (IaC: Terraform, 開発環境: Docker)
    ![architecture_stock-beta-app](./architecture/architecture_stock-beta-app.drawio.svg)
  - ソースコード: [suzuna/stock-beta-app](https://github.com/suzuna/stock-beta-app)
- [ニコニコ動画の再生数の推移を見られるWebアプリ](https://dev-frontend-n2jb3odbgq-an.a.run.app/)
  - ニコニコ動画の各動画の日次の再生数を見られるWebアプリを作成しました。
  - ニコニコ動画のAPI経由で毎日再生数を取得してBigQueryに格納しています（リリースから2年弱の時点で20億行 x 8列（200GB））。このテーブルにWebアプリからクエリをかけられるようにしています。
  - 技術構成 (IaC: Terraform)
    ![architecture_nicolog-backend](./architecture/architecture_nicolog.drawio.svg)
  - （参考）アーキテクチャの解説記事
    - [ニコニコ動画の再生数の推移を見られるWebアプリを作った](https://suzuna.me/posts/nicolog/)
