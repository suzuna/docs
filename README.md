# 作ったもの

## データ分析

- [東京23区の賃貸マンションの家賃相場を階層ベイズで推定する（2024年12月版）](https://suzuna.me/posts/rent-modeling-update/) [R, Stan]
  - 約60万件のSUUMOの家賃データを用いて、階層ベイズモデルで東京23区の賃貸マンション物件の家賃相場をモデリングしました。築年数、駅からの徒歩分数、部屋の階数による家賃への影響を推定するとともに、最寄り駅別の家賃相場の推定値を示しました。
- [カルマンフィルタで株式のベータ値を推定する](https://suzuna.me/posts/stock-beta/) [Python]
  - 個別株式のリスクの大きさを示す指標の一つである「ベータ値」は、日経平均株価のような市場全体の指数の値動きに対する個別株式の値動きの大きさです。カルマンフィルタをフルスクラッチで実装することでベータ値を推定しました。
- [Realized Volatilityの理論と実装](https://suzuna.me/posts/realized-volatility/) [Python]
  - ボラティリティの推定量であるRealized Volatilityについて、簡単に解説するとともに原論文に沿って実装しました。

## Webアプリ

デプロイしているGoogle Cloud環境のコールドスタートのため、初回起動時に数十秒かかることがあります。

- [「カルマンフィルタで株式のベータ値を推定する」の分析をWebアプリにしたもの](https://dev-streamlit-s5ootw75ka-an.a.run.app/)（リポジトリ: [suzuna/stock-beta-app](https://github.com/suzuna/stock-beta-app)）
  - 銘柄コードを入力すると、カルマンフィルタでのベータ値推定を行います。
  - ※ただし、無料で使用できる株価のデータソースが株式分割・併合に対応していないため、2018年以降に株式分割・併合が行われた銘柄では正しいベータ値の推定値となりません。
  - 技術構成 [Python, IaC: Terraform, 開発環境: Docker]
    - StreamlitのWebアプリからFastAPIの推論APIをリクエストしています。
    ![architecture_stock-beta-app](./architecture/architecture_stock-beta-app.drawio.svg)
