Дерево поиска называют такое дерево, что для ∀ узла, узлы левее не более, чем сам узел, а справа строго больше

Задача
Пусть T - бинарное дерево поиска.  Поиск ключа закчанвичающийся в листе (необязательно удачно)
Пусть $A\subset V$ те, что находятся левее пути поиска. Пусть $B\subset V$ - на пути поиска. Пусть $C\subset V$ - правое. Покажите или опровергните что $\forall a\in A$ $\forall b\in B$  $\forall b\in B$  $\forall b\in C$ $a\leq b\leq c$


St В преднем, если вставлять элемент рандомно, то в сред глубина ~1.386 lg n
St Если биранрно ровно вероятно случай, то в среднем поиск работает на $O(\sqrt{n}$
h(v) - глубина поддерева с корменм v
Def AVL назовём такое g n, что $\forall v\in V$ у которой есть дети $v_{r},v_{l}$
$|h(v_{l})-h(v_{r})|\leq f$


Task
$f\equiv1$, найдите минимум
$f(x)=|x-1|$
Пусть $a_{1}, a_{2}, \dots,a_{n}\in\mathbf{R}$ - различное число $f(l,r,x)=\sum_{k=l}^{r}|a_{k}-x|$
$\min\limits_{x\in R}f(l,r,x)$ за $O(n^2\log n)$


Шаг 1
Пусть $x^*$ - точка экстремума
Считаем что l и r - зафиксированны
$\exists\Delta^*>0$ $\forall|\Delta|<\Delta^*$ -> $f(l,r,x^*+\Delta)\geq f(l,r,x)$
Пусть $|\Delta<\Delta^*|$
![[Pasted image 20260930191635.png]]
Пусть $\sigma$ $a_{\sigma(1)}<a_{\sigma(2)}<a_{\sigma(3)}<a_{\sigma(n)}$


$f(l, r, x^*+\Delta)=f(l,r,x^*)-R\Delta+L\Delta\leq f(l,r,x^*+\Delta)-R\Delta+L\Delta$
$f(l,r,x^*+\Delta)\leq f(l,r,x^*+\Delta-R\Delta+L\Delta)$
$L\Delta-R\Delta\geq_{0}$
$L\geq R$
$f(l,r,x^*+\Delta)=f(l,r,x^*)=R\Delta-L\Delta\leq f(l,r,x^*+\Delta)+R\Delta-L\Delta$
$R\Delta-L\Delta\geq_{0}$
$L\geq R\geq L\implies L=R$
$x^*$-медиана

Шаг 2
Пусть $l\leq r$
$a_{l},a_{l+1},\dots,a_{r}$
$$f(l,r,x)=\sum_{k=l}^r|a_{k-x}|=\sum_{a<x}|a_{k}-x|+\sum_{a_{k}>x}|a_{k}-x|=\sum_{a_{k}<x}-(a_{k}-x)+\sum_{a_{k}>x}+(a_{k}-x)=\sum_{a_{k}<x}(x-a_{k})+\sum_{a_{k}>x}(a_{k}-x)=\sum(a_{k}<x)-\sum_{a_{k}<x}a_{k}+\sum_{a_{k}>x}a_{k}-\sum_{a_{k}>x}x=xa^--A^- +A^+ -xa^+$$
$A^-$ - сумма левого
$A^+$ - сумма правого


$a^-,A^-$ - сумму элементов $<x^*$
$a^+,A^+$ - сумму элементов $>x^*$

$A^- +=$
$a^- +=$


for l in {1, ..., n}:
	инициализируем дерево T {a_l}
	for r in {l, ..., n}:
		T.insert(a_r) # O(log n)
		Считаем минимум по формуле # O(log n)
Вмесго за O(n^2 log n)
