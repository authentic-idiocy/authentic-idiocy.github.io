---
layout: post
title: "O CAPM! My CAPM!"
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "wish me luck on my interview RIP"
---

<div class="legend-cheatsheet">
  <h2 class="legend-heading">Legend</h2>
  <table>
    <tr><th>Notation</th><th>Description</th></tr>
    <tr><td>\(r_P\)</td><td>Portfolio excess return</td></tr>
    <tr><td>\(r_M\)</td><td>Market excess return</td></tr>
    <tr><td>\(\mu_P\)</td><td>Expected excess return of portfolio \(P\)</td></tr>
    <tr><td>\(\mu_M\)</td><td>Expected market excess return</td></tr>
    <tr><td>\(i_F\)</td><td>Risk-free rate (interest)</td></tr>
    <tr><td>\(\beta_P\)</td><td>Beta of portfolio \(P\) (w.r.t. benchmark/market)</td></tr>
    <tr><td>\(\theta_P\)</td><td>Residual (idiosyncratic) return of \(P\)</td></tr>
    <tr><td>\(\omega_P\)</td><td>Residual (idiosyncratic) risk (stdev) of \(P\)</td></tr>
    <tr><td>\(h\)</td><td>Holdings / weights vector</td></tr>
    <tr><td>\(V\)</td><td>Covariance matrix of asset returns</td></tr>
    <tr><td>\(f\)</td><td>Vector of expected excess returns</td></tr>
    <tr><td>\(\mu\)</td><td>“CAPM vector” (as used in notes)</td></tr>
    <tr><td>\(e\)</td><td>All-ones vector (full-investment exposure)</td></tr>
    <tr><td>\(C\)</td><td>Fully-invested minimum-variance (GMV) portfolio</td></tr>
    <tr><td>\(q\)</td><td>Fully-invested maximum-Sharpe (tangency) portfolio</td></tr>
    <tr><td>\(B\)</td><td>Benchmark portfolio</td></tr>
  </table>
</div>

<div class="assumptions-block">
  <h2 class="assumptions-heading">Assumptions</h2>
  <ol>
    <li>Risk‑free rate exists</li>
    <li>First and second moments exist</li>
    <li>No fully-invested zero-risk portfolio</li>
    <li>Fully-invested minimum-risk portfolio \(C\) has positive expected excess return</li>
  </ol>
</div>

<div class="flashcard">
  <details>
    <summary>The Whole is Other than the Sum of Its Parts (but not really)</summary>
    <div class="back">
      <p><strong>Setup.</strong> Portfolio \(P\) and market \(M\) with excess returns \(r_P, r_M\).</p>

      <p><em>Regression form (time series):</em></p>

      \[
      r_P(t)=\alpha_P+\beta_P\,r_M(t)+\varepsilon_P(t),\qquad t=1,\ldots,T.
      \]

      <p><em>Arithmetic decomposition (definition):</em></p>

      \[
      \theta_P \;:=\; r_P-\beta_P r_M \quad\Rightarrow\quad r_P=\beta_P r_M+\theta_P.
      \]

      <p><em>Orthogonality (pure regression geometry):</em></p>

      \[
      \operatorname{Cov}(\theta_P,r_M)=\operatorname{Cov}(r_P-\beta_P r_M,\,r_M)
      =\operatorname{Cov}(r_P,r_M)-\beta_P \operatorname{Var}(r_M)=0.
      \]

      <p><em>Variance split:</em></p>

      \[
      \operatorname{Var}(r_P)=\beta_P^{2}\operatorname{Var}(r_M)+\omega_P^{2},
      \qquad \omega_P^{2}:=\operatorname{Var}(\theta_P).
      \]

      <p><small>
        Notes: \((\hat\alpha_P,\hat\beta_P)\) from historical OLS summarize the past; \(\beta\) itself is forward-looking. By convention the market has \(\beta=1\) and the risk-free asset has \(\beta=0\). No CAPM assumptions needed—this is straight regression algebra.
      </small></p>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Risky Business</summary>
    <div class="back">
      <p><strong>CAPM assertion.</strong> Define the residual (specific) return \(\theta_P := r_P - \beta_P r_M\). CAPM adds the condition</p>

      \[
      \mathbb{E}[\theta_P]=0 \quad \text{for every asset/portfolio } P.
      \]

      <p><strong>Implication for expected returns (excess-return form).</strong></p>

      \[
      \mu_P := \mathbb{E}[r_P] \;=\; \beta_P\,\mu_M,
      \qquad \mu_M := \mathbb{E}[r_M].
      \]

      <p><strong>Total-return (SML) form.</strong></p>

      \[
      \mathbb{E}[R_P] \;=\; i_F + \beta_P\,\mu_M
      \quad\text{(straight line in \((\beta,\mathbb{E}[R])\) with intercept \(i_F\) and slope \(\mu_M\)).}
      \]

      <p><strong>Intuition (risk-premia view).</strong> Markets only pay a <em>risk premium</em> for risk that can’t be diversified away. 
      Systematic risk is the market’s risk; your \(\beta_P\) measures how strongly you load on it. 
      Idiosyncratic (residual) risk can be diversified, so its price is zero—hence \(\mathbb{E}[\theta_P]=0\).</p>

      <p><strong>Impact (what this means in practice).</strong></p>
      <ol>
        <li><em>Diversifiable risk gets no paycheck.</em> Taking more residual risk doesn’t raise \(\mathbb{E}[R]\); only a higher \(\beta\) does.</li>
        <li><em>Cost of capital via SML.</em> Given \(\beta_P\), the required return is \(i_F+\beta_P\mu_M\). This is the hurdle rate for valuation/DCF.</li>
        <li><em>Performance evaluation.</em> Under CAPM, expected alpha is zero. Persistent positive alpha implies mispricing/model failure (or genuine skill).</li>
        <li><em>Portfolio tilts.</em> Want higher expected return? Increase exposure to market risk (\(\beta\uparrow\)). 
            Hedge assets with \(\beta<0\) lower expected excess return but can reduce total variance.</li>
        <li><em>Market-wide accounting.</em> Value-weighted residuals net to (about) zero across the market; CAPM strengthens this by setting each asset’s <em>expected</em> residual to zero.</li>
      </ol>

      <p><small>Notation: \(i_F\) risk-free rate; \(r_M\) market excess return; \(\mu_M=\mathbb{E}[r_M]\) market risk premium; \(\beta_P\) beta of \(P\) vs. the market.</small></p>
    </div>
  </details>
</div>

