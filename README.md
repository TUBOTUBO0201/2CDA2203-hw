# 2CDA2203-hw 線形代数　課題
 
 配布されたCSVファイル（report.csv）を読み込みデータとしてプロットした。
 
# 実行結果

![](https://user-images.githubusercontent.com/109895312/180639965-adac1587-5bc8-41ad-866b-efa273d1fcae.jpg)

# 開発環境
 
* JupiterLab 3.3.2
 
# プログラミングコード
 
```
import numpy as np
from matplotlib import pyplot as plt

# データをcsvから読み込みxyを作成
data = np.loadtxt('report.csv', delimiter=",")
data = data.T
x = data[0]
y = data[1]

# polyfitの次数を1（直線）にしてy=ax+bのa, bを取得
coe = np.polyfit(x, y, 1)

# 回帰直線を生成
y_fit = coe[0] * x + coe[1]

# グラフ描画
fig = plt.figure()
ax = fig.add_subplot(111)
ax.grid()

# データプロット
ax.scatter(x, y, marker = ".")
ax.plot(x, y_fit, color = "red")

# グラフ表示
fig.tight_layout()
plt.show()
plt.close()

print("y =",coe[0],"x","+",coe[1])
```
 
# 学番・氏名・所属
 
* 作成者　2CDA2203　佐藤　壱洸
* 所属　情報理工学部コンピュータ応用工学科
