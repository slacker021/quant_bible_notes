---
dg-publish: true
---
Let $X \subset \mathbb{R}$ that is nonempty and $m$ be a lower bound of $X$. With that said, assume the following:
$$
-X = \{-x \ | \ x \in A  \} \tag{1}
$$
This implies that 
$$
m \le x \ \forall x \in X \tag{2}
$$
Step 2 can be negated to show that
$$
-m \ge -x \ \forall x \in X \tag{3}
$$
By the axiom of completeness, the supremum of $-X$ is $-m$. By definition, 
$$
\text{sup} (-X) \ge -X \ \forall x \in X \tag{4}
$$
This inequality can be negated:
$$
-1 \cdot (\text{sup}(-X)) \le x \  \forall x \in X \tag{5}
$$
which means that $-1 \cdot (\text{sup}(-X))$ is a lower bound of set $X$. 

Now, suppose that for contradiction's sake that $-1 \cdot (\text{sup}(-X))$ is not the greatest lower bound. Suppose there's a lower bound that's even greater. In symbolic format, this means that 
$$
\exists y > -1 \cdot (\text{sup}(-X)) \text{ with } y \le x \ \forall x \in X \tag{6} 
$$
Multiplying this inequality by $-1$ would show that 
$$
-y < \text{sup}(-X) \tag{7}
$$
Given that the supremum of $-y$ is less than the supremum of $-X$, $-y$ can't be an upper bound because that would contradict the definition of the supremum. Multiplying the statement by $-1$ again shows that 
$$
-y \ge -x \ \forall x \in X \tag{8}
$$
This leads to the conclusion that $-y$ is an upper bound that is greater than the supremum. This is a contradiction because the supremum is the least upper bound. Therefore, $-\text{sup}(-X)$ must be the greatest lower bound of set $X$. 
$$
\textbf{Q.E.D}
$$