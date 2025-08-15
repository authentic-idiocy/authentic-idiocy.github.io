---
layout: post
title: "Shut up and Put Your Money Where Your Risk Tolerance Is."
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "A SFW way to ask what you consider a 'gamble' is."
---

<!-- Single Flashcard — G&K Ch.3 (pp.42–46): Summary + Formulas + Derivations -->

<div class="flashcard">
  <details>
    <summary>Risk Metrics — foundations (not Var/Semivariance/Shortfall/VaR)</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>1) What a usable risk measure must satisfy</summary>
        <div class="content">
          <ul>
            <li><strong>Universal & impersonal.</strong> Not investor-specific; works across mandates.</li>
            <li><strong>Symmetric.</strong> Judges up/down moves consistently vs. a benchmark.</li>
            <li><strong>Flexible & aggregable.</strong> Applies to assets and portfolios; composes cleanly.</li>
            <li><strong>Forecastable.</strong> Estimable with reasonable stability out of sample.</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>2) Distribution vs. single-number risk</summary>
        <div class="content">
          <p>The full return distribution answers every risk question but is unwieldy. In practice we compress it to a single, stable, aggregable statistic for monitoring and control.</p>
        </div>
      </details>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>A risk by any other name.</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>3) Standard deviation (the workhorse)</summary>
        <div class="content">
          <p><strong>Idea.</strong> Dispersion about the mean is the operative “cost of risk;” use variance for math, σ for reporting.</p>

          
\[ 
\operatorname{Var}(r)=\mathbb{E}\big[(r-\mu)^2\big]
\]

\[
\sigma=\sqrt{\operatorname{Var}(r)}
\]

\[
\text{Annualization (i.i.d.):}\quad 
\sigma_{\text{ann}}=\sqrt{T}\,\sigma_{\text{per}},\qquad
\sigma_{\text{ann}}^2=T\,\sigma_{\text{per}}^2
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>4) Semivariance (definitions)</summary>
        <div class="content">

\[
\textbf{Semivariance about mean:}\quad 
\operatorname{SemiVar}(r)=\mathbb{E}\!\big[(\mu-r)^2\,\mathbf{1}_{\{r<\mu\}}\big]
\]

\[
\textbf{Target semivariance (threshold }\tau\textbf{):}\quad 
\operatorname{SemiVar}_{\tau}(r)=\mathbb{E}\!\big[(\tau-r)^2\,\mathbf{1}_{\{r<\tau\}}\big]
\]

\[
\textbf{Symmetry:}\quad \operatorname{SemiVar}(r)=\tfrac{1}{2}\operatorname{Var}(r)\ \text{if the distribution is symmetric.}
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>5) Shortfall probability (one-period)</summary>
        <div class="content">
          <p><strong>Definition.</strong> Probability of failing a chosen threshold \(K\) next period: \(\Pr(R<K)\).</p>

\[
R\sim\mathcal N(E,\sigma^2)
\]

\[
\Pr(R<K)=\Phi\!\left(\frac{K-E}{\sigma}\right)
\]

          <p><strong>Drawbacks.</strong> Choice of \(K\) is investor-/mandate-specific; tail probabilities rely on distributional assumptions that can miss fat tails.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>6) Absolute shortfall (terminal value)</summary>
        <div class="content">
          <p><strong>Definition.</strong> Probability terminal value falls below a fixed level \(K\): \(\Pr(V_T<K)\).</p>

\[
r_t=\ln(1+R_t)\overset{i.i.d.}{\sim}\mathcal N(\mu,\sigma^2)
\]

\[
\ln V_T=\ln V_0+\sum_{t=1}^T r_t\sim \mathcal N(\ln V_0+T\mu,\ T\sigma^2)
\]

\[
\Pr(V_T<K)=\Phi\!\left(\frac{\ln K-\ln V_0 - T\mu}{\sqrt{T}\,\sigma}\right)
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>7) Relative shortfall (vs. a benchmark)</summary>
        <div class="content">
          <p><strong>Definition.</strong> Probability a risky asset or portfolio underperforms a benchmark over \(T\) periods.</p>

\[
\Delta := \sum_{t=1}^T (r_{S,t}-r_{B,t})
\]

\[
E(\Delta)=T(\mu_S-\mu_B),\quad 
\operatorname{Var}(\Delta)=T\!\left(\sigma_S^2+\sigma_B^2-2\rho_{SB}\sigma_S\sigma_B\right)
\]

\[
\Pr(V_{S,T}<V_{B,T})=\Pr(\Delta<0)
= \Phi\!\left(\frac{-T(\mu_S-\mu_B)}{\sqrt{T\big(\sigma_S^2+\sigma_B^2-2\rho_{SB}\sigma_S\sigma_B\big)}}\right)
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>8) VaR — parametric (Normal) </summary>
        <div class="content">
          <p><strong>Definition.</strong> For tail probability \(c\in(0,1)\), VaR is the positive number \( \mathrm{VaR}_c \) such that the next-period loss exceeds \( \mathrm{VaR}_c \) with probability \(c\).</p>

