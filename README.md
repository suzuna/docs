# つくったものの置き場

データ分析レポートなどのリンクを以下に示します。

- [カルマンフィルタで株式のベータ値を推定する](https://suzuna.me/posts/stock-beta/)
  - マーケット全体と比べた個別株式の値動きの大きさを示す「ベータ値」を、線形・ガウスな状態空間モデルで定式化してカルマンフィルタで推定しました。
  - 実装: Python
    - カルマンフィルタはnumpyとscipyを用いてスクラッチで書いています。
- [Time-Varying Beta Chart](https://dev-streamlit-s5ootw75ka-an.a.run.app/)
  - 上の分析結果をWebアプリ化しました。銘柄コードを入力すると株価の取得とカルマンフィルタでのベータ値推定を行い結果を表示します。
  - 技術構成は以下の通りです。
    - カルマンフィルタの推定（バックエンド）: FastAPI (Python) + Cloud Run + Artifact Registry (Docker)
    - Webアプリ（フロントエンド）: Streamlit (Python) + Cloud Run + Artifact Registry (Docker)
    - IaC: Terraform
    - 開発環境: Dockerで構築
  - ソースコードはこちらをご覧ください。-> [suzuna/stock-beta-app](https://github.com/suzuna/stock-beta-app)
- [TOPIXのボラティリティをStochastic Volatilityモデル + R + Stanで推定する](https://suzuna.me/posts/stochastic-volatility-model/)
  - Stochastic Volatilityモデルという非線形な状態空間モデルをMCMCで解くことでTOPIXのボラティリティを推定しました。
  - 実装: R, Stan
- [階層ベイズで東京23区のお部屋の家賃相場を推定する](https://suzuna.me/posts/rent-modeling/)
  - 東京23区の20万件程度の賃貸物件の家賃データを用いて、最寄り駅、面積、築年数、最寄り駅からの徒歩分数をもとに家賃相場を階層ベイズで推定しました。
  - 実装: R, Stan
