---
title: "釣合旋回まわりの微小擾乱運動方程式"
---
<div style="text-align: right;">
last update 2026/07
</div>

## 背景
模型グライダによるサーマル旋回では，機体は直線飛行ではなく，一定バンク角を保った円旋回を基準状態として飛行する．そのため，直線水平飛行まわりで導出された通常の微小擾乱方程式を，そのままサーマル自動捕捉系の設計に用いることは適切でない．本稿では，横滑りのない釣合旋回を基準状態とし，その近傍における6自由度運動方程式を線形化する．

## 仮定
- 旋回は横滑りなし
- 水平面内の旋回とする（沈下率0）


## 準備

6自由度の運動方程式

$$
\begin{align}
m(\dot{U}+QW-RV) &= -mg \sin{\Theta} + X_a\\
m(\dot{V}+RU-PW) &= mg \cos{\Theta} \sin{\Phi} + Y_a\\
m(\dot{W}+PV-QU) &= mg \cos{\Theta}\cos{\Phi} + Z_a
\end{align}
$$ {#eq-eq1}

$$
\begin{align}
I_{xx}\dot{P}-I_{xz}\dot{R}+(I_{zz}-I_{yy})QR-I_{xz}PQ &= L\\
I_{yy}\dot{Q}+(I_{xx}-I_{zz})RP+I_{xz}(P^2-R^2) &= M\\
-I_{xz}\dot{P}+I_{zz}\dot{R}+(I_{yy}-I_{zz})PQ+I_{xz}QR &= N
\end{align}
$$ {#eq-eq2}

機体角速度
$$
\begin{align}
P &= \dot{\Phi}-\dot{\Psi}\sin{\Theta}\\
Q &= \dot{\Theta}\cos{\Phi}=\dot{\Psi}\sin{\Phi}\cos{\Theta}\\
R &= -\dot{\Theta}\sin{\Phi}+\dot{\Psi}\cos{\Phi}\cos{\Theta}
\end{align}
$$

オイラー角
$$
\begin{align}
\dot{\Phi} &= P+Q\sin{\Phi}\tan{\Theta}+R\cos{\Phi}\tan{\Theta}\\
\dot{\Theta} &= Q\cos{\Phi}-R\sin{\Phi}\\
\dot{\Psi} &= Q\sin{\Phi}\sec{\Theta}+R\cos{\Phi}\sec{\Theta}
\end{align}
$$

## 導出

$X$ 軸方向速度を $U_0$，ピッチ角 $\theta_0 = 0$（水平面内の旋回）として，$Y$ 軸，$Z$ 軸方向速度については定常状態からの変動を考える．バンク角 $\phi_0$，旋回率 $\dot{\psi}_0$ で定常旋回しているとき，釣り合い式

$$
\begin{align}
L\cos{\phi_0} &= mg\\
L\sin{\phi_0} &= mU_0\dot{\psi}_0\\
\dot{\psi}_0 &= \frac{r}{U_0}tan{\phi_0}
\end{align}
$$

角速度の定常値は
$$
\begin{align}
P_0 &= 0\\
Q_0 &= \dot{\psi}_0 \sin{\phi_0}\\
R_0 &= \dot{\psi}_0 \cos{\phi_0}
\end{align}
$$

オイラー角の定常値は
$$
\begin{align}
\Phi_0 &= \phi_0\\
\Theta_0 &= \theta_0 = 0\\
\Psi_0 &= \int \dot{\psi_0} dt
\end{align}
$$

より，定常状態の運動方程式は
$$
\begin{align}
0 &= X_{a0}\\
mR_0 U_0 &= mg\sin{\phi_0} + Y_{a0}\\
-mQ_0 U_0  &= mg \cos{\phi_0} + Z_{a0}
\end{align}
$$

$$
\begin{align}
(I_{zz}-I_{yy})Q_0R_0&= L_0\\
-I_{xz}R_0^2 &= M_0\\
I_{xz}Q_0R_0 &= N_0
\end{align}
$$

運動変数の変化分を小文字で表すと
$$
\begin{align}
U &= U_0 + u\\
V &= v\\
W &= w\\
P &= p\\
Q &= Q_0 + q\\
R &= R_0 + r\\
\Phi &= \phi_0 + \phi\\
\Theta &= \theta\\
\Psi &= \int(\dot{\psi_0}+\dot{\psi})dt\\
X_a &= \Delta X\\
Y_a &= Y_{a0} + \Delta Y\\
Z_a &= Z_{a0} + \Delta Z\\
L &= L_0 + \Delta L\\
M &= M_0 + \Delta M\\
N &= N_0 + \Delta N
\end{align}
$$



## 線形化
オイラー角について，微小角近似すると
$$
\begin{align}
\sin{\Phi} &= \sin{(\phi_0 + \phi)} \approx \sin{\phi_0}+\phi\cos{\phi_0}\\
\cos{\Phi} &= \cos{(\phi_0 + \phi)} \approx \cos{\phi_0}-\phi\sin{\phi_0}\\
\sin{\Theta} &\approx \theta\\
\cos{\Theta} &\approx 1\\
\tan{\Theta} &\approx \theta
\end{align}
$$

式(@eq-eq1)，(@eq-eq2) に代入し，速度，角速度の変化分が積で現れる項を微小として無視すると，釣合旋回まわりの微小擾乱運動方程式を得る．

$$
\begin{align}
m(\dot{u}+Q_0w-R_0v) &= -mg \theta + \Delta X_a\\
m(\dot{v}+R_0u-U_0r) &= mg \cos{\phi_0} \phi + \Delta Y_a\\
m(\dot{w}-Q_0u-U_0q) &= -mg \sin{\phi_0}\phi + \Delta Z_a
\end{align}
$$

$$
\begin{align}
I_{xx}\dot{p}-I_{xz}\dot{r}+(I_{zz}-I_{yy})(Q_0r+R_0q)-I_{xz}Q_0p &= \Delta L\\
I_{yy}\dot{q}+(I_{xx}-I_{zz})R_0p-I_{xz}R_0r &= \Delta M\\
-I_{xz}\dot{p}+I_{zz}\dot{r}+(I_{yy}-I_{zz})Q_0p+I_{xz}(Q_0r+R_0q) &= \Delta N
\end{align}
$$

オイラー角は
$$
\begin{align}
\dot{\phi} &= p+\dot{\psi_0}\theta\\
\dot{\theta} &= q\cos{\phi_0}-r\sin{\phi_0}-\dot{\phi_0}\phi\\
\dot{\psi} &= q\sin{\phi_0}+r\cos{\phi_0}
\end{align}
$$

## 適用範囲
本式は，横滑りのない一定速度・一定バンク角の釣合旋回を基準状態とし，その近傍の運動を微小擾乱として線形化したものである．したがって，姿勢角，速度および角速度の基準状態からの変化が十分小さい範囲で適用できる．

大きな操舵，急激なバンク角の変更，失速付近の飛行，強い横滑りなど，基準状態から大きく外れる運動に対しては，無視した二次以上の項や空力特性の非線形性が無視できなくなる．


## 参考文献
- 加藤寛一郎・大屋昭男・柄沢研治，『航空機力学入門』，東京大学出版会，1985/9/10