\[
q_R(c)=E+\sigma\,\Phi^{-1}(c),\qquad
\mathrm{VaR}_c = -\,V\cdot q_R(c)
\]

\[
\text{Small horizon (}E\approx 0\text{):}\quad 
\mathrm{VaR}_c \approx z_c\,\sigma\,V,\ \ z_c:=|\Phi^{-1}(c)|
\]

\[
\text{Scaling (i.i.d.):}\quad 
\mathrm{VaR}_{c,\ T}\approx z_c\,\sigma\,\sqrt{T}\,V
\]

          <p><strong>Drawbacks.</strong> Assumes a shape (often Normal) for tails; ignores loss severity beyond the quantile; can be pro-cyclical when σ rises in sell-offs.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>9) Historical VaR</summary>
        <div class="content">
          <p><strong>Definition.</strong> Use the empirical \(c\)-quantile of a rolling window of past returns (or P&amp;L) as the loss threshold.</p>

\[
\widehat{\mathrm{VaR}}_{c} = V \cdot \big|\ \widehat{q}_{R}(c)\ \big|\quad
\text{with }\widehat{q}_{R}(c)\text{ the sample }c\text{-quantile of returns}
\]

          <p><strong>Notes.</strong> No distributional assumption; window choice and equal weighting of days matter; may underweight stale extremes.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>10) Volatility-based VaR</summary>
        <div class="content">
          <p><strong>Definition.</strong> Forecast next-period volatility \(\sigma_t\) (e.g., via a volatility model), assume short-horizon mean \(\approx 0\), then</p>

\[
\mathrm{VaR}_{c,t+1}= z_c\,\sigma_t\,V_t,\qquad z_{1\%}\approx 2.33,\ z_{5\%}\approx 1.65
\]

          <p><strong>Notes.</strong> Quality depends on the volatility forecast; still inherits the quantile-only limitation.</p>
        </div>
      </details>
    </div>
  </details>
</div>


<!-- Flashcard — G&K Ch.3 (pp.47–52): Risk, Diversification, Active & Residual Risk -->

<div class="flashcard">
  <details>
    <summary>Sigma</summary>
    <div class="back">
      <p><em>Open sections for the bite-size summary interleaved with the key formulas.</em></p>

      <details class="dropdown-block">
        <summary>1) Standard deviation as the risk metric</summary>
        <div class="content">
          <p><strong>Summary.</strong> Use the standard deviation of return as “risk”; use variance as the cost in optimization. For a given period, the risk of the excess return equals the risk of the total return because the risk-free rate is known at the start.</p>

\[
\operatorname{Var}(r)=\mathbb{E}\big[(r-\mu)^2\big]
\]

\[
\sigma=\sqrt{\operatorname{Var}(r)}
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>2) σ is not a weighted average (two-asset property)</summary>
        <div class="content">
          <p><strong>Summary.</strong> Portfolio σ is <em>not</em> the weighted average of individual σ’s; correlation drives diversification. Equality to the simple average occurs only if correlation is +1.</p>

\[
\sigma_P=\sqrt{(w_1\sigma_1)^2+(w_2\sigma_2)^2+2\,w_1w_2\,\sigma_1\sigma_2\,\rho_{12}}
\]

\[
\sigma_P \le w_1\sigma_1+w_2\sigma_2
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>3) Diversification with many assets</summary>
        <div class="content">
          <p><strong>Summary.</strong> Idiosyncratic risk diversifies away; what remains is the correlated component.</p>

\[
\text{Equal-weight, uncorrelated:}\quad \sigma_P=\frac{\sigma}{\sqrt{N}}
\]

\[
\text{Equal-weight, common correlation }\rho:\quad 
\sigma_P=\sigma\,\sqrt{\frac{1+\rho\,(N-1)}{N}}
\]

\[
\text{Limit as }N\to\infty:\quad \sigma_P\to \sigma\,\sqrt{\rho}
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>4) Time aggregation / annualization</summary>
        <div class="content">
          <p><strong>Summary.</strong> With negligible autocorrelation across non-overlapping periods, variance adds across time; σ scales with the square-root of time.</p>

\[
\sigma_{\text{annual}}=\sqrt{12}\,\sigma_{\text{monthly}}
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>5) Active risk (tracking error)</summary>
        <div class="content">
          <p><strong>Summary.</strong> Active return is portfolio minus benchmark return; active risk is its standard deviation. It is driven by <em>active exposures</em> and asset risks, not by benchmark weights per se.</p>

