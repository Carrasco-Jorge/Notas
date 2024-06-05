# Distribuciones más comunes y sus propiedades básicas

## Distribuciones discretas

Se dice que una variable aleatoria es discreta si el espacio muestral es *numerable*. En la mayoría de los casos este tipo de variable tiene valores enteros.

### Distribución uniforme

Una variable aleatoria $X$ discreta tiene distribución dicreta uniforme $(1,N)$ si 

$$P(X=x|N) = \frac{1}{N},\quad x=1,2,\dots,N$$

donde $N$ es un entero especificado. Esta distribución le asigna la misma "masa" a cada uno de los posibles resultados del experimento.

- **Media**: $\frac{N+1}{2}$

- **Varianza**: $\frac{(N+1)(N-1)}{12}$

Esta distribución se puede generalizar de modo que el espacio muestral sea cualquier rango de entero $N_0,N_0+1,\dots,N_1$ con

$$
P(X=x|N_0,N_1) = \frac{1}{N_1 - N_0 + 1}
$$

### Distribución hipergeométrica

Esta distribución surge de un experimento del siguiente tipo:

- Supongamos que se tienen $N$ individuos que solo se diferencian en que $M$ tienen un rasgo característico y $N- M$ no (por ejemplo: color rojo, defectuoso, etc.)

- Se seleccionan $K$ individuos de forma aleatoria sin reemplazo

- ¿Cuál es la probabilidad de que exactamente $x$ individuos tengan el rasgo característico?

Una variable aleatoria discreta $X$ tiene distribución hipergeométrica $(N,M,K)$ si

$$
P(X=x|N,M,K)=\frac{\begin{pmatrix} M\\\ x \end{pmatrix}\begin{pmatrix} N-M\\\ K-x \end{pmatrix}}{\begin{pmatrix} N\\\ K \end{pmatrix}}, \quad x=0,1,\dots,K
$$

Así mismo, el rango completo de valores que puede tomar $x$ es

$$
M-(N-K)\leq x\leq M
$$

Aunque generalmente $K\leq M$ y $K\leq N$.

- **Media**: $\frac{KM}{N}$

- **Varianza**: $\frac{KM}{N}\cdot\frac{(N-M)(N-K)}{N(N-1)}$

### Distribución Bernoulli

Una variable aleatoria $X$ se dice que tiene distribución Bernoulli $(p)$ si el espacio muestral es $\{ 0,1 \}$ y

$$
P(X=x|p)=p^x(1-p)^{1-x}
$$

Es decir,

$$
P(X=1|p)=p,\quad P(X=0|p) = 1-p
$$

Donde comunmente el valor $0$ se considera como "fracaso" y el valor $1$ como éxito.

- **Media**: $p$

- **Varianza**: $p(1-p)$

### Distribución binomial

Si una variable aleatoria discreta $X$ se define como el número de éxitos en una secuencia de tamaño $n$ de ensayos o experimentos **independientes** $Y_i$ ~ Bernoulli $(p)$, entonces 

$$X=\sum_{i=1}^nY_i$$

es una variable aleatoria Binomial $(n,p)$ y

$$
P(X=x|n,p)=\begin{pmatrix} n\\\ x \end{pmatrix}p^x(1-p)^{1-x},\quad x=0,1,2\dots,n
$$

- **Media**: $np$

- **Varianza**: $np(1-p)$

### Distribución Poisson

Esta distribución puede utilizarse para modelar el número de eventos que suceden en un intervalo de tiempo definido. Una de las suposiciones esenciales en las que la distribución Poisson se plantea es que, para **intervalos cortos de tiempo**, la probabilidad de que pase un suceso es proporcional al tiempo de espera.

Esta distribución tiene un solo parámetro $\lambda$, el cual a veces es llamado parámetro de *intensidad*. Una variable aleatoria discreta tiene distribución Poisson $(\lambda)$ si

$$
P(X=x|\lambda)=\frac{e^{-\lambda}\lambda^x}{x!},\quad x=0,1,\dots
$$

- **Media**: $\lambda$

- **Varianza**: $\lambda$

### Distribución binomial negativa

Si una variable aleatoria discreta $X$ se define como el número de ensayos o experimentos Bernoulli $(p)$ necesarios para obtener un número fijo $r$ de éxitos, entonces $X$ ~ BinomialNegativa $(r,p)$, donde

$$
P(X=x|r,p)=\begin{pmatrix} x-1\\\ r-1 \end{pmatrix}p^r(1-p)^{x-r},\quad x=r,r+1,\dots
$$

De forma alternativa, este tipo de variable aleatoria se define en términos del $Y=$ número de fracasos antes del $r$-ésimo éxtito. Esta formulación es estadísticamente equivalente a la previamente dada, ya que $Y=X-r$. De este modo

$$
P(Y=y|r,p)=(-1)^y\begin{pmatrix} -r\\\ y \end{pmatrix}p^r(1-p)^y
$$

Esta distribución, así como la distribución [Poisson](#distribución-poisson), se puede utilizar para modelar fenómenos en los que se espera a que ocurran eventos. En este caso, se espera por un número específico de éxitos.

- **Media**: $\mu=\frac{r(1-p)}{p}$

- **Varianza**: $\frac{r(1-p)}{p^2} = \mu + \frac{1}{r}\mu^2$

### Distribución geométrica

La distribución geométrica es un caso especial de la distribución [Binomial Negativa](#distribución-binomial-negativa). Si se elige $r=1$, se obtiene

$$
P(X=x|p)=p(1-p)^{x-1},\quad x=1,2,\dots
$$

Donde $p$ representa la probabilidad de éxito. Esta distribución puede interpretarse como el número de ensayo en el cual se obtiene el primer éxito, es decir, "se espera a que suceda un éxito".

La distribución geométrica tiene la propiedad de **"pérdida de memoria"**, es decir, que

$$
P(X>s|X>t) = P(X>s-t)
$$

Lo cual implica que la probabilidad de observar un "éxito" después de $s-t$ fracasos después de haber observado $t$ fracasos previamente es la misma que observar un "éxito" después de $s-t$ fracasos al inicio de la secuencia.

Para la media y la varianza que se muestran aquí, se toma en cuenta la variable aletoria $X$ definida en la sección [Binomial Negativa](#distribución-binomial-negativa), donde $X=Y+1$.

- **Media**: $\frac{1}{p}$

- **Varianza**: $\frac{1-p}{p^2}$

## Distribuciones continuas

### Distribución uniforme

La distribución uniforme continua está definidaal distribuir la "masa" de manera uniforme en un intervalo $[a,b]$. Su función de densidad de probabilidad es

$$
f(x|a,b)=\frac{1}{b-a},\quad x\in[a,b]
$$
$$
f(x|a,b)=0,\quad x\notin [a,b]
$$

- **Media**: $\frac{b+a}{2}$

- **Varianza**: $\frac{(b-a)^2}{12}$

### Distribución Gamma

- **Media**: 

- **Varianza**: 

#### Distribución Exponencial

- **Media**: 

- **Varianza**: 

### Distribución Normal

- **Media**: 

- **Varianza**: 

### Distribución Beta

- **Media**: 

- **Varianza**: 

### Distribución Cauchy

- **Media**: 

- **Varianza**: 

### Distribución Lognormal

- **Media**: 

- **Varianza**: 

### Distribución Doble(mente) exponencial

- **Media**: 

- **Varianza**: 
