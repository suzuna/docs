# 作ったもの

- [東京23区の賃貸マンションの家賃相場を階層ベイズで推定する（2024年12月版）](https://suzuna.me/posts/rent-modeling-update/) [R, Stan]
  - 約60万件のSUUMOの家賃データを用いて、階層ベイズモデルで東京23区の賃貸マンション物件の家賃相場をモデリングしました。築年数、駅からの徒歩分数、部屋の階数による家賃への影響を推定するとともに、最寄り駅別の家賃相場の推定値を示しました。
- [TOPIXのボラティリティをStochastic Volatilityモデル + R + Stanで推定する](https://suzuna.me/posts/stochastic-volatility-model/) [R, Stan]
  - Stochastic Volatilityモデルという非線形な状態空間モデルをStanで実装することで、TOPIXのボラティリティを推定しました。
- [Realized Volatilityの理論と実装](https://suzuna.me/posts/realized-volatility/) [Python]
  - ボラティリティの推定量であるRealized Volatilityについて、簡単に解説するとともに原論文に沿って実装しました。
