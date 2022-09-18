# IE242 HW 1 solution
## 1.
Let $\hat{\beta_1}$ and $\hat{\beta_2}$ respectively denote the least squares estimatros of $\beta_1$ and $\beta_2$ .<br/>
We can transform the equations for $Y_{1j},\; Y_{2j}, \;\text{and}\; Y_{3j}$ into a simple linear regression equations, $y_i=\beta_1+\beta_2 x + \epsilon_i$.
$$Y_{1j}=\beta_1+0\cdot \beta_2 +\epsilon_{1j},\;Y_{2j}=\beta_1+1\cdot \beta_2 +\epsilon_{2j},\; Y_{3j}=\beta_1+(-2)\cdot \beta_2 +\epsilon_{3j}$$
Now, We have
$$
\hat{\beta_2}=\frac{S_{yy}}{S_{xx}}=\sum_{i=1}^n a_i y_i ,\;\hat{\beta_1}=\bar{y}-\hat{\beta_2}\bar{x}=\sum_{i=1}^n b_i y_i $$
$$
\text{when}\;n=2n_1+n_2,\;a_i=\frac{x_i-\bar{x}}{S_{xx}},\; b_i=\frac{1}{n}-a_i x
$$
<br/>

Therefore
$$
 Cov(\hat{\beta_1},\hat{\beta_2})=Cov( \sum_{i=1}^n a_i y, \sum_{i=1}^n b_i y)=\sigma^2\sum_{i=1}^n a_i b_i=\sigma^2\sum_{i=1}^n (\frac{1}{n}a_i-a_i^2 \bar{x})=\sigma^2\{\frac{1}{n S_{xx}}\sum_{i=1}^n (x_i-\bar{x}) -\frac{\bar{x}}{S_{xx}}\sum_{i=1}^n(x_i-\bar{x})^2 \} =\frac{-\bar{x}}{S_{xx}}\sigma^2
$$
<br/>

$\hat{\beta_1}$ and $\hat{\beta_2}$ are uncorrelated when $\bar{x}=0$
<br/>

Since $\bar{x}=(0+1)\cdot n_1 -2\cdot n_2=n_1-2n_2$,  $\hat{\beta_1}$ and $\hat{\beta_2}$ are uncorrelated when $n_1=2n_2$ .
<br/>


## 2.
### (a)
$Cov(\hat{\beta_0},\hat{\beta_1})=\cfrac{-\bar{x}}{S_{xx}}\sigma^2 = -\bar{x} \cdot V(\hat{\beta_1})$<br/>

#### Explanation
- Since $\hat{\beta_0}$ is $\hat{E}(y_i \mid x_i=0)$, $Cov(\hat{\beta_0},\hat{\beta_1})$ has reverse sign with $\bar{x}$. 
- $\hat{y}=\hat{\beta_0}+\hat{\beta_1}x$ always go through $(\bar{x},\bar{y})$ $\Rightarrow$  $\hat{\beta_0}=\bar{y}$ is fixed when $\bar{x}=0$  =>  $\hat{\beta_0}$ and $\hat{\beta_1}$ are uncorrelated when $\bar{x}=0$
<br/>

### (b)
By definition, $\hat{\beta_0}$ and $\hat{\beta_1}$ satisfy
$$
\frac{\partial \; SSE}{\partial \beta_0}=-2\{\sum_{i=1}^N(y_i-\hat{\beta_0}-\hat{\beta_1}x_i)\}=0 \cdots (*) \\
\frac{\partial \; SSE}{\partial \beta_1}=-2\{\sum_{i=1}^N x_i (y_i-\hat{\beta_0}-\hat{\beta_1}x_i)\}=0 \cdots (**)
$$
$\sum_{i=1}^N e_i = 0$ by $(*)$
<br/>

$\sum_{i=1}^N x_i e_i = 0$ by $(**)$
<br/>

$\sum_{i=1}^N \hat{y_i} e_i =\sum_{i=1}^N(\hat{\beta_0}+\hat{\beta_1} x_i)e_i=\hat{\beta_0}\sum_{i=1}^N e_i+\hat{\beta_1}\sum_{i=1}^N x_i e_i=0$  by $(*),(**)$

<br/>

### (c)
$Var(\hat{\beta_0})=Var(\bar{y}-\hat{\beta_0}\bar{x})=Var(\bar{y})+\bar{x}^2Var(\hat{\beta_1})-2Cov(\bar{y},\hat{\beta_1})=Var(\bar{y})+\bar{x}^2Var(\hat{\beta_1})$
<br/>

$\Rightarrow Var(\hat{\beta_0})$ becomes minimum if the observations on the predictor variable $x_i,\; i=1,...,N$ are chosen such that $\bar{x}=0$

<br/>

### (d)
Minimizing $Var(\hat{\beta_1})=\cfrac{1}{S_{xx}}\sigma^2$ is the same as Maximizing $S_{xx}$
<br/>
<br/>

Now,
For any constant $C$, we have<br/>
$\sum(x_i-C)^2=\sum x_i^2-2C\sum x_i +N\cdot C^2,\;\; i=1,...,N$<br/>

The above quadratic minimized when $C=\bar{x}$
<br/>

$\Rightarrow\;S_{xx}=\sum_{i=1}^N(x_i-\bar{x})^2\;\leq\;\sum_{i=1}^N(x_i-\frac{a+b}{2})^2\;\leq\; \sum_{i=1}^N(x_i-a)(x_i-b)+\cfrac{(a-b)^2}{4}\;\leq\;\cfrac{(a-b)^2}{4}$
<br/>

If $N/2$ values of the predictor are selected equal to $a$ and the remaining $N/2$ values are chosen to equal to $b$, $S_{xx}=\cfrac{(a-b)^2}{4}$, which is max value of $S_{xx}$
<br/>

$\Rightarrow$ If $N/2$ values of the predictor are selected equal to $a$ and the remaining $N/2$ values are chosen to equal to $b$, $Var(\hat{\beta_1})$ is minimized.


