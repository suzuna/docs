# 作ったもの

## データ分析

- [東京23区の賃貸マンションの家賃相場を階層ベイズで推定する（2024年12月版）](https://suzuna.me/posts/rent-modeling-update/)
  - 約60万件のSUUMOの家賃データを用いて、階層ベイズモデルで東京23区の賃貸マンション物件の家賃相場をモデリングしました。築年数、駅からの徒歩分数、部屋の階数による家賃への影響を推定するとともに、最寄り駅別の家賃相場を示すことができました。
  - 実装: R, Stan
- [カルマンフィルタで株式のベータ値を推定する](https://suzuna.me/posts/stock-beta/)
  - 日経平均株価のような市場全体の値動きの大きさに対する個別株式の値動きの大きさである「ベータ値」を、状態空間モデルで定式化してフルスクラッチ実装のカルマンフィルタで推定しました。
  - 実装: Python
- [TOPIXのボラティリティをStochastic Volatilityモデル + R + Stanで推定する](https://suzuna.me/posts/stochastic-volatility-model/)
  - TOPIXのボラティリティを、Stochastic Volatilityモデルという非線形な状態空間モデルをStanで実装することで推定しました。
  - 実装: R, Stan

## Webアプリ

デプロイしているGoogle Cloud環境のコールドスタートのため、初回起動時に数十秒かかることがあります。ご容赦ください。

- [Time-Varying Beta Chart](https://dev-streamlit-s5ootw75ka-an.a.run.app/)（ソースコード: [suzuna/stock-beta-app](https://github.com/suzuna/stock-beta-app)）
  - 「[カルマンフィルタで株式のベータ値を推定する](https://suzuna.me/posts/stock-beta/)」の分析をWebアプリ化しました。
  - 銘柄コードを入力すると、カルマンフィルタでのベータ値推定を行います。
    - ※無料で使用できる株価のデータソースが株式分割・併合に対応していない都合上、2018年以降に株式分割・併合が行われた銘柄ではベータ値が正しく推定できません。
  - 技術構成 (Python, IaC: Terraform, 開発環境: Docker)
    ![architecture_stock-beta-app](./architecture/architecture_stock-beta-app.drawio.svg)
- [ニコニコ動画の再生数の推移を見られるWebアプリ](https://dev-frontend-n2jb3odbgq-an.a.run.app/)）（[アーキテクチャの解説記事](https://suzuna.me/posts/nicolog/)）
  - ニコニコ動画の各動画の日次の再生数を見られるWebアプリを作成しました。
  - ニコニコ動画のAPI経由で毎日再生数を取得してBigQueryに格納しています（リリースから2年の2024/9時点で20億行, 200GB）。このテーブルにWebアプリからクエリをかけられるようにしています。
  - 技術構成 (Python, R, IaC: Terraform)
    ![architecture_nicolog-backend](./architecture/architecture_nicolog.drawio.svg)
  - （参考）アーキテクチャの解説記事
    - [ニコニコ動画の再生数の推移を見られるWebアプリを作った](https://suzuna.me/posts/nicolog/)
