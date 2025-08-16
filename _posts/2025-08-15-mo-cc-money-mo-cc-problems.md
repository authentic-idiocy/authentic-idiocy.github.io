---
layout: post
title: "Mo Continuously Compounded Money, Mo Continuously Compounded Problems"
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "-- Biggie Smalls, probably."
---
<div class="flashcard">
  <details>
    <summary>Who hot, who not</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>The logarithmic function computes continuously-compounded returns from prices.</summary>
        <div class="content">
          <p>Let $S_t$ and $S_{t+h}$ be stock prices at times $t$ and $t+h$. Define the continuously-compounded return between $t$ and $t+h$ by</p>
          \[
          r_{t,t+h}=\ln\!\left(\frac{S_{t+h}}{S_t}\right).
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>The exponential function computes prices from continuously-compounded returns.</summary>
        <div class="content">
          <p>If you know $r_{t,t+h}$, recover the future price by</p>
          \[
          S_{t+h}=S_t\,e^{\,r_{t,t+h}}.
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Continuously-compounded returns are additive over subperiods.</summary>
        <div class="content">
          <p>For consecutive subperiods of length $h$ (e.g., $n$ steps),</p>
          \[
          r_{t,t+nh}=\sum_{i=1}^{n} r_{t+(i-1)h,\,t+ih}.
          \]
          <p><strong>Derivation (core step):</strong></p>
          \[
          \begin{aligned}
          r_{t,t+2h}
          &=\ln\!\left(\frac{S_{t+2h}}{S_t}\right) \\
          &=\ln\!\left(\frac{S_{t+2h}}{S_{t+h}}\cdot\frac{S_{t+h}}{S_t}\right) \\
          &=\ln\!\left(\frac{S_{t+2h}}{S_{t+h}}\right)+\ln\!\left(\frac{S_{t+h}}{S_t}\right) \\
          &= r_{t+h,\,t+2h}+r_{t,\,t+h},
          \end{aligned}
          \]
          <p>...induction, yada yada... derived for $n$.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Useful equivalences</summary>
        <div class="content">
          <p>Simple return $R_{t,t+h}:=\dfrac{S_{t+h}-S_t}{S_t}$ relates to the continuous return via</p>
          \[
          r_{t,t+h}=\ln(1+R_{t,t+h}),\qquad R_{t,t+h}=e^{\,r_{t,t+h}}-1.
          \]
          <p>For small moves, \(r\approx R\) (<span class="define" data-def="$$&#10;\\textbf{Taylor about }a:\\quad&#10;f(x)=\\sum_{k=0}^{n}\\frac{f^{(k)}(a)}{k!}(x-a)^k \\;+\\; R_{n+1}(x).&#10;$$&#10;$$&#10;\\textbf{Maclaurin about }0:\\quad&#10;f(x)=\\sum_{k=0}^{n}\\frac{f^{(k)}(0)}{k!}x^k \\;+\\; R_{n+1}(x).&#10;$$&#10;$$&#10;\\textbf{First order (}n=1\\textbf{):}\\quad&#10;f(x)\\approx f(a)+f'(a)(x-a)\\quad\\text{or}\\quad f(x)\\approx f(0)+f'(0)x.&#10;$$&#10;Let&#10;$$&#10;R:=\\frac{S_{t+h}-S_t}{S_t}=\\frac{S_{t+h}}{S_t}-1,\\qquad&#10;r:=\\ln\\!\\left(\\frac{S_{t+h}}{S_t}\\right)=\\ln(1+R).&#10;$$&#10;Expand \\(\\ln(1+x)\\) about \\(x=0\\):&#10;$$&#10;\\ln(1+x)=x-\\frac{x^{2}}{2}+\\frac{x^{3}}{3}-\\cdots&#10;=\\sum_{k=1}^{\\infty}(-1)^{k+1}\\frac{x^{k}}{k},\\quad |x|&lt;1\\ (\\text{also converges at }x=1).&#10;$$&#10;With \\(x=R\\),&#10;$$&#10;r=\\ln(1+R)=R-\\frac{R^{2}}{2}+O(R^{3})=R+O(R^{2}).&#10;$$&#10;Hence, to first order, \\(r\\approx R\\).">first-order Taylor</span>).</p>
        </div>
      </details>

    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Dangerous on trizack, leave your ass kizzack (Volatility (σ) for CCRs)</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>From monthly to annual volatility</summary>
        <div class="content">
          <p>Let the continuously-compounded monthly return in month \(i\) be \(r_{\text{monthly},i}\), \(i=1,\dots,12\).</p>
          <ul>
            <li><strong>Additivity of log returns ⇒ annual cc return</strong>
              \[
              r_{\text{annual}}
              =\sum_{i=1}^{12} r_{\text{monthly},i}.
              \]
            </li>
            <li><strong>Variance of the annual cc return</strong>
              \[
              \operatorname{Var}\!\left(r_{\text{annual}}\right)
              =\operatorname{Var}\!\left(\sum_{i=1}^{12} r_{\text{monthly},i}\right).
              \]
            </li>
            <li><strong>Assumptions used to annualize.</strong> Suppose (i) returns are <strong>uncorrelated</strong> across months (no serial covariance), and (ii) each month has the <strong>same variance</strong>. Write the annual standard deviation as \(\sigma_{\text{annual}}\) and the monthly standard deviation as \(\sigma_{\text{monthly}}\). Then covariance terms drop and the variance of a sum is the sum of variances:
              \[
              \sigma^{2}_{\text{annual}}
              =12\,\sigma_{\text{monthly}}^{2}.
              \]
            </li>
            <li><strong>Solve for monthly σ from annual σ</strong>
              \[
              \sigma_{\text{monthly}}
              =\frac{\sigma_{\text{annual}}}{\sqrt{12}}.
              \]
            </li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Generalization to any subperiod length \(h\)</summary>
        <div class="content">
          <p>Split the year into \(n\) equal periods, each of length \(h=1/n\). Let \(\sigma_h\) denote the standard deviation of returns over horizon \(h\) (in years) and \(\sigma_{nh}\) the stdev of returns over \(nh\).</p>
          <ul>
            <li><strong>Square-root-of-time scaling</strong>
              \[
              \sigma_h=\sigma_{nh}\sqrt{h}.
              \]
            </li>
            <li><strong>Invert to recover horizon-\(nh\) σ from horizon-\(h\) σ</strong>
              \[
              \sigma_{nh}=\frac{\sigma_h}{\sqrt{h}}.
              \]
            </li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Why the square-root law holds (quick derivation)</summary>
        <div class="content">
          \[
          r_{nh}=\sum_{i=1}^{n} r_{h,i},\quad
          \operatorname{Var}(r_{nh})
          =\sum_{i=1}^{n}\operatorname{Var}(r_{h,i})
          +2\sum_{i<j}\operatorname{Cov}(r_{h,i},r_{h,j}).
          \]
          <p>Uncorrelated returns set all covariances to \(0\). If each \(\operatorname{Var}(r_{h,i})=\sigma_h^2\), then \(\sigma^2 = n\sigma_h^2\). Since \(n=1/h\), we get \(\sigma_h=\sigma\sqrt{h}\).</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Nota Benes, or Notate Bene (assumptions &amp; caveats)</summary>
        <div class="content">
          <ul>
            <li>The scaling assumes continuously-compounded returns are <strong>independent and identically distributed</strong> across periods. If not:
              <ul>
                <li><strong>Serial dependence (mean reversion/momentum):</strong> Covariance terms &ne; 0. With <em>mean reversion</em> (negative autocorrelation), long-horizon volatility can be <em>less</em> than \(\sigma\sqrt{T}\) (e.g., many commodities, where supply responses push prices back toward fundamentals). With <em>momentum</em> (positive autocorrelation), it can be <em>greater</em> than \(\sigma\sqrt{T}\).</li>
                <li><strong>Time-varying volatility (heteroskedasticity):</strong> Scaling is more complicated than \(\sqrt{\cdot}\).</li>
              </ul>
            </li>
            <li><strong>Pricing implication.</strong> When independence is doubtful, <strong>SIM IT</strong>.</li>
          </ul>
        </div>
      </details>

    </div>
  </details>
</div>
