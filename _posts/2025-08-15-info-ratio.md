---
layout: post
title: "An Engineer, Philosopher, and Economist are Stranded on a Deserted Island and Only Have Canned Food."
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "information action ratio."
---

<div class="flashcard">
  <details>
    <summary>\(\alpha\): (noun) al·​pha</summary>
    <div class="back">
      <details class="dropdown-block">
        <summary>Ex ante vs. ex post</summary>
        <div class="content">
          <ul>
            <li>Looking forward (<b>ex ante</b>): alpha is a <b>forecast of residual return</b>.</li>
            <li>Looking backward (<b>ex post</b>): alpha is the <b>average of realized residual returns</b>.</li>
            <li>Realized alphas are for keeping score; the manager's job is to generate <b>good forecasts</b>.</li>
          </ul>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Regression definition (realized/historical α and β)</summary>
        <div class="content">
          <p>If \(r_p(t)\) are portfolio <b>excess</b> returns for \(t=1,\dots,T\) and \(r_B(t)\) are benchmark <b>excess</b> returns over the same periods, the regression is</p>
          <p>\[
          r_p(t) \;=\; \alpha_p \;+\; \beta_p \cdot r_B(t) \;+\; \varepsilon_p(t)
          \]</p>
          <p>The estimates of \(\beta_p\) and \(\alpha_p\) from this regression are the <b>realized (historical)</b> beta and alpha.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Residual (idiosyncratic) returns</summary>
        <div class="content">
          <p>Define the portfolio's residual return as</p>
          <p>\[
          \theta_p(t) \;=\; \alpha_p \;+\; \varepsilon_p(t)
          \]</p>
          <p>Where \(\alpha_p\) is the <b>average residual return</b> and \(\varepsilon_p(t)\) is the <b>mean-zero</b> random residual component.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Forecast alpha (single asset)</summary>
        <div class="content">
          <p>Let \(\theta_n\) be the residual return on stock \(n\). The <b>forecast alpha</b> is</p>
          <p>\[
          \alpha_n \;=\; E[\theta_n]
          \]</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Portfolio property of alpha</summary>
        <div class="content">
          <p>Because both residual returns and expectations aggregate linearly, alpha has the <b>portfolio property</b>. For a two-stock portfolio with holdings \(h_p(1)\) and \(h_p(2)\) and stock alphas \(\alpha_1,\alpha_2\),</p>
          <p>\[
          \alpha_p \;=\; h_p(1)\cdot \alpha_1 \;+\; h_p(2)\cdot \alpha_2
          \]</p>
          <p>This matches the interpretation that \(\alpha_p\) is the <b>forecast of expected residual return</b> on the portfolio.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Benchmark and cash</summary>
        <div class="content">
          <ul>
            <li>By definition, the benchmark has residual return \(\theta_B = 0\) <b>with certainty</b>, hence its alpha is \(\alpha_B = 0\). The alphas are therefore <b>benchmark-neutral</b>.</li>
            <li>The risk-free (cash) portfolio also has <b>zero residual return</b>, so the alpha for cash \(\alpha_r = 0\).</li>
            <li>Any portfolio that is a mixture of benchmark and cash has <b>zero alpha</b>.</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>