\[
\psi_P=\operatorname{Std}[\,r_P-r_B\,]
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>6) Residual risk and beta (orthogonal to benchmark)</summary>
        <div class="content">
          <p><strong>Summary.</strong> Residual risk is the component of portfolio risk orthogonal to the benchmark; remove the systematic piece measured by beta.</p>

\[
\omega_P=\sqrt{\sigma_P^2-\beta_P^2\,\sigma_B^2}
\]

\[
\beta_P=\frac{\operatorname{Cov}(r_P,r_B)}{\operatorname{Var}(r_B)}
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>7) Cost of risk (optimization view)</summary>
        <div class="content">
          <p><strong>Summary.</strong> Treat variance as a <em>cost</em> with risk-aversion parameter \(a\). For active management, the expected return trade-off associated with taking tracking error \(\psi_P\) is proportional to \(\psi_P^2\).</p>

\[
\text{Cost of active risk} \;=\; a\,\psi_P^2
\]
        </div>
      </details>

    </div>
  </details>
</div>

<!-- Flashcard — G&K Ch.3 (pp.53–54): Elementary Risk Models -->

<div class="flashcard">
  <details>
    <summary>3 Indecent Proposals</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>Why a risk model? (the covariance matrix)</summary>
        <div class="content">
          <p><strong>Summary.</strong> For \(N\) assets you must estimate \(N\) volatilities plus \(N(N-1)/2\) correlations. Gather them in the covariance matrix \(V\); the goal of a risk model is to forecast \(V\) accurately and efficiently.</p>

\[
V=\begin{bmatrix}
\sigma_1^2 & \sigma_{12} & \cdots & \sigma_{1N}\\
\sigma_{21} & \sigma_2^2 & \cdots & \sigma_{2N}\\
\vdots & \vdots & \ddots & \vdots\\
\sigma_{N1} & \sigma_{N2} & \cdots & \sigma_N^2
\end{bmatrix},
\quad
\sigma_{nm}=\operatorname{Cov}(r_n,r_m),\ \ \sigma_n=\sqrt{\operatorname{Var}(r_n)}.
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Model 1 — Single-factor (market + residual) risk model</summary>
        <div class="content">
          <p><strong>Summary.</strong> Decompose each stock’s risk into market and residual components; treat residuals across names as uncorrelated within the model.</p>

\[
r_n=\beta_n\,r_M+\theta_n
\]

\[
\operatorname{Cov}(r_n,r_m)=\beta_n\beta_m\,\sigma_M^2
\]

\[
\sigma_n^2=\beta_n^2\,\sigma_M^2+\omega_n^2
\]

          <ul>
            <li><strong>NB.</strong> CAPM is about <em>expected returns</em> in equilibrium; this single-factor model is a <em>risk</em> model (no pricing claims).</li>
            <li><strong>NB.</strong> Market-weighted residuals sum to zero:
\[
\sum_{n} h_M(n)\,\theta_n=0
\]
This implies small average negative residual correlation in large universes.</li>
            <li><strong>Consequence.</strong> Cross-stock residual covariances are set to \(0\), giving a conservative estimate of co-movement beyond the market.</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Model 2 — Constant-correlation</summary>
        <div class="content">
          <p><strong>Summary.</strong> Use each stock’s own \(\sigma_n\) and one common correlation \(\rho\) for all pairs; quick but crude.</p>

\[
\operatorname{Cov}(r_n,r_m)=\sigma_n\,\sigma_m\,\rho \quad (n\neq m)
\]

          <ul>
            <li><strong>Pros.</strong> Extremely simple; useful for “quick-and-dirty” controls.</li>
            <li><strong>Cons.</strong> Ignores industry/style linkages and other structure.</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Model 3 — Historical covariance matrix</summary>
        <div class="content">
          <p><strong>Summary.</strong> Estimate \(V\) directly from sample covariances. Not robust for portfolio construction.</p>
          <ul>
            <li>Requires more time observations than assets to avoid singularity.</li>
            <li>Short windows conflict with typical forecast horizons; long windows miss structural change.</li>
            <li>Selection and sample biases (omitted failures, corporate events) distort estimates.</li>
            <li>Sampling error explodes with dimension: large \(N\) means many chances for bad numbers.</li>
            <li><strong>NB (rank condition).</strong> An \(N\times N\) sample covariance from \(T\) periods has rank \(\le T-1\); a practical rule is \(T\gtrsim N+1\).</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Bottom line</summary>
        <div class="content">
          <p>Elementary models illuminate trade-offs but are either too crude (single-factor, constant-\(\rho\)) or too noisy (historical \(V\)). This motivates structured multi-factor risk models to stabilize and explain covariance forecasts.</p>
        </div>
      </details>

    </div>
  </details>
</div>


