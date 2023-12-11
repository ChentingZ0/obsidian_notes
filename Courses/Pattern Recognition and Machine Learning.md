- Hidden Markov Model
Hidden state -> observation

- Bayesian Pattern Classification
 $f_{X|S}(x|j)$ , $P_{S}(j)$  ---> $P_{S|X}(j|x)$ (posteior)
 ---> Expected loss $R(i|x)$ over observed vector $x$.

Decision rules:
Choose our discrimate function
1. Minimum-Risk -> minimize $R(i|x)$
2. MAP -> maximize Posterior
3. ML -> maximize  state-observation distribution

- EM algorithm
[[EM, K-means]]