<div class="flashcard">
  <details>
    <summary>Look back at it. No wait. Don't.</summary>
    <div class="back">
      <details class="dropdown-block">
        <summary>The Ex Post Information Ratio: A Measure of Achievement</summary>
        <div class="content">
          <p><strong>Definition.</strong><br>
          An <b>information ratio</b> \(IR\) is the ratio of <i>(annualized) residual return</i> to <i>(annualized) residual risk</i>. Ex post, it uses <b>realized</b> residual return and <b>realized</b> residual risk (active risk).</p>
          
          <p><strong>Properties.</strong></p>
          <ul>
            <li>A realized \(IR\) can be negative.</li>
            <li>The benchmark's \(IR\) is <b>exactly zero</b> (its residual return is \(0\)).</li>
            <li>Link to regression: If the alpha regression is run over \(Y\) years, the realized information ratio is approximately</li>
          </ul>
          <div class="define">
            <p>\[
            IR_{\text{ex post}} \approx \frac{t(\hat{\alpha})}{\sqrt{Y}} .
            \]</p>
            <div class="tooltip">
              <div style="max-width: 500px">
                <h4>A statsy tip: What is \(t(\hat{\alpha}_p)\)?</h4>
                <p>In the regression from the screenshot</p>
                <p>\[
                r_p(t) \;=\; \alpha_p \;+\; \beta_p\, r_B(t) \;+\; \varepsilon_p(t)
                \]</p>
                <p>estimated on \(t=1,\dots,T\) observations, \(t(\hat{\alpha}_p)\) means the <b>t-statistic of the estimated intercept</b> \(\hat{\alpha}_p\):</p>
                <p>\[
                t(\hat{\alpha}_p) \;=\; \frac{\hat{\alpha}_p}{\widehat{\operatorname{se}}(\hat{\alpha}_p)} .
                \]</p>
                
                <p>Here</p>
                <ul>
                  <li>\(r_p(t)\): portfolio <b>excess</b> return at time \(t\).</li>
                  <li>\(r_B(t)\): benchmark <b>excess</b> return at time \(t\).</li>
                  <li>\(\varepsilon_p(t)\): regression residual at time \(t\).</li>
                  <li>\(T\): number of time periods used in the regression.</li>
                  <li>\(Y\): number of <b>years</b> covered by those data (e.g., monthly data over \(Y\) years gives \(T=12Y\)).</li>
                  <li>\(\widehat{\operatorname{se}}(\hat{\alpha}_p)\): estimated <b>standard error</b> of \(\hat{\alpha}_p\).</li>
                </ul>
                
                <p>A concrete formula for the standard error in this simple regression is</p>
                <p>\[
                \widehat{\operatorname{se}}(\hat{\alpha}_p)
                \;=\;
                \hat{\sigma}_\varepsilon \, \sqrt{\left[(X^\top X)^{-1}\right]_{11}}
                \]</p>
                
                <p>with</p>
                <p>\[
                \hat{\sigma}_\varepsilon^{\,2} \;=\; \frac{1}{T-2}\sum_{t=1}^{T}\hat{\varepsilon}_p(t)^{2},
                \qquad
                \hat{\varepsilon}_p(t) \;=\; r_p(t)-\hat{\alpha}_p-\hat{\beta}_p\,r_B(t),
                \]</p>
                
                <p>and \(X\) the \(T\times 2\) design matrix whose first column is all ones and second column is \(r_B(t)\). Equivalently, writing \(\bar{r}_B=\frac{1}{T}\sum r_B(t)\) and \(S_{BB}=\sum (r_B(t)-\bar{r}_B)^2\),</p>
                <p>\[
                \left[(X^\top X)^{-1}\right]_{11}
                \;=\;
                \frac{1}{T} \;+\; \frac{\bar{r}_B^{\,2}}{S_{BB}} .
                \]</p>
              </div>
            </div>
          </div>
          
          <p><b>Theory intuition.</b> Ex post \(IR\) is a <b>signal-to-noise</b> measure for realized residual performance: how much alpha per unit of residual volatility your realized track record shows.</p>
          
          <p><b>Treynor and Black (1973) call this the <b>appraisal ratio</b>.</b></p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>The Ex Ante Information Ratio: A Measure of Opportunity</summary>
        <div class="content">
          <p><strong>Definition (planning view).</strong><br>
          Ex ante, the information ratio is the <b>expected</b> level of annual residual return per unit of annual residual risk. More precisely: it is the <b>highest</b> achievable ratio of expected annual residual return to residual risk that the manager can obtain using their information.</p>
          
          <p><b>Theory intuition.</b><br>
          Ex ante \(IR\) summarizes the <b>quality of forecasts</b> (alphas) and the <b>efficiency of portfolio construction</b> that turns those forecasts into return per unit of active risk. It is a <b>capability frontier</b>: better information or better use of it raises the frontier.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Empirical yardsticks</summary>
        <div class="content">
          <p>The cross-section of realized manager \(IR\)s is roughly <b>symmetric around 0</b>, consistent with active management being a <b>zero-sum game after fees</b>. Heuristics used throughout:</p>
          <ul>
            <li>Top-quartile manager: \(IR \approx 0.5\) ("good").</li>
            <li>\(IR=0.75\): "very good."</li>
            <li>\(IR=1.0\): "exceptional."</li>
          </ul>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Formal definition at the portfolio level</summary>
        <div class="content">
          <p>Given any portfolio \(P\) with portfolio alpha \(\alpha_p\) and portfolio residual (active) risk \(\omega_p\),</p>
          <p>\[
          IR_p \;=\; \frac{\alpha_p}{\omega_p}
          \]</p>
          
          <p>The manager's own "information ratio" is the <b>maximum</b> attainable across feasible portfolios (built from their alphas):</p>
          <p>\[
          IR \;=\; \Max\{\, IR_p \mid P \,\}
          \]</p>
          
          <p><b>Theory notes.</b></p>
          <ul>
            <li>The notation \(IR\) <b>depends on the alpha vector</b>; one common use is to <b>scale</b> the alpha forecasts so that the manager's maximization delivers a sensible target \(IR\).</li>
            <li>The definition implies <b>risk-level invariance</b>: if a manager can achieve an expected residual return of \(2\%\) with \(4\%\) residual risk, they can (by scaling the active position) achieve \(3\%\) with \(6\%\) residual risk—same \(IR\). (see <i>'Decomposition, active risk, and scale invariance'</i> below)</li>
          </ul>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Decomposition, active risk, and scale invariance</summary>
        <div class="content">
          <p>Let \(h_p\) be portfolio holdings, \(h_B\) benchmark holdings, and \(h_p^{a}\) <b>active</b> holdings.</p>
          
          <p><strong>Holdings decomposition.</strong></p>
          <p>\[
          h_p \;=\; h_B \;+\; h_p^{a}, \quad \text{with} \quad \alpha_B = 0 .
          \]</p>
          
          <p>If \(\alpha\) is the vector of stock alphas, then</p>
          <p>\[
          \alpha_p \;=\; \alpha^{\mathsf T} h_p \;=\; \alpha^{\mathsf T} h_p^{a}.
          \]</p>
          
          <p><strong>Active risk.</strong><br>
          Let <b>\(\psi_p\)</b>: the portfolio's <b>active (residual) variance</b> under holdings \(h_p^{a}\) and residual-return covariance matrix \(V\in\mathbb{R}^{N\times N}\):</p>
          <p>\[
          \psi_p \;=\; (h_p^{a})^{\mathsf T} V\, h_p^{a}
          \quad\text{and}\quad
          \omega_p \;=\; \sqrt{\psi_p}\ \ \text{(active risk, i.e., st. dev.)}.
          \]</p>
          
          <p><strong>Scaling (aggressiveness).</strong><br>
          Let active holdings be scaled by <b>\(\phi\)</b>: a <b>scalar aggressiveness multiplier</b> (unitless) that scales the <b>active holdings</b>.</p>
          
          <p>If \(h_p^{a}\in\mathbb{R}^N\) are the active weights, then</p>
          <p>\[
          h_p^{a}\ \to\ \phi\,h_p^{a},\quad \phi>0 .
          \]</p>
          
          <p>Under this scaling,</p>
          <p>\[
          \alpha_p \to \phi\,\alpha_p,\qquad \omega_p \to \phi\,\omega_p,\qquad IR_p=\alpha_p/\omega_p\ \text{unchanged}.
          \]</p>
          
          <p><b>Theory intuition.</b><br>
          Because both numerator and denominator scale <b>linearly</b> in exposure, \(IR\) is <b>independent of aggressiveness</b> under ideal (unconstrained) conditions. In practice, <b>constraints</b> (e.g., short-sale limits, turnover/financing frictions) break pure scaling and can <b>reduce</b> realized \(IR\) as risk is pushed higher.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Time-horizon scaling</summary>
        <div class="content">
          <p>To avoid confusion, standardize to a <b>1-year</b> horizon. Over horizon \(T\) (in years):</p>
          <ul>
            <li>Expected residual return scales \(\propto T\).</li>
            <li>Residual <b>variance</b> scales \(\propto T\), so <b>residual risk</b> (st. dev.) scales \(\propto \sqrt{T}\).</li>
            <li>Therefore the information ratio scales as</li>
          </ul>
          <div class="define">
            <p>\[
            IR(T) \;=\; \sqrt{T}\; IR(1\ \text{year}).
            \]</p>
            <div class="tooltip">
              <div style="max-width: 500px">
                <h4>In math:</h4>
                <p><strong>Notation across horizons</strong></p>
                <p>Let \(\alpha_p(T)\) and \(\omega_p(T)\) denote the <b>expected residual return</b> and <b>residual risk (st.dev.)</b> over a horizon \(T\) years. Then</p>
                <p>\[
                IR_p(T)=\frac{\alpha_p(T)}{\omega_p(T)}.
                \]</p>
                
                <p>Define the 1-year quantities \(\alpha_p(1)\) and \(\omega_p(1)\).</p>
                
                <p><strong>Step 1 — Expected residual return scales linearly in time</strong></p>
                <p>Additivity of expectations over \(T\) years gives</p>
                <p>\[
                \alpha_p(T)=T\,\alpha_p(1).
                \]</p>
                <p>(In words: run the same edge for twice as long, you expect twice the residual return.)</p>
                
                <p><strong>Step 2 — Residual <b>variance</b> scales linearly ⇒ residual <b>risk</b> scales as \(\sqrt{T}\)</strong></p>
                <p>With negligible serial correlation, variances add:</p>
                <p>\[
                \operatorname{Var}_T = T\,\operatorname{Var}_{1\text{y}}
                \quad\Longrightarrow\quad
                \omega_p(T)=\sqrt{T}\,\omega_p(1).
                \]</p>
                
                <p><strong>Step 3 — Put together to get the IR scaling</strong></p>
                <p>\[
                IR_p(T)
                =\frac{\alpha_p(T)}{\omega_p(T)}
                =\frac{T\,\alpha_p(1)}{\sqrt{T}\,\omega_p(1)}
                =\sqrt{T}\,\frac{\alpha_p(1)}{\omega_p(1)}
                =\boxed{\,\sqrt{T}\,IR_p(1\text{ year})\,}.
                \]</p>
              </div>
            </div>
          </div>
          
          <p>Corollaries: a quarterly \(IR\) is half the annual \(IR\); a monthly \(IR\) is \(1/\sqrt{12}\) of the annual \(IR\).</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Tilder</summary>
        <div class="content">
          <ul>
            <li><b>Ex post \(IR\)</b> measures <b>achievement</b> (realized alpha per unit of realized residual risk) and connects tightly to the <b>t-stat</b> of \(\alpha\).</li>
            <li><b>Ex ante \(IR\)</b> measures <b>opportunity</b> (what your information and construction can deliver) and is the <b>maximized</b> \(\alpha/\omega\) over feasible portfolios.</li>
            <li>\(IR\) is <b>scale-invariant</b> with respect to position size but <b>horizon-dependent</b> (\(\sqrt{T}\) rule).
              <ul>
                <li>Hold the same active trade longer: expected alpha grows \(\propto T\); uncertainty (risk) grows only \(\propto \sqrt{T}\). Their ratio therefore grows like \(\sqrt{T}\).</li>
              </ul>
            </li>
            <li>Benchmarks and cash have <b>zero \(IR\)</b>; the cross-section of manager \(IR\)s centers near <b>zero</b>, consistent with active management being zero-sum after costs.</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>
