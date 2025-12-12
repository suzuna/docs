# 作ったもの

- [t分布を用いたロバストな家賃相場の階層ベイズモデリング](https://suzuna.me/posts/robust-rent-modeling/) [R, Stan]
  - 約60万件の家賃データを用いて、東京23区の賃貸マンション物件の家賃相場を階層ベイズモデルでモデリングしました。家賃データに観測される外れ値に対応するため誤差項にt分布を用いたモデルを実装したところ、正規分布のモデルよりもドメイン知識に整合的な結果が得られ、汎化性能が高まりました。
- [多変量確率的ボラティリティモデルで相関係数の時変性をとらえる](https://suzuna.me/posts/multivariate-stochastic-volatility-model/) [Python, Stan]
  - 資産間のリターンの相関係数は時変性を持ちます。これに対応するため、多変量確率的ボラティリティモデルという非線形な状態空間モデルをStanで実装しました。TOPIXと東証REIT指数の相関係数の時変性を示すことができました。
- [Realized Volatilityの理論と実装](https://suzuna.me/posts/realized-volatility/) [Python]
  - ボラティリティの推定量であるRealized Volatilityについて、簡単に解説するとともに原論文に沿って実装しました。為替介入があった日に、ドル円の価格に大きなジャンプが発生したことが分かりました。
