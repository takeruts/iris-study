# タイトル
## サブタイトル

文章の中に $x$ のように数式も入れられます。

- エネルギーと質量には $E = mc^2$ の関係がある。

ドルマーク2つで囲えば行全体に、
1つで囲めば文中に数式が書けます。

$$
f'(x) = \frac{d f(x)}{d x} = \lim_{\Delta x \to 0} \frac{f(x+\Delta x) - f(x)}{\Delta x}
$$

$f(x) = x^2$ として
$$
\begin{align}
f'(x) = \frac{dx^2}{dx} &=& \lim_{\Delta x \to 0} \frac{(x+\Delta x)^2 - x^2}{\Delta x} \\
&=&  \lim_{\Delta x \to 0} \frac{(x^2+2x\Delta x + \Delta x^2) - x^2}{\Delta x} \\
&=&  \lim_{\Delta x \to 0} \frac{2x\Delta x + \Delta x^2}{\Delta x} \\
&=&  \lim_{\Delta x \to 0} 2x + \Delta x \\
&=&  2x \\
\end{align}
$$
