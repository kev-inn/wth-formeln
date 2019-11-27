# Formeln WTH

## Allgemeines

$f^X (x)=(F^X(x))‘$, $\int_{-\infty}^{\infty}f(x)dx=1$, ……Dichtefunktion 

PMF (Probability Mass Function) ist anscheinend diskret, also P(X=x)=f(x)

$F(x)$ …………………Verteilungsfunktion (CDF Cumulative Distribution Function) sowohl diskret als auch stetig

Binomialkoeffizient: ${N \choose k} = \frac{N!}{k!\cdot (N-k)!}$

Kleiner Gauß: $\sum_{k=0}^{n} k = \frac {n(n+1)} 2$

Geometrische Reihe: $\sum_{k=0}^{n} q^k = \frac {q^{n+1}-1} {q-1}$
$\text{bei } q<1, \lim_{n \to \infty} \Rightarrow \frac 1 {1-q}$

[Mengenlehre.tif](Zusammenfassungen\Mengenlehre.tif) 

## Diskrete Verteilungen

$X \sim Unif(\Omega)$

$F^X(x) = \sum p_k$

### Hypergeometrisch

$X \sim H_{W,S}$

Ziehe $n$ mal ohne Zurücklegen mit $N_1$ weißen und N gesamt Kugeln

$P(|\text{weiß}|=k)=\frac {\binom {N_1} k \binom {N-N_1}{n-k}} {\binom N n}, k \in \{0,...,n\}$

### Binomial

$X \sim B_{n,p}$

Ziehe n mal mit Zurücklegen mit $N_1$ weißen und $N$ gesamt Kugeln und $p=\frac {N_1} N$

$P(|\text{weiß}|=k)=\binom n k p^k (1-p)^{n-k}, k \in \{0, …, n\}$

### (Multinomial)

Ziehe $n$ mal mit Zurücklegen, mit $N_1$ Kugeln der Farbe 1, $N_2$ der Farbe 2 usw. und $N$ gesamt

$P(|\text{Farbe } i| = k_i) = \frac {\frac {n!} {\prod (k_i!)} \cdot \prod (N_i)} {N^n}$

### Poisson

$X \sim P_{\lambda}$

Mit Zurücklegen, Anzahl der Ziehungen $n \to \infty$, relative Häufigkeit der weißen $p \to 0$, $np \to \lambda >0$

$P(|\text{weiss}|=k)=\frac {\lambda^k e^{-\lambda}} {k!}$

### Geometrisch

$X \sim G_{p}$

Mit zurücklegen, Anzahl der Ziehungen bis eine weiße Kugel gezogen wird

$P(|\text{Versuche}|=k) = p(1-p)^{k-1}$

## Stetige Verteilungen

### Gleichverteilt

$X \sim \text{Unif}(a,b)$

$f(x) = \begin{cases} \frac{1}{b-a} &\mbox{falls } a \leq x \leq b \\ 0 & \mbox{sonst} \end{cases}$

$F(x) = \begin{cases} 0 &\mbox{falls } x < a \\ \frac{x-a}{b-a} &\mbox{falls } a \leq x \leq b \\ 1 & \mbox{falls } x>b \end{cases}$

### Exponentialverteilt

$X \sim \text{Exp}(\lambda)$

$f(x) = \begin{cases} \lambda \cdot e ^{-\lambda x}, & x \geq 0 \\ 0, & x<0\end{cases}$

$F(x) = \begin{cases} 1 – e^{-\lambda x}, & x \geq 0 \\ 0, & x<0\end{cases}$

### Normalverteilt

$X \sim \text{N}(\mu, \sigma^2)$

$f(x) = \phi_{\mu, \sigma^2}(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \cdot e^{\left( – \frac{(x-\mu)^2}{2\sigma^2} \right)}$

$F(x) = \Phi_{\mu, \sigma^2}(x) =\int_{-\infty}^t \phi_{\mu, \sigma^2}(t) dt$

$Z = \frac{X-\mu}{\sigma}$, $P(Z \leq z) = P(Z> -z) = 1-P(Z\leq -z)$

## Zufallsvektoren

Für PMF: $P(X=x, Y=y)=f(x,y), x_{min} \leq x \leq x_{max}, y_{min} \leq y \leq y_{max}$

### Diskret

$\sum_{x_{min}}^{x_{max}}\sum_{y_{min}}^{y_{max}}f(x,y)=1$

$P(X=x)=f(x)=\sum_{y_{min}}^{y_{max}}f(x,y)$

$P(X\leq x_1, Y\leq y_1)=F^{XY}(x,y)=\sum_{x_{min}}^{x_1}\sum_{y_{min}}^{y_1}f(x,y)$

### Stetig

$\int_{x_{min}}^{x_{max}}\int_{y_{min}}^{y_{max}}f(x,y)dydx=1$

$f^Y(y)=\int_{x_{min}}^{x_{max}}f(x,y)dx$

$P(X\leq x_1, Y\leq y_1)=F^{XY}(x_1,y_1)=\int_{x_{min}}^{x_{1}}\int_{y_{min}}^{y_{1}}f(x,y)dydx$

$P(Y\leq y_1)=F^Y(y)=F(x_{max}, y_1) = P(X\leq x_{max}, Y\leq y_1)$

$P(X\leq x_1 \text{oder } Y \leq y_1) = P(X\leq x_1) + P(Y \leq y_1) - P(X \leq x_1, Y \leq y_1)$

## Bedingte Wahrscheinlichkeiten

$P(A|B) = \frac {P(A) \cdot P(B|A)} {P(B)}$

$P(A \cap B)= P(A|B) \cdot P(B)$

$P(B_k|A) = \frac {P(B_k)P(A|B_k)} {\sum P(B_i)P(A|B_i)}$

## Momente

### Erwartungswert

**Diskret allgemein:**

$\mu = E(X)=\sum x_i P(X=x_i)$,

$E(g(x))=\sum g(x_i) P(X=x_i)$

$E(X,Y)=\sum_k \sum_l x_k y_l P(X=x_k, Y=y_l)$

**Binomial:** $E(X) = np$

**Poisson:** $E(x)=\lambda$

**Geometrisch:** $E(x)=\frac 1 p$

**Stetig:**

$E(X)= \int_{-\infty}^{\infty} x f^X(x)dx$

$E(g(X))= \int_{-\infty}^{\infty} g(x) f^X(x)dx$

$E(X,Y) ) = \int \int xyf(x,y)dx dy$

**Exponential:** $E(X)=\frac 1 \lambda$

**Normal:** $E(X)=\mu, E(X^2)=\mu ^2 + \sigma ^2$

### Varianz

$\sigma^2 =\text{Var}(X))=E((x-\mu)^2)=E(X^2)-E(X)^2$

**Gleich:** $\sigma^2 = \frac {(b-a)^2} {12}$

**Exponential:** $\sigma^2=\frac 1 {\lambda^2}$

**Normal(0,1):** $\sigma^2 = 1$

### Kovarianz

$\text{Cov}(X, Y) = E((X-\mu_x)(Y-\mu_y))=E(X,Y)-E(X)E(Y)$

**Korrelation:** $-1 \leq \text{Corr}(X,Y)=\frac {\text{Cov(X,Y)}} {\sqrt{\text{Var}(x)}\cdot \sqrt{\text{Var(}y)}} \leq 1$

### Konvergenz

$\sqrt n \frac {\overline X_n-\mu} \sigma \to N(0,1)$
