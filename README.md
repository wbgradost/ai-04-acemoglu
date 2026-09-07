# AI, Human Cognition and Knowledge Collapse

Acemoglu, Kong, and Ozdaglar (2026), *AI, Human Cognition and Knowledge Collapse*, NBER Working Paper 34910. This repository uses the [MIT PDF dated May 5, 2026](https://economics.mit.edu/sites/default/files/2026-05/AI%2C%20Human%20Cognition%20and%20Knowledge%20Collapse%2005-05-26.pdf), 69 pages.

## Question and environment

Can more accurate agentic AI improve decisions today yet undermine the human learning that replenishes collective knowledge? Each date has a continuum of short-lived, atomistic agents. Agent (i) must predict a common state \(\theta_t\) (general knowledge, useful throughout her community) and an iid idiosyncratic state \(\theta_{i,t}\) (knowledge specific to her current context). The common state follows a random walk, so old knowledge loses relevance unless new cohorts replenish it.

Before seeing her private signals, the agent chooses learning effort \(e_{i,t}\geq0\), taking the inherited public precision \(X_t\), agentic-AI precision \(\tau_A\), and all technologies and prices as given. Effort creates two signals at once: a private signal about \(\theta_{i,t}\) with precision \(\lambda_I e_{i,t}\), and a thin public signal about \(\theta_t\) with precision \(\lambda_G e_{i,t}\). The latter is aggregated across the island and benefits future cohorts, but an atomistic agent does not internalize that contribution. AI supplies another private signal about \(\theta_{i,t}\) with precision \(\tau_A\). Hence individual posterior precision is

\[
Y_{i,t}=\sigma^{-2}+\lambda_I e_{i,t}+\tau_A \qquad\text{(equation 4, p. 13).}
\]

Public precision \(X_t=\operatorname{Var}(\theta_t\mid\mathcal I_t)^{-1}\) is the stock of general knowledge. With symmetric island effort \(E_t\), it evolves by the Kalman recursion

\[
X_{t+1}^{-1}=(X_t+\lambda_G E_t)^{-1}+\Sigma^2
\qquad\text{(equation 3, p. 13).}
\]

## Agent's problem and Observation 1

Output is \(f(a_G,a_I)\), where each binary argument records whether the corresponding prediction is within one unit of the truth. Define

\[
\Delta_G=f(1,0)-f(0,0),\quad
\Delta_I=f(0,1)-f(0,0),\quad
\Delta_X=f(1,1)-f(1,0)-f(0,1)+f(0,0).
\]

The normalization is \(\Delta_G+\Delta_I+\Delta_X=1\). **Assumption 1** imposes \(\Delta_I=0\) and \(\Delta_X>0\): context-specific knowledge has no standalone value and the two kinds of knowledge are strictly complementary (p. 9). Bayesian predictions are posterior means (equation 5, p. 13). Writing \(G(\tau)=2\Phi(\sqrt\tau)-1\) and \(g=G'\), the within-period problem is

\[
\max_{e\geq0}\; f(0,0)+G(X_t)\Delta_G
+G(X_t)G(\sigma^{-2}+\lambda_Ie+\tau_A)\Delta_X
-\frac{\varepsilon}{\varepsilon+1}e^{(\varepsilon+1)/\varepsilon}
\qquad\text{(equation 6, p. 14).}
\]

Its first-order condition is

\[
\Delta_XG(X_t)\lambda_Ig(\sigma^{-2}+\lambda_Ie+\tau_A)=e^{1/\varepsilon}
\qquad\text{(p. 15).}
\]

The left side falls in effort because \(g'(\tau)=-\tfrac12(1+\tau^{-1})g(\tau)<0\); marginal cost rises, so the optimum is unique (interior for \(X_t>0\), and \(e=0\) at \(X_t=0\)). Differentiating the marginal payoff—not merely asserting signs—gives Observation 1:

\[
U_{eX}=\Delta_X\lambda_Ig(X_t)g(Y_{i,t})>0,
\qquad
U_{e\tau_A}=\Delta_XG(X_t)\lambda_Ig'(Y_{i,t})<0.
\]

Thus general knowledge complements effort: it raises the payoff from improving the context-specific prediction. Agentic AI substitutes for effort: it supplies the same type of precision and diminishing returns to precision reduce the marginal value of learning. The strict signs use positive precisions, \(\lambda_I>0\), and Assumption 1; the zero-knowledge boundary is the corner described above.

## Dynamic result and welfare

In symmetric equilibrium \(E_t=I e(X_t,\tau_A)\), so AI precision \(\uparrow\) \(\Rightarrow\) effort \(\downarrow\) \(\Rightarrow\) new general knowledge \(\downarrow\) \(\Rightarrow X_{t+1}\downarrow\) \(\Rightarrow\) future effort \(\downarrow\) (equations 7--8, p. 16). When effort supply is inelastic enough (\(\varepsilon<4\)), zero knowledge is unstable and every \(X_1>0\) converges to the high-knowledge steady state (Proposition 3). When \(\varepsilon>4\), zero is locally stable; below the endogenous threshold \(\tau_A^c\), initial knowledge selects between collapse and the high state, while above \(\tau_A^c\) the zero-knowledge state is uniquely and globally stable (Proposition 5, pp. 21--22).

Welfare is not generally increasing in AI accuracy. At the high steady state, higher \(\tau_A\) gives a direct gain in idiosyncratic precision but an indirect loss through lower \(\bar X_h\) (p. 26). Under Assumption 2, \(\sigma^{-2}\geq\sqrt2-1\), welfare is single-peaked: Proposition 10 covers \(\varepsilon<4\); Proposition 11 covers \(\varepsilon>4\) and adds the discontinuous fall to zero after \(\tau_A^c\) (p. 27). By contrast, welfare is strictly increasing in aggregation capacity \(I\) whenever the high-knowledge steady state exists (Proposition 9, p. 25).

`hand/observation-1-foc.jpg` is pending. It will contain the handwritten FOC and the two cross-partials above; no synthetic handwriting is included.
