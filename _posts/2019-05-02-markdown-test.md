---
title: # Achievable Rate Analysis of Opportunistic Transmission in Bursty Interference Networks (2018. 04. 25)
key: 20170707
tags: TeXt
mathjax: true
mathjax_autoNumber: true
---

When $$a \ne 0$$, there are two solutions to $$ax^2 + bx + c = 0$$ and they are

$$x_1 = {-b + \sqrt{b^2-4ac} \over 2a}$$

$$x_2 = {-b - \sqrt{b^2-4ac} \over 2a} \notag$$

<!--more-->

You need set `mathjax: true` in the *_config.yml* or the markdown’s front matter to **enable** it.
{:.warning}

**After MathJax enabled**, you can set `mathjax_autoNumber: true` to have equations be numbered automatically, You can use `\notag` or `\nonumber` to prevent individual equations from being numbered.
{:.info}

[Documentation](https://tianqi.name/jekyll-TeXt-theme/docs/en/markdown-enhancements#mathjax)

**markdown:**

```tex
When $$a \ne 0$$, there are two solutions to $$ax^2 + bx + c = 0$$ and they are
$$x_1 = {-b + \sqrt{b^2-4ac} \over 2a}$$
$$x_2 = {-b - \sqrt{b^2-4ac} \over 2a} \notag$$
```

## System Model

We consider the $K$-user bursty fading interference channel which consists of $K$ transmitter(TX) – receivers(RX) pairs.

We assume that each TX or RX is equipped with a single antenna and assume the block fading channel where channel coefficients remain constant during one transmission block (e.g., one frame) and independently changes over every transmission block.

The term $h_{ij}$ denotes the wireless channel coefficient from the $j$-th TX to the $i$-th RX and it is assumed to be an independent but non-identically distributed (i.n.d.) complex Gaussian random variable with zero mean and different variances.

To be specific, $h_{ij} \sim \mathcal{CN}(0,1)$ for $j \neq i$ and $h_{ii} \sim \mathcal{CN}(0, \sigma_i^2)$ with $\sigma_i^2 \ge 1$, where $i, j \in \mathcal{K} \overset{\Delta}{=} \{1, \cdots, K\}$.

Thus, the desired channel gain is larger than the interference channel gains, which is realistic in the sense that the TX–RX pair is determined based on the distance between them in general

Therefore, the received signal at the $i$-th RX is given by

$$r_i = b_i \sqrt{P_i} h_{ii} s_i + \sum_{j\in \mathcal{K}\setminus i} b_j \sqrt{P_j}h_{ij}s_j + z_i,$$

where $P_j$ and $s_j$ denote the transmit power and the desired symbol of the $j$-th transmitter, respectively.

In this letter, we assume that $P_j = P$, and $\mathbb{E}[|s_j|^2] = 1$ for all $j$.

$z_i$ denotes the circular symmetric complex additive white Gaussian noise with zero mean and variance of $N_0$, i.e., $z_i \sim \mathcal{CN} (0, N_0)$.

Let $\rho  \buildrel \Delta \over = \frac{P}{N_0}$.

The term $b_j \in \{0,1\}$ indicates the transmission state of the $j$-th TX, which is equal to 1 or 0 for an active state or a non-active state, respectively.

Let $\alpha_j$ be the probability that the $j$-th TX is active.

Then, $\alpha_j$ denotes the probability that the $j$-th TX sends data to the $j$-th RX, which is modeled by a Bernoulli random variable, $b_j \sim \text{Bern}(\alpha_j)$.

In this letter, we assume that all TXs have the same active probability, i.e., $\alpha_j = \alpha$ for all $j$

By using the channel reciprocity of time division duplexing (TDD) system, we assume the local channel state information (CSI) for all TXs and RXs as, which implies the $j$-th TX knows $h_{ij}$ for all $i$.

We also assume that there is no central scheduler to control data transmission of TXs, and thus each TX determines data transmission based on its local CSI in a distributed manner.

## Achievable Rate Analysis

We mathematically analyze the achievable rates of three different transmission techniques in a bursty fading interference channel: random transmission (RT) and two proposed opportunistic transmission techniques (OT-1 and OT-2).

For a given active probability $\alpha$, in the RT technique, each TX sends data with the probability $\alpha$ without consideration of channel states.

In the OT-1 technique, each TX sends data only when all generating interference gain is lower than a certain threshold.

In the OT-2 technique, each TX sends data only when its desired channel gain to its corresponding RX is larger than a certain threshold.

The overall procedure of the three transmission techniques are summarized as follows:

First, each TX determines whether it sends data to the corresponding RX or not based on its activation probability and local CSI.

Second, active TXs send a request-to-send (RTS) packet as in IEEE 802.11 specifications, and the corresponding RX computes the received signal-to-interference ratio (SINR) value.

Third, the RXs that receive the RTS packet from its corresponding TX send clear-to-send (CTS) packet, where the CTS packet includes their received SINR information.

Finally, each active TX sends its data packet with a proper data- rate to the corresponding RX, based on the received SINR information.

Let $\mathcal{B} = \{j | b_j = 1,j \in \mathcal{K}\}$ denote the index set of the active TXs and $n = |\mathcal{B}|$. Without loss of generality, we focus on the achievable rate of the first TX–RX pair, i.e., $1 \in \mathcal{B}$.

Then, for a given $n$, the average achievable rate of the first TX–RX pair is expressed as:

$${R_n}\left( {\frac{1}{\rho }} \right) = \mathbb{E}\left[ {{{\log }_2}\left( {1 + \frac{{{{\left| {{h_{11}}} \right|}^2}}}{{\tfrac{{{I_n}}}{P} + \tfrac{1}{\rho }}}} \right)} \right]$$

where ${I_n} = {\sum _{j \in \mathcal{B},j \ne 1}}{\left| {{h_{1j}}} \right|^2}P$ and $I_1 = 0$

$R_n\left(\frac{1}{\rho}\right)$ depends on $n$.

Then, by averaging on $n$, the average achievable rate of the first TX–RX pair is obtained as:

$${R_{avg}}\left( {\frac{1}{\rho }} \right) = \sum\limits_{n = 0}^{K - 1}
{\left( {\begin{array}{*{20}{c}}
  {K - 1} \\
  n
\end{array}} \right)
{\alpha ^{n + 1}}{{\left( {1 - \alpha } \right)}^{K - n - 1}}{R_{n + 1}}} \left( {\frac{1}{\rho }} \right)$$

In the following subsections, we analyze the achievable rate
for a given n for three different transmission techniques.

Then, the average achievable rate for each transmission technique is obtained by plugging it into.

### Random Transmission (RT)

In the RT technique, $b_j$ of the $j$-th TX is determined as:

$${b_j} = \left\{ {\begin{array}{*{20}{c}}
  1&{{\text{with probability }}\alpha } \\
  0&{{\text{with probability 1 - }}\alpha }
\end{array}} \right.$$

When $n = 1$, there is no interference and the achievable rate of the RT technique is given by

$$\begin{align*}
{R_1^{{\text{RT}}}} \left( {\frac{1}{\rho }} \right) &= \int_0^\infty  {{{\log }_2}\left( {1 + x\rho } \right){f_X}^{RT}(x)dx} = \frac{{{\exp\left(\tfrac{\lambda }{\rho } \right) } {E_1}\left( {\tfrac{\lambda }{\rho }} \right)}}{{\ln 2}}\\
\end{align*}$$

>$$\begin{align*}
 \int_0^\infty  {{\log }_2}\left( {1 + x\rho } \right){f_X}^{RT}(x)dx &= \int_0^\infty {{\log }_2 \left( {1 + x\rho } \right) \lambda e^{−\lambda x}dx}= \left[ {\frac{{{e^{ - \lambda x}}\ln \left( {1 + x\rho } \right) - {e^{\frac{\lambda }{\rho }}}{E_1}\left( {\lambda \left( {x + \frac{1}{\rho }} \right)} \right)}}{{\ln 2}}} \right]_0^\infty\\
&= \int_{0}^{\infty} \frac{\rho e^{-\lambda x}}{(1+x\rho)\ln2} dx = \frac{1}{\ln2} \int_{0}^{\infty} \frac{\rho e^{-\lambda x}}{(1+x\rho)} dx\\
&= \frac{1}{\ln2} \int_{1}^{\infty} \frac{e^{\left(\tfrac{-\lambda t+\lambda}{\rho} \right)}}{t} dt = \frac{1}{\ln2} \int_{1}^{\infty} \frac{e^{-\tfrac{\lambda t}{\rho}} e^{\tfrac{\lambda}{\rho}}}{t} dt\\
&= \frac{e^{\tfrac{\lambda}{\rho}}}{\ln2} \int_{\tfrac{\lambda}{\rho}}^{\infty} \frac{e^{-x}}{x} dx = \frac{e^{\tfrac{\lambda}{\rho}} {E_1}\left( {\tfrac{\lambda }{\rho }} \right)}{\ln2}
\end{align*}$$

where $X$ represents the random variable (RV) denoting the desired channel gain and its probability density function (PDF) is given as $f^\text{RT}_X(x) = \lambda e^{−\lambda x}$, where $\lambda  = \frac{1}{\sigma^2_i}$.

For the first TX–RX, $\lambda = \frac{1}{\sigma^2_1}$.

$E_1(x)$ denotes the exponential integral function which is defined as $\int_x^\infty e^{-t}t^{-1} dt$

When $n = 2$, there are two active users in the network and one interferer exists.

The achievable rate of the RT scheme for $n = 2$ is expressed as follows:

$$\begin{align*}
R_2^{{\text{RT}}}\left( {\frac{1}{\rho }} \right){\text{ }} &= \int_0^\infty  {\int_0^\infty  {{{\log }_2}\left( {1 + \frac{x}{{y + \tfrac{1}{\rho }}}} \right)f_{XY}^{RT}(x,y)dxdy} }\\
&= \int_0^\infty  {R_1^{RT}\left( {\tfrac{1}{\rho } + y} \right)f_Y^{RT}\left( y \right)dy} \\
&= \frac{{{E_1}\left( {\tfrac{1}{\rho }} \right)\exp \left( {\tfrac{1}{\rho }} \right) - {E_1}\left( {\tfrac{\lambda }{\rho }} \right)\exp \left( {\tfrac{\lambda }{\rho }} \right)}}{{\left( {\lambda  - 1} \right)\ln 2}} \\
&= \frac{{{E_1}\left( {\tfrac{1}{\rho }} \right)\exp \left( {\tfrac{1}{\rho }} \right)}}{{\left( {\lambda  - 1} \right)\ln 2}} - \frac{1}{{\left( {\lambda  - 1} \right)}}R_1^{RT}\left( {\tfrac{1}{\rho }} \right)
\end{align*} $$

>$$\begin{align*}
>\int_0^\infty  {R_1^{RT}\left( {\tfrac{1}{\rho} + y} \right)f_Y^{RT}\left( y \right)dy} &= \int_0^\infty  {\frac{{{e^{\lambda\left(\tfrac{1 }{\rho }+y\right)}}{E_1}\left( {\lambda\left(\tfrac{1 }{\rho }+y\right)} \right)}e^{-y}}{{\ln 2} } dy} \\
>&= \frac{e^{\tfrac{\lambda}{\rho}}}{\ln2} \int_0^\infty  {{{e^{(\lambda -1)y}}{E_1}\left( {\lambda\left(\tfrac{1 }{\rho }+y\right)} \right)} dy}\\
>&= \frac{e^{\tfrac{\lambda}{\rho}}}{\ln2} \left(-{\frac{ E_1 \left(\tfrac{\lambda}{\rho} \right)} {{\lambda  - 1}}}  + \frac{e^{\left( {-\tfrac{\lambda}{\rho}} \right)} e^{\tfrac{1}{\rho}} E_1 \left( \frac{1}{\rho}\right)}{\lambda  - 1}\right) \\
>&= \frac{{{E_1}\left( {\tfrac{1}{\rho }} \right)\exp \left( {\tfrac{1}{\rho }} \right) - {E_1}\left( {\tfrac{\lambda }{\rho }} \right)\exp \left( {\tfrac{\lambda }{\rho }} \right)}}{{\left( {\lambda  - 1} \right)\ln 2}} 
>\end{align*}$$
>where
>$$\begin{align*}
>\int_0^\infty  {{{e^{(\lambda -1)y}}{E_1}\left( {\lambda\left(\tfrac{1 }{\rho }+y\right)} \right)} dy} &= \left[ {{E_1}\left( {\lambda \left( {\frac{1}{\rho } + y} \right)} \right)\frac{{{e^{(\lambda  - 1)y}}}}{{\lambda  - 1}}} \right]_0^\infty  + \frac{{{e^{\left( { - \tfrac{\lambda }{\rho }} \right)}}}}{{\lambda  - 1}}\int_0^\infty  {\frac{{{e^{ - y}}}}{{\tfrac{1}{\rho } + y}}dy} \\
>&=  -{\frac{ E_1 \left(\tfrac{\lambda}{\rho} \right)} {{\lambda  - 1}}}  + \frac{e^{\left( {-\tfrac{\lambda}{\rho}} \right)}}{{\lambda  - 1}} \int_0^\infty  {\frac{{{e^{-y}}}}{{{\tfrac{1}{\rho } + y}}}dy}\\
>&=  -{\frac{ E_1 \left(\tfrac{\lambda}{\rho} \right)} {{\lambda  - 1}}}  + \frac{e^{\left( {-\tfrac{\lambda}{\rho}} \right)} e^{{\tfrac{1}{\rho }}}}{{\lambda  - 1}} \int_{0}^\infty  {\frac{{{e^{-\left(\tfrac{1}{\rho } + y\right)}}}}{{{\tfrac{1}{\rho } + y}}}dy}\\
>&=  -{\frac{ E_1 \left(\tfrac{\lambda}{\rho} \right)} {{\lambda  - 1}}}  + \frac{e^{\left( {-\tfrac{\lambda}{\rho}} \right)} e^{\tfrac{1}{\rho}} E_1 \left( \frac{1}{\rho}\right)}{\lambda  - 1} 
>\end{align*}$$
>where $u = {E_1}\left( {\lambda \left( {\frac{1}{\rho } + y} \right)} \right)$, $du =  - \frac{{{e^{-\lambda \left( {\tfrac{1}{\rho } + y} \right)}}}}{{\tfrac{1}{\rho } + y}}dy$, $dv = {e^{\left( {\lambda  - 1} \right)y}}dy$ and $v = \frac{e^{(\lambda-1)y}}{\lambda-1}$

where $Y$ indicates the RV denoting the interference channel gain, i.e., $f^{RT}_Y(y) = e^{−y}$ for $y \ge 0$, and $f^{RT}_{XY} (x, y)$ denotes a joint PDF with $X$ and $Y$.

Since all channel coefficients are independent, $f^{RT}_{XY} (x, y) = f^{RT}_X(x)f^{RT}_Y(y)$.



Interestingly, for $n \ge 3$, $R^{RT}_n(\rho)$ can be rewritten as:

$$\begin{align*}
R_n^{RT}\left( {\frac{1}{\rho }} \right) &= \int_0^\infty  {R_{n - 1}^{RT}\left( {\tfrac{1}{\rho } + y} \right){e^{ - y}}dy} \\
&= \frac{1}{{\left( {\lambda  - 1} \right)\ln 2}}{B_n}\left( {\frac{1}{\rho }} \right) - \frac{1}{{\left( {\lambda  - 1} \right)}}R_{n - 1}^{RT}\left( \rho  \right)\\
\end{align*}$$

where $B_n\left(\frac{1}{\rho}\right)$ represents integral of $E_1(y)$.

>$$\begin{align*}
>R_3^{RT}\left( {\frac{1}{\rho }} \right) &= \int_0^\infty  {R_{2}^{RT}\left( {\tfrac{1}{\rho } + y_1} \right){e^{ - y_1}}dy_1} \\
>&= \int_0^\infty  {\left(\frac{{{E_1}\left( {\tfrac{1}{\rho } + y_1} \right) e^{\tfrac{1}{\rho } + y_1}}}{{\left( {\lambda  - 1} \right)\ln 2}} - \frac{1}{{\left( {\lambda  - 1} \right)}}R_1^{RT}\left( {\tfrac{1}{\rho } + y_1} \right) \right) e^{ - y_1} dy_1}\\
>&= \int_0^\infty  {\frac{{{E_1}\left( {\tfrac{1}{\rho } + y_1} \right) e^{\tfrac{1}{\rho }}}}{{\left( {\lambda  - 1} \right)\ln 2}} - \frac{1}{{\left( {\lambda  - 1} \right)}}R_1^{RT}\left( {\tfrac{1}{\rho } + y_1} \right) e^{ - y_1}  dy_1}\\
>&= \frac{{e^{\tfrac{1}{\rho }}}}{{\left( {\lambda  - 1} \right)\ln 2}} \int_0^\infty  {{E_1}\left( {\tfrac{1}{\rho } + y_1} \right) dy_1} - \frac{1}{{\left( {\lambda  - 1} \right)}} \int_0^\infty  {R_1^{RT}\left( {\tfrac{1}{\rho } + y_1} \right) e^{ - y_1}  dy_1}\\
>&= \frac{{e^{\tfrac{1}{\rho }}}}{{\left( {\lambda  - 1} \right)\ln 2}} \int_0^\infty  {{E_1}\left( {\tfrac{1}{\rho } + y_1} \right) dy_1} - \frac{1}{{\left( {\lambda  - 1} \right)}} {R_2^{{\text{RT}}}}\left( \frac{1}{\rho } \right) \\
>\end{align*}$$
>
>$$\begin{align*}
>R_4^{RT}\left( {\frac{1}{\rho }} \right) &= \int_0^\infty  {R_{3}^{RT}\left( {\tfrac{1}{\rho } + y_2} \right){e^{ - y_2}}dy_2} \\
>&= \int_0^\infty  {\left(\frac{{e^{\tfrac{1}{\rho } + y_2}}}{{\left( {\lambda  - 1} \right)\ln 2}} \int_0^\infty  {{E_1}\left( {\tfrac{1}{\rho } + y_2 + y_1} \right) dy_1} - \frac{1}{{\left( {\lambda  - 1} \right)}} {R_2^{{\text{RT}}}}\left( \frac{1}{\rho } + y2 \right) \right) {e^{ - y_2}}dy_2} \\
>&= {\frac{{e^{\tfrac{1}{\rho }}}}{{\left( {\lambda  - 1} \right)\ln 2}} \int_0^\infty \int_0^\infty  {{E_1}\left( {\tfrac{1}{\rho } + y_2 + y_1} \right) dy_1 dy_2} - \frac{1}{{\left( {\lambda  - 1} \right)}} \int_0^\infty {R_2^{{\text{RT}}}}\left( \frac{1}{\rho } + y2 \right) {e^{ - y_2}}dy_2} \\
>&= {\frac{{e^{\tfrac{1}{\rho }}}}{{\left( {\lambda  - 1} \right)\ln 2}} \int_0^\infty \int_0^\infty  {{E_1}\left( {\tfrac{1}{\rho } + y_2 + y_1} \right) dy_1 dy_2} - \frac{1}{{\left( {\lambda  - 1} \right)}}} R_3^{RT}\left( {\frac{1}{\rho }} \right)
>\end{align*}$$

$B_n\left(\frac{1}{\rho}\right)$ can be obtained as:

$$\begin{align*}
{B_n}\left( {\frac{1}{\rho }} \right) &= \underbrace {\int_0^\infty  { \cdots \int_0^\infty  {} } }_{n - 1}{E_1}\left( {\frac{1}{\rho } + \sum\limits_{m = 1}^{n - 1} {{y_m}} } \right)d{y_1} \cdots d{y_{n - 1}}\\
 &=  {\frac{{{E_1}\left( {\tfrac{1}{\rho }} \right)\exp \left( {\tfrac{1}{\rho }} \right)}}{{{{\left( { - \rho } \right)}^{n - 1}}}} + \sum\limits_{m = 0}^{n - 2} {\frac{{m!}}{{{{\left( { - \rho } \right)}^{n - 2 - m}}}}} } \\
\end{align*}$$

Then,

$$\begin{align*}
R_{n+1}^{RT}\left( {\frac{1}{\rho }} \right) + \frac{R_{n}^{RT}\left( \rho  \right)}{{\left( {\lambda  - 1} \right)}} &= \frac{1}{{\left( {\lambda  - 1} \right)\ln 2}}{B_{n+1}}\left( {\frac{1}{\rho }} \right)\\
\end{align*}$$

### Opportunistic Transmission based on Generating Interference (OT-1)

As noted before, in the OT-1 technique, $b_j$ of the $j$-th TX is determined as:

$${b_j} = \left\{ {\begin{array}{*{20}{c}}
  1&{{\text{if }}{y_{ij}} < \eta ,\quad \forall i \ne j} \\
  0&{{\text{otherwise}}}
\end{array}} \right.$$

where $y_{ij} \triangleq |h_{ij}|^2$ denotes the generating interference gain from the $j$-th TX to the $i$-th RX and $\eta$ denotes a certain threshold.

The activation probability at the TX is given as $\alpha = (1 − e^{−\eta})^{K−1}$.

For a given activation probability, the threshold is given as $\eta = −\ln \left(1-\alpha^{\frac{1}{K-1}} \right)$.

For $n = 1$, since there is no interference, the achievable rate of the OT-1 technique is the same as that of the RT technique, i.e., $R^{OT-1}_1 = R^{RT}_1 \triangleq \beta(1)F_1(\tfrac{1}{\rho})$ where $\beta(n)$ is represented as constant term.

For $n = 2$, the achievable rate of the OT-1 technique is given by:

$$\begin{align*}
R_2^{OT - 1}\left( {\frac{1}{\rho }} \right) &= \int_0^\eta  {R_1^{OT - 1}\left( {\frac{1}{\rho } + y} \right){f_Y}} (y)dy \\
&= \frac{{\exp \left( {\frac{1}{\rho }} \right)}}{{\left( {1 - {e^{ - \eta }}} \right)\left( {\lambda  - 1} \right)\ln 2}}\left[ {{E_1}\left( {\lambda \left( {\tfrac{1}{\rho } + \eta } \right)} \right)\exp \left( {(\lambda  - 1)\left( {\tfrac{1}{\rho } + \eta } \right)} \right) - {E_1}\left( {\frac{\lambda }{\rho }} \right)\exp \left( {\frac{{\lambda  - 1}}{\rho }} \right) - {E_1}\left( {\frac{1}{\rho } + \eta } \right) + {E_1}\left( {\frac{1}{\rho }} \right)} \right] \\
&\triangleq \frac{{\beta (2)}}{{\lambda  - 1}}\left( {{H_2}\left( {\frac{1}{\rho } + \eta } \right) - {H_2}\left( {\frac{1}{\rho }} \right)} \right)
\end{align*}$$

where $f_Y(y)$ denotes the PDF of $Y$ which is given as:

$$f_Y^{OT - 1}(y) = \left\{ {\begin{array}{*{20}{c}}
  {{e^{ - \tfrac{y}{{1 - {e^{ - \eta }}}}}}}&{{\text{if }}0 \leqslant y < n} \\
  0&{{\text{otherwise}}}
\end{array}} \right.$$

>$$\begin{align*}
>\int_0^\eta  {R_1^{OT - 1}\left( {\frac{1}{\rho } + y} \right){f_Y}} (y)dy &= \int_0^\eta  {R_1^{RT}\left( {\frac{1}{\rho } + y} \right){f_Y}} (y)dy\\
>&= \int_0^\eta {\frac{{{e^{\lambda\left(\frac{1 }{\rho }+y\right)}}{E_1}\left( {\lambda\left(\frac{1 }{\rho }+y\right)} \right)} \frac{e^{-y}}{1-e^{-\eta}} }{{\ln 2} }  dy} \\
>&= \frac{{{e^{\frac{\lambda }{\rho }}}}}{{\left( {1 - {e^{ - \eta }}} \right)\ln 2}}\int_0^\eta  {{e^{(\lambda  - 1)y}}{E_1}\left( {\lambda \left( {\frac{1}{\rho } + y} \right)} \right)dy} \\
>&= \frac{{{e^{\frac{\lambda }{\rho }}}}}{{\left( {1 - {e^{ - \eta }}} \right)\ln 2}}\left( {\left. {\frac{{{E_1}\left( {\lambda \left( {\tfrac{1}{\rho } + y} \right)} \right){e^{(\lambda  - 1)y}}}}{{\lambda  - 1}}} \right]_{y = 0}^\eta  + \int_0^\eta  {\frac{{{e^{ - \lambda \left( {\tfrac{1}{\rho } + y} \right)}}{e^{(\lambda  - 1)y}}}}{{\left( {\tfrac{1}{\rho } + y} \right)\left( {\lambda  - 1} \right)}}dy} } \right) \\
>&= \frac{{{e^{\frac{\lambda }{\rho }}}}}{{\left( {1 - {e^{ - \eta }}} \right)\ln 2}}\left( {\frac{{{E_1}\left( {\lambda \left( {\tfrac{1}{\rho } + \eta } \right)} \right){e^{(\lambda  - 1)\eta }}}}{{\lambda  - 1}} - \frac{{{E_1}\left( {\lambda \left( {\tfrac{1}{\rho }} \right)} \right)}}{{\lambda  - 1}} + \frac{{{e^{ - \tfrac{\lambda }{\rho }}}}}{{\left( {\lambda  - 1} \right)}}\int_0^\eta  {\frac{{{e^{ - y}}}}{{\tfrac{1}{\rho } + y}}dy} } \right) \\
>&= \frac{{{e^{\frac{\lambda }{\rho }}}}}{{\left( {1 - {e^{ - \eta }}} \right)\ln 2}}\left( {\frac{{{E_1}\left( {\lambda \left( {\tfrac{1}{\rho } + \eta } \right)} \right){e^{(\lambda  - 1)\eta }}}}{{\lambda  - 1}} - \frac{{{E_1}\left( {\lambda \left( {\tfrac{1}{\rho }} \right)} \right)}}{{\lambda  - 1}} + \frac{{{e^{ - \tfrac{\lambda }{\rho }}}}}{{\left( {\lambda  - 1} \right)}}\left[ { - {e^{\frac{1}{\rho }}}{E_1}\left( {\frac{1}{\rho } + y} \right)} \right]_0^\eta } \right) \\
>&= \frac{{{e^{\frac{\lambda }{\rho }}}}}{{\left( {1 - {e^{ - \eta }}} \right)\left( {\lambda  - 1} \right)\ln 2}}\left( {{e^{(\lambda  - 1)\eta }}{E_1}\left( {\lambda \left( {\tfrac{1}{\rho } + \eta } \right)} \right) - {E_1}\left( {\tfrac{\lambda }{\rho }} \right) - {e^{\tfrac{1}{\rho }\left( {1 - \lambda } \right)}}{E_1}\left( {\frac{1}{\rho } + \eta } \right) + {e^{\tfrac{1}{\rho }\left( {1 - \lambda } \right)}}{E_1}\left( {\frac{1}{\rho }} \right)} \right) \\
>&= \frac{1}{{\left( {1 - {e^{ - \eta }}} \right)\left( {\lambda  - 1} \right)\ln 2}}\left( {{e^{\lambda \left( {\frac{1}{\rho } + \eta } \right)}}{e^{ - \eta }}{E_1}\left( {\lambda \left( {\tfrac{1}{\rho } + \eta } \right)} \right) - {e^{\frac{\lambda }{\rho }}}{E_1}\left( {\tfrac{\lambda }{\rho }} \right) - {e^{\tfrac{1}{\rho }}}{E_1}\left( {\frac{1}{\rho } + \eta } \right) + {e^{\tfrac{1}{\rho }}}{E_1}\left( {\frac{1}{\rho }} \right)} \right) \\
>&= \frac{{{e^{\frac{1}{\rho }}}}}{{\left( {1 - {e^{ - \eta }}} \right)\left( {\lambda  - 1} \right)\ln 2}}\left( {{e^{\left( {\lambda  - 1} \right)\left( {\frac{1}{\rho } + \eta } \right)}}{E_1}\left( {\lambda \left( {\tfrac{1}{\rho } + \eta } \right)} \right) - {e^{\frac{{\lambda  - 1}}{\rho }}}{E_1}\left( {\tfrac{\lambda }{\rho }} \right) - {E_1}\left( {\frac{1}{\rho } + \eta } \right) + {E_1}\left( {\frac{1}{\rho }} \right)} \right)
\end{align*}$$

where $R^{OT-1}_n\left(\frac{1}{\rho} \right) \triangleq \beta(n) F_n(\frac{1}{\rho})$, $H(y)$ is function of integral $F(y)$, i.e., $H_{n+1}(\frac{1}{\rho}+y) \triangleq \int_0^\eta H_n(\frac{1}{\rho} + y)dy = \int_0^\eta F_n\left(\frac{1}{\rho}+y\right)-G_n\left(\frac{1}{\rho}+y\right)$.

$G_1\left(\frac{1}{\rho}\right)$ is represented as $E_1\left(\frac{1}{\rho} \right)$ and $\beta (2) \triangleq \frac{{\exp \left( {\tfrac{1}{\rho }} \right)}}{{\left( {1 - {e^{ - \eta }}} \right)\ln 2}}$.

For a general $n \ge 3$ the function of $F_n(\frac{1}{\rho})$ of the OT-1 technique is obtained recursively as:

$${F_{n + 1}}\left( {\frac{1}{\rho }} \right) = \frac{1}{{\lambda  - 1}}\left( {{F_n}\left( {\frac{1}{\rho } + \eta } \right) - {F_n}\left( {\frac{1}{\rho }} \right) - {G_n}\left( {\frac{1}{\rho } + \eta } \right) + {G_n}\left( {\frac{1}{\rho }} \right)} \right)$$


$G_n \left(\frac{1}{\rho}\right)$ is defined as:

$$\begin{align*}
G_n \left(\frac{1}{\rho}\right) &= \underbrace {\int_0^\eta  { \cdots \int_0^\eta} }_{n - 1}{E_1}\left( {\frac{1}{\rho } + \sum\limits_{m = 1}^{n - 1} {{y_m}} } \right)d{y_1} \cdots d{y_{n - 1}} \\
&= \sum\limits_{m = 0}^{n - 1} {\frac{{{{( - 1)}^{n - 1 - m}}}}{{(n - 1 - m)!m!}}\left( {{E_1}\left( {\frac{1}{\rho } + m\eta } \right){{\left( {\frac{1}{\rho } + m\eta } \right)}^{n - 1}} - \exp \left( { - \left( {\frac{1}{\rho } + m\eta } \right)} \right)\sum\limits_{l = 0}^{n - 2} {(n - 2 - l)!{{\left( {\frac{1}{\rho } + m\eta } \right)}^l}{{( - 1)}^{n - 2 - l}}} } \right)}
\end{align*}$$

Fanally, $R_{AVG}^{OT-1}\left(\frac{1}{\rho}\right)$ is obtained

$R_1^{OT - 1}\left( {\frac{1}{\rho }} \right) = \frac{{{e^{\tfrac{\lambda }{\rho }}}{E_1}\left( {\tfrac{\lambda }{\rho }} \right)}}{{\ln 2}} $

$R_2^{OT - 1}\left( {\frac{1}{\rho }} \right) = \frac{{{e^{\frac{1}{\rho }}}}}{{\left( {1 - {e^{ - \eta }}} \right)\left( {\lambda  - 1} \right)\ln 2}}\left( {\int_0^\eta  {{f_2}\left( {\frac{1}{\rho } + y} \right) - {g_2}\left( {\frac{1}{\rho } + y} \right)dy} } \right) $

$R_3^{OT - 1}\left( {\frac{1}{\rho }} \right) = \frac{{{e^{\frac{1}{\rho }}}}}{{{{\left( {1 - {e^{ - \eta }}} \right)}^2}\left( {\lambda  - 1} \right)\ln 2}}\int_0^\eta  {\int_0^\eta  {{f_3}\left( {\frac{1}{\rho } + y} \right) - {g_3}\left( {\frac{1}{\rho } + y} \right)dy} } d{y_1} $

$\vdots $

$R_n^{OT - 1}\left( {\frac{1}{\rho }} \right) = \frac{{{e^{\frac{1}{\rho }}}}}{{{{\left( {1 - {e^{ - \eta }}} \right)}^{n - 1}}\left( {\lambda  - 1} \right)\ln 2}}\int_0^\eta  { \cdots \int_0^\eta  {{f_n}\left( {\frac{1}{\rho } + y} \right) - {g_n}\left( {\frac{1}{\rho } + y} \right)dy} }  \cdots d{y_{n - 2}}  $

$\int_0^\eta  {{f_n}\left( {\frac{1}{\rho } + y} \right)dy}  = \left. {{F_n}\left( {\frac{1}{\rho } + y} \right)} \right]_{y = 0}^\eta $

${F_n}\left( {\frac{1}{\rho }} \right) = {F_{n - 1}}\left( {\frac{1}{\rho } + \eta } \right) $, ${F_2}\left( {\frac{1}{\rho }} \right) = {e^{\left( {\lambda  - 1} \right)\frac{1}{\rho }}}{E_1}\left( {\frac{\lambda }{\rho }} \right) $

$\int_0^\eta  {{g_n}\left( {\frac{1}{\rho } + y} \right)dy}  = \left. {{G_n}\left( {\frac{1}{\rho } + y} \right)} \right]_{y = 0}^\eta $

${G_n}\left( {\frac{1}{\rho }} \right) = {G_{n - 1}}\left( {\frac{1}{\rho } + \eta } \right) $, ${G_2}\left( {\frac{1}{\rho }} \right) = {E_1}\left( {\frac{1}{\rho }} \right)$

### Opportunistic Transmission based on Desired Channel Gain (OT-2)

In the OT-2 technique, bj of the j-th TX is determined as:

$${b_j} = \left\{ {\begin{array}{*{20}{c}}
  1&{{\text{if }}{x_{j}} < \zeta } \\
  0&{{\text{otherwise}}}
\end{array}} \right.$$

where $x_j \triangleq |h_{jj}|^2$ denotes the instantaneous channel gain from the $j$-th TX to the $j$-th RX and $\zeta$ is a threshold which is determined as a system parameter.

Then, the activation probability at each transmitter in the OT-1 technique becomes a function of $\zeta$, i.e., $\alpha = e^{−\lambda \zeta}$.

For a given activation probability, hence, the threshold is given by $\zeta = −\frac{1}{\lambda} \ln \alpha$.

Different from the OT-1 technique, the OT-2 technique only considers its own desired channel gain. For $n = 1$, the achievable rate of the OT-2 technique is given by

$R_1^{OP - 2}\left( {\frac{1}{\rho }} \right) = \int_\zeta ^\infty  {{{\log }_2}\left( {1 + \rho x} \right)f_X^{OT - 2}\left( x \right)dx} $

$ = \int_\zeta ^\infty  {\frac{{{e^{ - \lambda x}}}}{{{e^{ - \lambda \zeta }}}}{{\log }_2}\left( {1 + \rho x} \right)dx}  = \int_\zeta ^\infty  {{e^{ - \lambda (x - \zeta )}}{{\log }_2}\left( {1 + \rho x} \right)dx} $

$ = \left[ {\frac{{{e^{\lambda \zeta }}\left( { - {e^{\frac{\lambda }{\rho }}}{E_1}\left( {\lambda x + \frac{\lambda }{\rho }} \right) - {e^{ - \lambda x}}\ln \left( {\rho x + 1} \right)} \right)}}{{\lambda \ln 2}}} \right]_\zeta ^\infty $

$ = \frac{{{e^{\lambda \zeta }}\left( {{e^{\frac{\lambda }{\rho }}}{E_1}\left( {\lambda \zeta  + \frac{\lambda }{\rho }} \right) + {e^{ - \lambda \zeta }}\ln \left( {\rho \zeta + 1} \right)} \right)}}{{\lambda \ln 2}} $

$ = \frac{{{e^{\lambda \left( {\zeta  + \frac{1}{\rho }} \right)}}{E_1}\left( {\lambda \zeta  + \frac{\lambda }{\rho }} \right)}}{{\lambda \ln 2}} + \frac{{\ln \left( {\rho \zeta + 1} \right)}}{{\lambda \ln 2}} = \frac{1}{\lambda }\left( {\frac{{{e^{\lambda \left( {\zeta  + \frac{1}{\rho }} \right)}}{E_1}\left( {\lambda \left( {\zeta  + \frac{1}{\rho }} \right)} \right)}}{{\ln 2}} + {{\log }_2}\left( {\rho \zeta  + 1} \right)} \right) $

$ = \frac{1}{\lambda }\left( {R_1^{RT}\left( {\zeta  + \frac{1}{\rho }} \right) + {{\log }_2}\left( {\rho \zeta  + 1} \right)} \right)$

 nv


**front matter:**

    ---
    ...
    mathjax: true
    mathjax_autoNumber: true
    ---
