---
layout: post
title: "O CAPM! My CAPM!"
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "wish me luck on my interview RIP"
---

<div class="legend-cheatsheet">
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
