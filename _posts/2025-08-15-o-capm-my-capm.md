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
    <summary>You can be diversified away. I raise the cost of capital. We are not the same.</summary>
    <div class="back">
      <p><strong>Setup.</strong> Portfolio \(P\) and market \(M\) with excess returns \(r_P, r_M\).</p>
      
      <ul>
        <li><em>Note:</em> The market portfolio \(M\) is typically approximated using a broad value-weighted domestic equity index (e.g., S&amp;P 500 for US markets).</li>
      </ul>
      
      <p>Define the portfolio's market beta as:</p>
      \[
      \beta_P = \frac{\operatorname{Cov}(r_P,r_M)}{\operatorname{Var}(r_M)}
      \]
      
      <p><em>Regression form (time series):</em></p>
      
      \[
      r_P(t)=\alpha_P+\beta_P\,r_M(t)+\varepsilon_P(t),\qquad t=1,\ldots,T.
      \]
      
      <p><em>Arithmetic decomposition (definition):</em></p>
      
      \[
      r_P=\underbrace{\beta_P r_M}_{\text{market (systematic) component}} + \underbrace{\theta_P}_{\text{residual (idiosyncratic) component}} \quad\Rightarrow\quad \theta_P \;:=\; r_P-\beta_P r_M.
      \]
      
      <p><em>Orthogonality (pure regression geometry):</em></p>
      
      \[
      \operatorname{Cov}(\theta_P,r_M)=\operatorname{Cov}(r_P-\beta_P r_M,\,r_M)
      =\operatorname{Cov}(r_P,r_M)-\beta_P \operatorname{Var}(r_M)=0.
      \]
      
      <p><em>Variance split:</em></p>
      
      \[
      \operatorname{Var}(r_P)=\underbrace{\beta_P^{2}\operatorname{Var}(r_M)}_{\text{systematic risk}} + \underbrace{\omega_P^{2}}_{\text{idiosyncratic risk}},
      \qquad \omega_P^{2}:=\operatorname{Var}(\theta_P).
      \]
      <details class="dropdown-block">
        <summary>In english.</summary>
        <div class="content">
          <ul>
            <li>\(\beta_p\) measures how much <strong>market risk</strong> \(P\) carries per unit of market variance.</li>
            <li>The arithmetic decomposition is a <strong>projection</strong>: \(r_p\) is orthogonally projected onto \(r_M\). The fitted part \(\beta_p r_M\) is the market-driven return; the miss \(\theta_p\) is everything <em>not</em> explained by the market.</li>
            <li>Because \(\theta_p \perp r_M\), total variance splits additively. This is the statistical backbone behind phrases like “systematic vs. idiosyncratic risk.”</li>
            <li>None of this assumes CAPM or equilibrium—only linear projection and definitions. CAPM later stipulates how <strong>expected</strong> returns relate to \(\beta\) and says residuals shouldn’t earn systematic premia.</li>
          </ul>
        </div>
      </details>
      <p><small>
        Notes: \((\hat\alpha_P,\hat\beta_P)\) from historical OLS summarize the past; \(\beta\) itself is forward-looking. By convention the market has \(\beta=1\) and the risk-free asset has \(\beta=0\). No CAPM assumptions needed—this is straight regression algebra.<br>
        <span style="font-style: italic;">The CAPM adds <span style="font-weight: bold;">economic</span> content only when it asserts something about the <span style="font-weight: bold;">expected</span> returns of those residual (non-market) pieces.</span>
      </small></p>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>CAPM Crunch</summary>
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
        <li><em>Implicit assumption:</em> Investors share <strong>homogeneous expectations</strong> (they differ only in risk tolerance).</li>
        <li><em>Passive investing implication:</em> Under CAPM, anyone who deviates from the market plays a <strong>zero-sum</strong> game—extra risk with no extra expected return—so the logic pushes to buy-and-hold the market (<strong>passive investing</strong>).</li>
      </ol>
      <details class="dropdown-block">
        <summary>CAPM and Efficient Markets Theory</summary>
        <div class="content">
          <ul>
            <li>Not identical but consistent.</li>
            <li><b>EMH forms:</b>
              <ul>
                <li><b>Weak:</b> Cannot beat the market using only historical price/volume.</li>
                <li><b>Semistrong:</b> Cannot beat the market using all public info (fundamentals, analyst reports, social media).</li>
                <li><b>Strong:</b> Prices reflect <b>all</b> relevant information; no one can systematically outperform.</li>
              </ul>
            </li>
            <li>CAPM says: For every winner there's a loser; absent "greater fools," don't expect to outperform.</li>
            <li>EMH's strong/no-greater-fools view dovetails with CAPM's \(\mathbb{E}[\alpha]=0\) claim.</li>
          </ul>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Consensus Expected Returns</summary>
        <div class="content">
          <ul>
            <li>CAPM's \(\mathbb{E}[\theta_p]=0\) ⇒ <b>passive</b> (market) is optimal.</li>
            <li>In mean–variance terms:
              <ul>
                <li><b>Feed CAPM \(\mathbb{E}[r]\)</b> into Markowitz ⇒ <b>optimal</b> portfolio is the <b>market</b></li>
                <li>(Or some <b>combo</b> of market and cash under full-investment constraints. <strong>KEEP READING.</strong>)</li>
              </ul>
            </li>
            <li>Conversely, <b>assume</b> market is optimal ⇒ back out the \(\mathbb{E}[r]\) that make it so: returns proportional to \(\beta\) w.r.t. that optimal portfolio.</li>
            <li>Hence CAPM \(\mathbb{E}[r]\) are called <b>consensus expected returns</b>: the returns that make the market (consensus portfolio) optimal.</li>
            <li>An <b>active</b> manager's subjective \(\mathbb{E}[r]\) must <b>differ</b> from consensus \(\mathbb{E}[r]\).</li>
          </ul>
        </div>
      </details>
      <p><small>Notation: \(i_F\) risk-free rate; \(r_M\) market excess return; \(\mu_M=\mathbb{E}[r_M]\) market risk premium; \(\beta_P\) beta of \(P\) vs. the market.</small></p>
    </div>
  </details>
</div>

<!-- Flashcard: Ex-ante SML vs. Ex-post line (interactive) -->
<div class="flashcard">
  <details open>
    <summary>"Ex-ante vs. Ex-post": Is it all just Latin?</summary>
    <div class="back">

      <p><strong>CAPM is about expectations.</strong> Ex-ante (CAPM), expected total return lies on the Security Market Line
      \( \mathbb{E}[R_P]= i_F + \beta_P\,\mu_M \) (intercept \(i_F\), slope \( \mu_M \)).
      Ex-post, after realization, plot \( R_P = i_F + \beta_P\, r_M \) (intercept \(i_F\), slope = realized market excess \(r_M\)).
      Vertical gaps from this ex-post line are residuals \( \varepsilon_P = R_P - (i_F+\beta_P r_M)\).
      Value-weighted residuals across the universe sum to ~0.</p>

      <div id="capm-fig-2x" style="width:900px;height:520px;"></div>
      <div id="capm-fig-2x-info" style="font-size:0.9em; opacity:0.95; margin-top:8px;"></div>
      
      <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
      <script>
      function renderCAPMExAnteExPost() {
        // ===== Parameters to mirror the book figures =====
        const i_f  = 0.05;          // risk-free rate (5%)
        const mu_M = 0.07;          // expected excess market return (7%)  — SML slope
        const betas  = [0.8, 1.0, 1.15, 1.3];     // P1, M, P2, P3
        const labels = ["P1","M","P2","P3"];
      
        // ===== Figure 2.1 — Security Market Line (ex-ante) =====
        const x1 = Array.from({length:301}, (_, i) => i * 1.4 / 300);
        const y1 = x1.map(b => i_f + mu_M * b);
      
        const smlLine = {
          x: x1, y: y1, mode: "lines", name: "Security Market Line",
          xaxis: "x", yaxis: "y", hoverinfo: "skip"
        };
        const rfMarker = {
          x: [0], y: [i_f], mode: "markers+text", name: "Risk-free (R_f)",
          text: ["R_f"], textposition: "top left", showlegend: false, xaxis: "x", yaxis: "y"
        };
        const smlPts = {
          x: betas, y: betas.map(b => i_f + mu_M * b),
          mode: "markers+text", name: "Portfolios on SML",
          text: labels, textposition: ["bottom left","bottom center","bottom right","bottom right"],
          xaxis: "x", yaxis: "y"
        };
      
        // ===== Figure 2.2 — Ex-post market line (realizations) =====
        const R_M = 0.02; // realized market return (2%) < R_f ⇒ downward slope like the page
        const x2 = Array.from({length:301}, (_, i) => i * 1.5 / 300);
        const y2 = x2.map(b => i_f + (R_M - i_f) * b);
      
        const exPostLine = {
          x: x2, y: y2, mode: "lines", name: "CAPM Ex-Post Returns",
          xaxis: "x2", yaxis: "y2", hoverinfo: "skip"
        };
        const prime = s => s + "\u2032"; // prime mark
        const exPostPredPts = {
          x: betas, y: betas.map(b => i_f + (R_M - i_f) * b),
          mode: "markers+text", name: "On ex-post line",
          text: [prime("P1"), "M", prime("P2"), prime("P3")],
          textposition: ["bottom left","bottom center","bottom right","bottom right"],
          xaxis: "x2", yaxis: "y2"
        };
      
        // Realized returns (so P3 beats, P1/P2 lag — matches the caption text)
        const realized = [0.010, 0.020, 0.012, 0.050];
        const realizedPts = {
          x: betas, y: realized, mode: "markers+text", name: "Realized Annual Return",
          marker: {symbol: "square", size: 8},
          text: labels, textposition: ["top left","top center","top right","top right"],
          xaxis: "x2", yaxis: "y2"
        };
      
        const data = [smlLine, rfMarker, smlPts, exPostLine, exPostPredPts, realizedPts];
      
        const layout = {
          template: "plotly_white",
          height: 520, width: 900,
          margin: {l: 55, r: 30, t: 70, b: 55},
          legend: {orientation: "h", x: 0.5, xanchor: "center", y: 1.12, yanchor: "bottom"},
          // left subplot (Figure 2.1)
          xaxis:  {domain: [0.00, 0.46], title: "Beta", range: [0, 1.4]},
          yaxis:  {domain: [0.00, 1.00], title: "Expected Annual Return", tickformat: ".0%", range: [0, 0.16]},
          // right subplot (Figure 2.2)
          xaxis2: {domain: [0.54, 1.00], title: "Beta", range: [0, 1.5]},
          yaxis2: {domain: [0.00, 1.00], title: "Expected Annual Return", tickformat: ".0%", range: [0, 0.06]},
          // captions
          annotations: [
            {text: "Figure 2.1 — The Security Market Line", x: 0.23, xref: "paper", y: 1.06, yref: "paper", showarrow: false, font: {size: 13}},
            {text: "Figure 2.2 — An Ex-Post Market Line",  x: 0.77, xref: "paper", y: 1.06, yref: "paper", showarrow: false, font: {size: 13}}
          ]
        };
      
        Plotly.newPlot("capm-fig-2x", data, layout, {displayModeBar: true, responsive: true});
      
        // ===== Info / intuition =====
        const infoHTML = `
          <p><strong>Security Market Line (left).</strong> Consensus CAPM: \\(E[R]=i_f+\\beta\\,\\mu_M\\) with \\(i_f=5\\%\\), \\(\\mu_M=7\\%\\). Points \\(P_1,P_2,P_3\\) and \\(M\\) lie on the line.</p>
          <p><strong>Ex-post line (or '<i>Insecurity</i> Market Line' if you like nerdy finance humor that makes other people want to punch you.) (right).</strong> Connect \\(R_f\\) to realized \\(R_M=2\\%\\): \\(R'=i_f+\\beta\\,(R_M-i_f)\\). Open markers \\(P_1',M,P_2',P_3'\\) lie on that line (CAPM ex-post predictions); filled squares are the realized returns.</p>
          <ul style="margin-top:6px;">
            <li>Vertical gap (square − open marker) = realized residual/alpha.</li>
            <li>Value-weighted residuals net to zero each period; dispersion is idiosyncratic risk.</li>
            <li>Here \\(P_3\\) sits above the line (positive alpha); \\(P_1\\), \\(P_2\\) sit below (negative alphas).</li>
          </ul>`;
        document.getElementById("capm-fig-2x-info").innerHTML = infoHTML;
      }
      renderCAPMExAnteExPost();
      </script>
      <details class="dropdown-block">
        <summary>What does this mean for you, the active investor with the active lifestyle? (cough, day trader, cough.)</summary>
        <div class="content">
          <strong>Goal:</strong> Beat the market.
          <ul>
            <li>CAPM says \(\mathbb{E}[\theta_p]=0\) ⇒ \(\mathbb{E}[r_p]=\beta_p \mu_M\).</li>
            <li>On priors, alpha is a 50–50 proposition. Sheer dumb luck a la McGonagall.; a strict CAPM disciple wouldn't hire an active manager.</li>
          </ul>
          Yet CAPM (and EMH) still <strong>help</strong> actives:
          <ol>
            <li><b>Burden of proof</b> shifts to the manager to explain why insights should produce superior <i>risk-adjusted</i> results (market is at least somewhat efficient).</li>
            <li><b>Decomposition</b> into market vs. residual return needs <b>no theory</b>—only a beta forecast. Many managers therefore target \(\beta \approx 1\) to control market timing risk.</li>
            <li>Provides <b>consensus expected returns</b> (the CAPM line) as a <b>baseline</b>; research can focus on forecasting <b>residual</b> returns (where consensus is zero).</li>
          </ol>
        </div>
      </details>
      <details class="dropdown-block">
        <summary>Your Robinhood trading strategy is only as good as your \(\beta\) forecast.</summary>
        <div class="content">
        <ul>
          <li>Or I guess if we're splitting hairs, your <strong>\(\mu_M\)</strong> is only as good as your \(\beta\) forecast.</li>
          <li>3 ways to do it:
            <ol>
              <li><b>Simple:</b> historical beta from past returns</li>
              <li><b>Improved:</b> <b>Bayesian</b> shrinkage/adjustment to historical betas. <strong>KEEP READING.</strong></li>
              <li><b>Forward-looking risk models</b> (discussed in post coming to a blog near you.) for beta in particular</li>
            </ol>
          </li>
          <li>Estimate \(\mu_M\) from historical excess returns.
            <ul>
              <li>Note: a <b>beta-neutral to benchmark</b> policy needn't estimate \(\mu_M\); with <b>portfolio \(\beta=1.0\)</b> vs. the market benchmark, the market excess return does <b>not</b> contribute to <b>active</b> return.</li>
            </ul>
          </li>
        </ul>
      </details>
    </div>
  </details>
</div>

{% capture appendix %}
<div class="flashcard">
  <details>
    <summary>For all the dudes out there with shrinking feet</summary>
    <div class="back">
      <p>tldr: treat the <em>true</em> beta as a random variable with a prior (usually near 1 for equities), and combine that prior with the noisy OLS beta you estimate from returns. The posterior mean is a <strong>shrunk</strong> beta—pulled toward the prior by an amount that depends on the OLS standard error.</p>

      <details class="dropdown-block">
        <summary>What it is (model)</summary>
        <div class="content">
          <p>For asset \(i\) with excess returns \(r_{i,t}\) and market \(r_{M,t}\),</p>
          <p>\[
          r_{i,t}=\alpha_i+\beta_i\,r_{M,t}+\varepsilon_{i,t},\qquad \varepsilon_{i,t}\sim \mathcal N(0,\sigma_\varepsilon^2).
          \]</p>
          <p>OLS gives \(\hat\beta_i\) and its sampling variance</p>
          <p>\[
          s_i^2 \;=\; \widehat{\operatorname{Var}}(\hat\beta_i\mid\beta_i)
          \;=\; \frac{\hat\sigma_{\varepsilon,i}^2}{\sum_{t}(r_{M,t}-\bar r_M)^2}.
          \]</p>
          <p>Place a Normal prior on the true beta:</p>
          <p>\[
          \beta_i \sim \mathcal N(\beta_{0,i},\,\tau^2).
          \]</p>
          <p>Conjugacy ⇒ posterior mean (the shrinkage estimator):</p>
          <p>\[
          \tilde\beta_i
          = \underbrace{\frac{\tau^2}{\tau^2+s_i^2}}_{w_i}\,\hat\beta_i
          \;+\;
          \underbrace{\frac{s_i^2}{\tau^2+s_i^2}}_{1-w_i}\,\beta_{0,i},
          \qquad 
          \operatorname{Var}(\beta_i\mid\text{data})=\frac{\tau^2 s_i^2}{\tau^2+s_i^2}.
          \]</p>
          <div class="define">
            <p><small><strong>Deriving the shrinkage estimator (a ruler from the base, I thought...)</strong></small></p>
              <h3>Setup</h3>
              <p>We observe an OLS beta estimate \(\hat\beta_i\) for asset \(i\) with known sampling variance \(s_i^2\), and we place a Normal prior on the true beta \(\beta_i\).</p>
              <p>\[
              \hat\beta_i \mid \beta_i \sim \mathcal{N}\!\left(\beta_i,\, s_i^2\right)
              \]</p>
              <p>\[
              \beta_i \sim \mathcal{N}\!\left(\beta_{0,i},\, \tau^2\right)
              \]</p>
              <p>Goal: compute the posterior \(p(\beta_i \mid \hat\beta_i)\) and extract its mean and variance.</p>

              <h3>Derivation — by completing the square</h3>
              <p><strong>1) Write the unnormalized posterior density.</strong></p>
              <p>\[
              p(\beta_i \mid \hat\beta_i) \ \propto\ p(\hat\beta_i \mid \beta_i)\,p(\beta_i)
              \]</p>
              <p>\[
              \propto \exp\!\left(-\frac{1}{2}\frac{(\hat\beta_i-\beta_i)^2}{s_i^2}\right)\,
              \exp\!\left(-\frac{1}{2}\frac{(\beta_i-\beta_{0,i})^2}{\tau^2}\right)
              \]</p>

              <p><strong>2) Combine exponents and expand the squares.</strong></p>
              <p>\[
              -\frac{1}{2}\Bigg[
              \frac{(\hat\beta_i-\beta_i)^2}{s_i^2}+\frac{(\beta_i-\beta_{0,i})^2}{\tau^2}
              \Bigg]
              =
              -\frac{1}{2}\Bigg[
              \left(\frac{1}{s_i^2}+\frac{1}{\tau^2}\right)\beta_i^2
              -2\left(\frac{\hat\beta_i}{s_i^2}+\frac{\beta_{0,i}}{\tau^2}\right)\beta_i
              +\text{const}
              \Bigg]
              \]</p>
              <p>Define the <strong>precisions</strong> to keep notation clean</p>
              <p>\[
              \lambda := \frac{1}{s_i^2}, \qquad \kappa := \frac{1}{\tau^2}
              \]</p>
              <p>and set</p>
              <p>\[
              A := \lambda+\kappa, \qquad B := \lambda\,\hat\beta_i+\kappa\,\beta_{0,i}
              \]</p>
              <p>Then the exponent becomes</p>
              <p>\[
              -\frac{1}{2}\Big[A\,\beta_i^2-2B\,\beta_i+\text{const}\Big]
              \]</p>

              <p><strong>3) Complete the square in \(\beta_i\).</strong></p>
              <p>\[
              A\,\beta_i^2-2B\,\beta_i
              =
              A\Big(\beta_i-\frac{B}{A}\Big)^2 - \frac{B^2}{A}
              \]</p>
              <p>Thus</p>
              <p>\[
              p(\beta_i \mid \hat\beta_i)\ \propto\
              \exp\!\left(-\frac{1}{2}A\Big(\beta_i-\frac{B}{A}\Big)^2\right)
              \]</p>
              <p>This is the kernel of a Normal with mean \(B/A\) and variance \(1/A\).</p>
              <p>\[
              \beta_i \mid \hat\beta_i \sim \mathcal{N}\!\left(\frac{B}{A},\, \frac{1}{A}\right)
              \]</p>

              <p><strong>4) Undo the shorthand \(A,B,\lambda,\kappa\).</strong></p>
              <p>Posterior <strong>mean</strong>:</p>
              <p>\[
              \frac{B}{A}
              =
              \frac{\lambda\,\hat\beta_i+\kappa\,\beta_{0,i}}{\lambda+\kappa}
              =
              \frac{\hat\beta_i/s_i^2+\beta_{0,i}/\tau^2}{1/s_i^2+1/\tau^2}
              =
              \frac{\tau^2\,\hat\beta_i+s_i^2\,\beta_{0,i}}{\tau^2+s_i^2}
              \]</p>
              <p>Posterior <strong>variance</strong>:</p>
              <p>\[
              \frac{1}{A}=\frac{1}{\lambda+\kappa}
              =
              \frac{1}{1/s_i^2+1/\tau^2}
              =
              \frac{\tau^2 s_i^2}{\tau^2+s_i^2}
              \]</p>

              <p><strong>5) Put the mean into "weighted average" form.</strong></p>
              <p>Define the shrinkage weight</p>
              <p>\[
              w_i := \frac{\tau^2}{\tau^2+s_i^2}
              \]</p>
              <p>Then</p>
              <p>\[
              \tilde\beta_i := \mathbb{E}[\beta_i \mid \hat\beta_i]
              = w_i\,\hat\beta_i + (1-w_i)\,\beta_{0,i}
              \]</p>
              <p>and</p>
              <p>\[
              \operatorname{Var}(\beta_i \mid \hat\beta_i) = \frac{\tau^2 s_i^2}{\tau^2+s_i^2}
              \]</p>

              <h3>In English</h3>
              <p>Bayes turns two Normal sources of information into a <strong>precision-weighted average</strong>:</p>
              <p>\[
              \tilde\beta_i
              =
              \underbrace{\frac{1}{s_i^2}}_{\text{data precision}}
              \Big/
              \underbrace{\left(\frac{1}{s_i^2}+\frac{1}{\tau^2}\right)}_{\text{total precision}}
              \cdot \hat\beta_i
              \;+\;
              \underbrace{\frac{1}{\tau^2}}_{\text{prior precision}}
              \Big/
              \underbrace{\left(\frac{1}{s_i^2}+\frac{1}{\tau^2}\right)}_{\text{total precision}}
              \cdot \beta_{0,i}
              \]</p>
              <p>Equivalently, in variance space, weights are \(\tau^2\) vs \(s_i^2\). If data are precise (\(s_i^2 \downarrow\)), the posterior leans toward \(\hat\beta_i\). If data are noisy, it leans toward \(\beta_{0,i}\). The posterior variance is <strong>smaller</strong> than either \(s_i^2\) or \(\tau^2\) because precisions add.</p>
            </div>
          </div>
          <ul>
            <li>If \(\hat\beta_i\) is <strong>precise</strong> (\(s_i^2\downarrow\)), \(w_i\to 1\) ⇒ little shrinkage.</li>
            <li>If \(\hat\beta_i\) is <strong>noisy</strong>, \(w_i\to 0\) ⇒ strong pull toward \(\beta_{0,i}\).</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>How to do this (practical steps)</summary>
        <div class="content">
          <p><strong>A. Pick/estimate the prior \((\beta_{0,i},\tau^2)\).</strong></p>
          <ul>
            <li>Easiest (Vasicek/empirical Bayes, market-wide):
              \(\beta_{0,i}=\bar{\hat\beta}\) or simply \(1\);
              \(\tau^2 = \max\{0,\,\operatorname{Var}_\text{cross}(\hat\beta_i)-\overline{s_i^2}\}\).</li>
          </ul>
          
          <p><strong>B. Compute OLS betas and errors.</strong></p>
          <ul>
            <li>For each asset, run the regression, get \(\hat\beta_i\) and \(s_i^2\) (use Newey–West if you want to be robust).</li>
          </ul>
          
          <p><strong>C. Shrink.</strong></p>
          <ul>
            <li>Apply \(\tilde\beta_i=w_i\hat\beta_i+(1-w_i)\beta_{0,i}\) with \(w_i=\tau^2/(\tau^2+s_i^2)\).</li>
          </ul>
          
          <p><strong>D. Re-scale (optional but recommended).</strong></p>
          <ul>
            <li>Enforce the identity \(\sum_i v_i\,\tilde\beta_i=1\) (value-weighted to your market proxy) by multiplying all \(\tilde\beta_i\) by a common scalar so the weighted average is 1.</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Markowitz, Markowitz... (a la 'Malkovich, Malkovich' from 'Being John Malkovich')</summary>
    <div class="back">
      <details class="dropdown-block">
        <summary>Notation & Setup</summary>
        <div class="content">
          <p><strong>Notation</strong></p>
          <ul>
            <li>\(N\) assets, return covariance \(V\in\mathbb{R}^{N\times N}\), \(V\succ 0\).</li>
            <li>Attribute (characteristic) vector \(a\in\mathbb{R}^N\).</li>
            <li>Portfolio weights \(h\in\mathbb{R}^N\).</li>
            <li>Exposure of portfolio \(h\) to attribute \(a\) is the scalar \(a^\top h\).</li>
            <li>The characteristic portfolio for \(a\) is the minimum-variance portfolio with unit exposure \(a^\top h=1\). We'll denote it \(h_a\).</li>
          </ul>
          
          <p><strong>Variance of Portfolio Returns</strong></p>
          <p>\(R\in\mathbb{R}^N\) is the <strong>random vector of asset returns</strong> for one period.
          Let \(\mu:=\mathbb{E}[R]\) and \(V:=\operatorname{Cov}(R)=\mathbb{E}\!\big[(R-\mu)(R-\mu)^\top\big]\), with \(V\succ0\).
          For any deterministic portfolio weights \(h\), the portfolio return is the scalar \(R_h:=h^\top R\), and</p>
          
          <p>\[
          \operatorname{Var}(R_h)=\operatorname{Var}(h^\top R)=h^\top V h
          \]</p>
          
          <p>since</p>
          
          <p>\[
          \operatorname{Var}(h^\top R)
          =\mathbb{E}\!\big[(h^\top(R-\mu))^2\big]
          =\mathbb{E}\!\big[h^\top(R-\mu)(R-\mu)^\top h\big]
          =h^\top\,\mathbb{E}\!\big[(R-\mu)(R-\mu)^\top\big]\,h
          =h^\top V h
          \]</p>
          
          <p>using linearity and the fact that \(h\) is non-random.</p>
          
          <p><strong>Covariance of Each Asset & Portfolio Returns</strong></p>
          <p>\[
          \operatorname{Cov}\!\big(R,\;h^\top R\big)=Vh.
          \]</p>
          
          <p><strong>Derivation</strong></p>
          <p>\[
          \operatorname{Cov}(R,\;h^\top R)
          =\mathbb{E}\!\big[(R-\mu)\,(h^\top R-\mathbb{E}[h^\top R])\big].
          \]</p>
          
          <p>\[
          \mathbb{E}[h^\top R]=h^\top\mu
          \;\Rightarrow\;
          h^\top R-\mathbb{E}[h^\top R]
          =h^\top(R-\mu).
          \]</p>
          
          <p>\[
          \operatorname{Cov}(R,\;h^\top R)
          =\mathbb{E}\!\big[(R-\mu)\,h^\top(R-\mu)\big].
          \]</p>
          
          <p>\[
          \operatorname{Cov}(R,\;h^\top R)
          =\mathbb{E}\!\big[(R-\mu)(R-\mu)^\top\big]\,h
          =Vh.
          \]</p>
          
          <p><strong>Characteristic Portfolios</strong></p>
          <ul>
            <li>Assets have attributes (betas, \(E/P\), sector, …). To any attribute vector \(\mathbf{a}^T=\{a_1,\dots,a_N\}\) associate a <strong>characteristic portfolio</strong> \(\mathbf{h}_a\) that uniquely captures that attribute.</li>
            <li><strong>Exposure</strong> of portfolio \(\mathbf{h}_p\) to attribute \(\mathbf{a}\):</li>
          </ul>
          <p>\[
          a_p \;=\; \sum_{k} a_k\,h_{pk}.
          \]</p>
          <p>This machinery lets us measure portfolio exposure to an attribute via covariance with the attribute's characteristic portfolio, and also invert the mapping (find which attribute a given portfolio best expresses).</p>
          
          <p><strong>Proposition 1</strong></p>
          <ol>
            <li><strong>Existence/uniqueness (unit-exposure, min-risk):</strong> For any attribute \(\mathbf{a}\neq \mathbf{0}\), there is a unique portfolio \(\mathbf{h}_a\) with <strong>unit exposure</strong> to \(\mathbf{a}\) and <strong>minimum variance</strong>. Its holdings are</li>
          </ol>
          <p>\[
          \mathbf{h}_a \;=\; \frac{\mathbf{V}^{-1}\mathbf{a}}{\mathbf{a}^T \mathbf{V}^{-1}\mathbf{a}} 
          \]</p>
          <p>(Characteristic portfolios need not be fully invested; they may be long/short and leveraged. In practice we can combine with a benchmark to deleverage when building investable portfolios.)</p>
          
          <ol start="2">
            <li><strong>Variance of the characteristic portfolio:</strong></li>
          </ol>
          <p>\[
          \sigma_a^2 \;=\; \mathbf{h}_a^T \mathbf{V}\,\mathbf{h}_a \;=\; \frac{1}{\mathbf{a}^T \mathbf{V}^{-1}\mathbf{a}} 
          \]</p>
          
          <ol start="3">
            <li><strong>Betas to \(\mathbf{h}_a\):</strong> The vector of asset betas <strong>with respect to</strong> portfolio \(\mathbf{h}_a\) equals the attribute:</li>
          </ol>
          <p>\[
          \mathbf{a} \;=\; \frac{\mathbf{V}\,\mathbf{h}_a}{\sigma_a^{2}} 
          \]</p>
          
          <ol start="4">
            <li><strong>Two attributes \(\mathbf{a},\mathbf{d}\):</strong> With characteristic portfolios \(\mathbf{h}_a,\mathbf{h}_d\) and exposures \(a_q\) and \(d_q\), the covariance satisfies</li>
          </ol>
          <p>\[
          \sigma_{a,d} \;=\; a_q\,\sigma_d^2 \;=\; d_q\,\sigma_a^2 
          \]</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Prop. 1 Proof</summary>
        <div class="content">
          <p><strong>1) Existence/uniqueness and closed form for \(h_a\)</strong></p>
          <p><strong>Optimization problem:</strong></p>
          <p>\[
          \min_{h\in\mathbb{R}^N}\; h^\top V h
          \quad\text{s.t.}\quad
          a^\top h = 1.
          \]</p>
          
          <p><strong>Lagrangian:</strong></p>
          <p>\[
          L(h,\lambda)=f(h)-\lambda\big(g(h)-1\big)
          = h^\top V h-\lambda\big(a^\top h-1\big).
          \]</p>
          
          <p><strong>FOC:</strong></p>
          <p>\[
          \nabla f(h)=\lambda\,\nabla g(h),
          \qquad
          g(h)=1.
          \]</p>
          
          <p>Compute the gradients:</p>
          <p>\[
          \nabla f(h)=2Vh
          \quad(\text{since }V=V^\top\text{ is a covariance matrix}),
          \qquad
          \nabla g(h)=a.
          \]</p>
          
          <p>Set them equal and solve:</p>
          <p>\[
          2Vh=\lambda a
          \;\Rightarrow\;
          Vh=\frac{\lambda}{2}\,a
          \;\Rightarrow\;
          h=\frac{\lambda}{2}\,V^{-1}a.
          \]</p>
          
          <p>Enforce the constraint \(a^\top h=1\):</p>
          <p>\[
          1=a^\top h
          = a^\top\!\left(\frac{\lambda}{2}V^{-1}a\right)
          = \frac{\lambda}{2}\,a^\top V^{-1}a
          \;\Rightarrow\;
          \lambda=\frac{2}{a^\top V^{-1}a}.
          \]</p>
          
          <p>Plug back:</p>
          <p>\[
          \boxed{\,h_a=\frac{V^{-1}a}{a^\top V^{-1}a}\,}.
          \]</p>
          
          <p><strong>Existence/uniqueness.</strong> \(V\succ0\Rightarrow f(h)=h^\top Vh\) is strictly convex and \(\nabla^2 f(h)=2V\succ0\). The feasible set \(\{h:a^\top h=1\}\) is a nonempty affine hyperplane and is convex. A strictly convex function on a convex set has a unique minimizer, so \(h_a\) above is the unique solution.</p>
          
          <p>(and for below parts of proof, for brevity):</p>
          <p>\[
          \text{ define }c_a:=a^\top V^{-1}a>0
          \]</p>
          
          <p><strong>2) Variance of the characteristic portfolio</strong></p>
          <p>\[
          \sigma_a^2:=\operatorname{Var}(h_a^\top R)=h_a^\top V h_a
          \]</p>
          
          <p>Plug \(h_a=(V^{-1}a)/c_a\):</p>
          <p>\[
          \begin{aligned}
          h_a^\top V h_a
          &=\left(\frac{V^{-1}a}{c_a}\right)^\top V \left(\frac{V^{-1}a}{c_a}\right)\\[4pt]
          &=\frac{a^\top V^{-1} V V^{-1} a}{c_a^2}\\[4pt]
          &=\frac{a^\top V^{-1} a}{c_a^2}\\[4pt]
          &=\frac{c_a}{c_a^2}
          =\frac{1}{c_a}
          =\boxed{\frac{1}{a^\top V^{-1}a}}
          \end{aligned}
          \]</p>
          
          <p>which is the stated formula.</p>
          
          <p><strong>3) Betas w.r.t. \(h_a\) equal the attribute \(a\)</strong></p>
          <p>For any reference portfolio \(P\) with weights \(h_P\), define the vector of asset betas <strong>with respect to \(P\)</strong> by</p>
          <p>\[
          \beta^{(P)}:=\frac{\operatorname{Cov}(R,\,R_P)}{\operatorname{Var}(R_P)}
          =\frac{V h_P}{h_P^\top V h_P}
          \]</p>
          
          <p>because \(\operatorname{Cov}(R,\,h_P^\top R)=Vh_P\) and \(\operatorname{Var}(R_P)=h_P^\top V h_P\).</p>
          
          <p>Set \(P=h_a\). Then</p>
          <p>\[
          V h_a = V\left(\frac{V^{-1}a}{c_a}\right)=\frac{a}{c_a}
          \]</p>
          
          <p>and from item 2,</p>
          <p>\[
          \sigma_a^2=h_a^\top V h_a=\frac{1}{c_a}
          \]</p>
          
          <p>so</p>
          <p>\[
          \beta^{(h_a)}
          =\frac{V h_a}{\sigma_a^2}
          =\frac{\frac{a}{c_a}}{\frac{1}{c_a}}
          =\boxed{a}
          \]</p>
          
          <p>i.e., each asset's beta to the characteristic portfolio equals its attribute value.</p>
          
          <p><strong>4) Covariance between two characteristic portfolios (Eq. 2A.4)</strong></p>
          <p>Let \(d\in\mathbb{R}^N\) be a second attribute with characteristic portfolio \(h_d=\dfrac{V^{-1}d}{d^\top V^{-1}d}\) and variance \(\sigma_d^2=\frac{1}{c_d}\).</p>
          
          <p>Define the <strong>cross-exposures</strong></p>
          <p>\[
          a_{h_d}:=a^\top h_d
          \quad\text{(exposure of \(h_d\) to attribute \(a\))},\qquad
          d_{h_a}:=d^\top h_a
          \quad\text{(exposure of \(h_a\) to attribute \(d\))}.
          \]</p>
          
          <p>Compute the covariance:</p>
          <p>\[
          \sigma_{a,d}
          :=\operatorname{Cov}(R_{h_a},R_{h_d})
          = h_a^\top V h_d.
          \]</p>
          
          <p>Two equivalent ways to evaluate the scalar \(h_a^\top V h_d\):</p>
          
          <p><strong>Route A (push \(V\) to the left using \(Vh_a=a/c_a\)):</strong></p>
          <p>\[
          h_a^\top V h_d
          =(Vh_a)^\top h_d
          =\left(\frac{a}{c_a}\right)^\top h_d
          =\frac{a^\top h_d}{c_a}
          =a_{h_d}\,\sigma_a^2.
          \]</p>
          
          <p><strong>Route B (push \(V\) to the right using \(Vh_d=d/c_d\)):</strong></p>
          <p>\[
          h_a^\top V h_d
          =h_a^\top\left(\frac{d}{c_d}\right)
          =\frac{d^\top h_a}{c_d}
          =d_{h_a}\,\sigma_d^2.
          \]</p>
          
          <p>Hence</p>
          <p>\[
          \boxed{\,\sigma_{a,d}=a_{h_d}\,\sigma_a^2
          = d_{h_a}\,\sigma_d^2\,}.
          \]</p>
          
          <p><strong>Quick consistency checks</strong></p>
          <ul>
            <li><strong>Unit exposure:</strong> By construction \(a^\top h_a=1\) and \(d^\top h_d=1\).</li>
            <li><strong>Symmetry:</strong> \(\sigma_{a,d}=\sigma_{d,a}\) is obvious from \(h_a^\top V h_d\) being a scalar and from the two routes above.</li>
          </ul>
          
          <p><strong>In english (what was the point)</strong></p>
          <ul>
            <li>\(\mathbf{h}_a\) is the <strong>min-variance portfolio</strong> that loads <strong>one unit</strong> on attribute \(\mathbf{a}\). It's the orthogonal-projection analogue in mean–variance space.
              <ul>
                <li>The characteristic portfolio \(h_a\) is "the cheapest way" (lowest variance) to get one unit of attribute \(a\). Its weights are the <strong>generalized regression coefficients</strong> of \(a\) on the assets under metric \(V\): \(V^{-1}a\) normalized to unit exposure.</li>
              </ul>
            </li>
            <li>The optimizer solution gives closed-form <strong>weights</strong>, <strong>risk</strong>, and <strong>betas</strong>; together they show that "betas to the characteristic portfolio = the attribute itself."
              <ul>
                <li>the characteristic portfolio is the <strong>factor-mimicking portfolio</strong> for \(a\).</li>
                <li>Cross-covariances equal "other attribute exposure \(\times\) variance": covariance is large either because the two attributes load on each other (large cross-exposure) or because the target attribute is intrinsically volatile (large \(\sigma^2\)).</li>
              </ul>
            </li>
          </ul>
        </div>
      </details>
      <details class="dropdown-slider">
        <summary>
          <div class="summary-title">The Scaling & Mixture Corollaries</div>
        </summary>
        <input type="checkbox" id="scaling-mixture-toggle" class="slider-toggle">
        <div class="slider-container">
          <div class="primary">
            <p><b>Scaling:</b> For positive scalar \(\kappa\), the characteristic portfolio of \(\kappa \mathbf{a}\) rescales to preserve unit exposure (i.e., \(\mathbf{h}_{\kappa a} = \mathbf{h}_a/\kappa\)).</p>

            <p><b>Linear combination of attributes:</b> If \(\mathbf{a}\) is a weighted combination of attributes \(\mathbf{d}\) and \(\mathbf{f}\), say \(\mathbf{a}=\kappa_d \mathbf{d}+\kappa_f \mathbf{f}\), then the corresponding characteristic portfolio is the matching weighted combination:</p>

            <p>\[
            \mathbf{h}_a \;=\; \Big(\frac{\kappa_d \sigma_d^2}{\sigma_a^2}\Big)\mathbf{h}_d \;+\; \Big(\frac{\kappa_f \sigma_f^2}{\sigma_a^2}\Big)\mathbf{h}_f
            \]</p>

            <p>with</p>

            <p>\[
            \frac{1}{\sigma_a^2} \;=\; \frac{\kappa_d^2}{\sigma_d^2} \;+\; \frac{\kappa_f^2}{\sigma_f^2}.
            \]</p>
            <label for="scaling-mixture-toggle" class="split-arrow"></label>
          </div>
          <div class="secondary">
            <p><strong>The Proof of the Scaling & Mixture Corollaries</strong></p>
            <p><strong>Scaling</strong></p>
            <p><b>Goal.</b> Show for \(\kappa>0\):</p>
            <p>\[
            h_{\kappa a}=\frac{h_a}{\kappa}
            \]</p>
            <p>\[
            \sigma_{\kappa a}^2=\frac{\sigma_a^2}{\kappa^2}
            \]</p>

            <p><b>Definition (Item 1).</b></p>
            <p>\[
            h_x=\frac{V^{-1}x}{x^\top V^{-1}x},\qquad
            \sigma_x^2=\frac{1}{x^\top V^{-1}x}
            \]</p>

            <p><b>Apply with \(x=\kappa a\).</b></p>
            <p>\[
            h_{\kappa a}
            =\frac{V^{-1}(\kappa a)}{(\kappa a)^\top V^{-1}(\kappa a)}
            =\frac{\kappa V^{-1}a}{\kappa^2\,a^\top V^{-1}a}
            =\frac{1}{\kappa}\,\frac{V^{-1}a}{a^\top V^{-1}a}
            =\frac{h_a}{\kappa}
            \]</p>

            <p>\[
            \sigma_{\kappa a}^2
            =\frac{1}{(\kappa a)^\top V^{-1}(\kappa a)}
            =\frac{1}{\kappa^2\,a^\top V^{-1}a}
            =\frac{\sigma_a^2}{\kappa^2}
            \]</p>

            <p><b>Unit-exposure check.</b></p>
            <p>\[
            (\kappa a)^\top h_{\kappa a}
            =(\kappa a)^\top\!\left(\frac{h_a}{\kappa}\right)
            =a^\top h_a
            =1
            \]</p>

            <p><b>In words:</b> change the <b>units</b> of the attribute, not the economics. If you double the attribute scale, you need half as much portfolio to get one unit of exposure; variance scales like a square.</p>

            <p><b>Why it's important:</b> invariance to labeling. Whether \(a\) is "beta in %" or "beta in decimals," your exposure mechanism behaves consistently.</p>

            <p><strong>Mixture part a) Linear combination of attributes</strong></p>
            <p>Let \(a=\kappa_d d+\kappa_f f\). Define</p>
            <p>\[
            h_d=\frac{V^{-1}d}{d^\top V^{-1}d},\quad
            h_f=\frac{V^{-1}f}{f^\top V^{-1}f}
            \]</p>
            <p>\[
            \sigma_d^2=\frac{1}{d^\top V^{-1}d},\quad
            \sigma_f^2=\frac{1}{f^\top V^{-1}f},\quad
            \sigma_a^2=\frac{1}{a^\top V^{-1}a}
            \]</p>

            <p><b>Mixture representation for \(h_a\):</b></p>
            <p>From the solution to the quad prog,</p>
            <p>\[
            h_a=\frac{V^{-1}a}{a^\top V^{-1}a}
            =\frac{\kappa_d V^{-1}d+\kappa_f V^{-1}f}{a^\top V^{-1}a}
            \]</p>

            <p>Use \(h_d=\sigma_d^2 V^{-1}d\Rightarrow V^{-1}d=\frac{1}{\sigma_d^2}h_d\) and similarly \(V^{-1}f=\frac{1}{\sigma_f^2}h_f\). Also \(a^\top V^{-1}a=\frac{1}{\sigma_a^2}\). Thus</p>
            <p>\[
            h_a
            =\sigma_a^2\!\left(\frac{\kappa_d}{\sigma_d^2}h_d+\frac{\kappa_f}{\sigma_f^2}h_f\right)
            \]</p>

            <p>Equivalently,</p>
            <p>\[
            \boxed{\,h_a=\left(\frac{\kappa_d\,\sigma_a^2}{\sigma_d^2}\right)h_d
            +\left(\frac{\kappa_f\,\sigma_a^2}{\sigma_f^2}\right)h_f\,}
            \]</p>

            <p><strong>Mixture part b) Variance \(\sigma_a^2\) and orthogonal special case</strong></p>
            <p>By Item 2 (Variance of the characteristic portfolio),</p>
            <p>\[
            \frac{1}{\sigma_a^2}
            =a^\top V^{-1}a
            =(\kappa_d d+\kappa_f f)^\top V^{-1}(\kappa_d d+\kappa_f f)
            \]</p>

            <p><b>1) Distribute the quadratic form (bilinearity).</b></p>
            <p>\[
            = (\kappa_d d)^\top V^{-1}(\kappa_d d)
            +(\kappa_f f)^\top V^{-1}(\kappa_f f)
            +(\kappa_d d)^\top V^{-1}(\kappa_f f)
            +(\kappa_f f)^\top V^{-1}(\kappa_d d)
            \]</p>

            <p><b>2) Pull out scalars \(\kappa_d,\kappa_f\).</b></p>
            <p>\[
            = \kappa_d^2\, d^\top V^{-1} d
            +\kappa_f^2\, f^\top V^{-1} f
            +\kappa_d\kappa_f\, d^\top V^{-1} f
            +\kappa_d\kappa_f\, f^\top V^{-1} d
            \]</p>

            <p><b>3) Use symmetry of \(V^{-1}\) so \(d^\top V^{-1} f=f^\top V^{-1} d\).</b></p>
            <p>\[
            = \kappa_d^2\, d^\top V^{-1} d
            +\kappa_f^2\, f^\top V^{-1} f
            +2\kappa_d\kappa_f\, d^\top V^{-1} f
            \]</p>

            <p><b>4) Substitute the variance identities \(d^\top V^{-1} d=1/\sigma_d^2\) and \(f^\top V^{-1} f=1/\sigma_f^2\).</b></p>
            <p>\[
            = \frac{\kappa_d^2}{\sigma_d^2}
            +\frac{\kappa_f^2}{\sigma_f^2}
            +2\kappa_d\kappa_f\, d^\top V^{-1} f
            \]</p>

            <p>Relate the cross term to Item 4. Since</p>
            <p>\[
            \sigma_{d,f}:=\operatorname{Cov}(R_{h_d},R_{h_f})
            =h_d^\top V h_f
            =\sigma_d^2\sigma_f^2\,d^\top V^{-1}f
            \]</p>

            <p>we have \(d^\top V^{-1}f=\sigma_{d,f}/(\sigma_d^2\sigma_f^2)\). Hence</p>
            <p>\[
            \boxed{\;\frac{1}{\sigma_a^2}
            =\frac{\kappa_d^2}{\sigma_d^2}
            +\frac{\kappa_f^2}{\sigma_f^2}
            +\frac{2\kappa_d\kappa_f\,\sigma_{d,f}}{\sigma_d^2\sigma_f^2}\;}
            \]</p>

            <p><b>Orthogonal special case.</b> If \(d\) and \(f\) are \(V^{-1}\)-orthogonal (equivalently \(\sigma_{d,f}=0\)), only the first two terms remain.:</p>
            <p>\[
            \boxed{\;\frac{1}{\sigma_a^2}
            =\frac{\kappa_d^2}{\sigma_d^2}
            +\frac{\kappa_f^2}{\sigma_f^2}\;}
            \]</p>

            <p><b>In words:</b> the <b>portfolio map is linear</b> under the \(V^{-1}\) metric. A composite attribute is implemented by a matching composite of its characteristic portfolios, with weights adjusted by their variances. The variance formula is just the usual "sum plus cross-term"; if \(h_d\) and \(h_f\) are uncorrelated, it becomes Pythagorean.</p>

            <p><b>Why it's important:</b> you can modularly build complex factors from a base library of characteristic portfolios, and you can <b>orthogonalize</b> them by making \(d,f\) \(V^{-1}\)-orthogonal, giving uncorrelated factor returns.</p>
          </div>
        </div>
      </details>
      <details class="dropdown-block">
        <summary>Characteristic Portfolio Examples: Charles and Bob</summary>
        <div class="content">
          <p><strong>Portfolio \(C\): The minimum-risk fully invested characteristic portfolio</strong></p>
          <ul>
            <li>Let the <b>attribute</b> be the all-ones vector</li>
          </ul>
          <p>\[
          \mathbf{e}^{\!T}=\{1,1,\ldots,1\}
          \]</p>
          
          <p>The <b>exposure</b> of portfolio \(p\) to \(\mathbf{e}\) is \(e_p=\sum_n h_{pn}\) (its investment level). If \(e_p=1\), the portfolio is <b>fully invested</b>.</p>
          
          <p><b>Attribute & exposure.</b><br>
          Exposure of any portfolio \(h\) to "fully invested" is</p>
          <p>\[
          e_h := e^\top h.
          \]</p>
          
          <p><b>Characteristic portfolio for \(e\).</b> By Prop 1. Item 1,</p>
          <p>\[
          h_C=\frac{V^{-1}e}{e^\top V^{-1}e}.
          \]</p>
          
          <p><b>Variance.</b> By Prop 1. Item 2,</p>
          <p>\[
          \sigma_C^2
          = h_C^\top V h_C
          = \frac{1}{\,e^\top V^{-1}e\,}.
          \]</p>
          
          <p><b>Betas wrt \(h_a\)</b> By Prop 1. Item 3,</p>
          <p>\[
          Vh_C=\sigma_C^2\,e
          \quad\Longleftrightarrow\quad
          e=\frac{Vh_C}{\sigma_C^2}.
          \]</p>
          
          <p><b>"Every asset has beta 1 w.r.t. \(C\)".</b><br>
          Asset-level betas relative to \(C\) are</p>
          <p>\[
          \beta^{(C)}=\frac{Vh_C}{\sigma_C^2}=e,
          \]</p>
          <p>so each asset's beta to \(C\) is \(1\).</p>
          
          <p><b>Covariance of any portfolio \(P\) with \(C\).</b> Using Item 4,</p>
          <p>\[
          \sigma_{P,C}
          = h_P^\top V h_C
          = h_P^\top(\sigma_C^2 e)
          = \sigma_C^2\,e_P,
          \]</p>
          <p>so if \(P\) is fully invested \((e_P=1)\) then \(\sigma_{P,C}=\sigma_C^2\).</p>
          
          <p><b>En ingles.</b> \(C\) is the unique minimum-variance fully-invested portfolio. Because \(Vh_C=\sigma_C^2 e\), every asset (and any fully invested portfolio) "lines up" with \(C\): their covariance with \(C\) is just their investment level times \(\sigma_C^2\).</p>
          
          <p><b>En mas ingles.</b> In \(C\), each asset's <b>marginal contribution to risk</b> is proportional to its beta to the portfolio. If those contributions weren't identical, you could trade to reduce total risk, contradicting minimality. Since the portfolio's own beta to itself is 1, each asset's beta to \(C\) must be 1.</p>
          
          <p><strong>Portfolio \(B\): The benchmark</strong></p>
          <p><b>Define the beta attribute via \(B\).</b></p>
          <p>\[
          \beta := \frac{\operatorname{Cov}(R,\,R_B)}{\operatorname{Var}(R_B)}
          = \frac{Vh_B}{\sigma_B^2}.
          \]</p>
          
          <p><b>Characteristic portfolio of \(\beta\) equals \(B\).</b> By Prop 1. Item 1,</p>
          <p>\[
          h_\beta=\frac{V^{-1}\beta}{\beta^\top V^{-1}\beta}.
          \]</p>
          
          <p>Plug \(\beta=\dfrac{Vh_B}{\sigma_B^2}\):</p>
          <p>\[
          V^{-1}\beta=\frac{1}{\sigma_B^2}h_B,
          \qquad
          \beta^\top V^{-1}\beta
          =\frac{1}{\sigma_B^4}\,h_B^\top V h_B
          =\frac{1}{\sigma_B^2}.
          \]</p>
          
          <p>Hence</p>
          <p>\[
          h_\beta=\frac{(1/\sigma_B^2)h_B}{\,1/\sigma_B^2\,}
          =\boxed{\,h_B\,}.
          \]</p>
          
          <p><b>Variance of the \(\beta\) characteristic portfolio.</b></p>
          <p>\[
          \sigma_\beta^2
          =\frac{1}{\beta^\top V^{-1}\beta}
          =\boxed{\,\sigma_B^2\,}.
          \]</p>
          
          <p><b>En ingles:</b> the <b>benchmark is the min-risk portfolio among all \(\beta=1\) portfolios</b> (it has the same systematic risk as any \(\beta=1\) portfolio and <b>zero residual risk</b>, so its total risk is the smallest).</p>
          
          <p><strong>Relationship between \(B\) and \(C\) (Prop 1. Item 4 with \(a=\beta,\;d=e\)).</strong></p>
          <p>\[
          \sigma_{B,C}
          = \beta_C\,\sigma_\beta^2
          = e_B\,\sigma_C^2,
          \]</p>
          
          <p>where</p>
          <p>\[
          \beta_C:=\beta^\top h_C,\qquad e_B:=e^\top h_B.
          \]</p>
          
          <ul>
            <li>If \(B\) is fully invested, then \(e_B=1\Rightarrow\sigma_{B,C}=\sigma_C^2\).</li>
            <li>In general \(\beta_C=\sigma_{B,C}/\sigma_B^2\); it need not equal \(1\) unless additional normalization is imposed.</li>
          </ul>
          
          <p><b>En ingles.</b> Defining the beta attribute with respect to \(B\) makes \(B\) itself the minimum-variance portfolio among all portfolios with beta-one exposure. The covariance link \(\sigma_{B,C}=e_B\sigma_C^2=\beta_C\sigma_B^2\) cleanly separates "how much \(B\) is invested" \((e_B)\) from "how much \(C\) loads on the \(\beta\) attribute" \((\beta_C)\).</p>
          
          <p><b>En mas ingles.</b> Characteristic portfolios are "least-wiggle" (min-variance) portfolios achieving <b>unit exposure</b> to the chosen attribute; covariances follow from the orthogonal-projection geometry and exposure identities.</p>
        </div>
      </details>
      <details class="dropdown-block">
        <summary>Portfolio \(q\)</summary>
        <div class="content">
          <p>The <b>expected excess returns</b> \(\mathbf{f}\) have <b>portfolio \(q\)</b> as their characteristic portfolio.</p>
          
          <p><strong>Sharpe Ratio</strong></p>
          <p>For any risky portfolio \(P\) \((\sigma_P>0)\), the Sharpe ratio is</p>
          <p>\[
          \mathrm{SR}_P \;=\; \frac{f_P}{\sigma_P}
          \]</p>
          
          <p><strong>Proposition 2: Portfolio with the Maximum Sharpe Ratio</strong></p>
          <p>Let \(q\) be the <b>characteristic portfolio</b> of the expected excess returns \(\mathbf{f}\):</p>
          <p>\[
          \mathbf{h}_q \;=\; \frac{\mathbf{V}^{-1}\mathbf{f}}{\mathbf{f}^{\!T}\mathbf{V}^{-1}\mathbf{f}}
          \]</p>
          
          <p>Then</p>
          <p>\[
          \mathrm{SR}_q \;=\; \max_P \mathrm{SR}_P \;=\; \big(\mathbf{f}^{\!T}\mathbf{V}^{-1}\mathbf{f}\big)^{1/2}
          \]</p>
          
          <p>\[
          f_q \;=\; 1
          \]</p>
          
          <p>\[
          \sigma_q^2 \;=\; \frac{1}{\mathbf{f}^{\!T}\mathbf{V}^{-1}\mathbf{f}}
          \]</p>
          
          <p><b>3. (property)</b></p>
          <p>\[
          \mathbf{f} \;=\; \frac{\mathbf{V}\mathbf{h}_q}{\sigma_q^2} \;=\; \Big(\frac{\mathbf{V}\mathbf{h}_q}{\sigma_q}\Big)\,\mathrm{SR}_q
          \]</p>
          
          <p><b>4.</b> If \(\rho_{p,q}\) is the correlation between portfolios \(P\) and \(q\), then</p>
          <p>\[
          \mathrm{SR}_P \;=\; \rho_{p,q}\,\mathrm{SR}_q
          \]</p>
          
          <p><b>5.</b> The <b>fraction invested in risky assets</b> for \(q\) is</p>
          <p>\[
          e_q \;=\; \frac{f_C\,\sigma_q^2}{\sigma_C^2}
          \]</p>
        </div>
      </details>
      <details class="dropdown-block">
        <summary>Prop. 2 Proof There it is</summary>
        <div class="content">
          <p><strong>Setup</strong></p>
          <ul>
            <li>Random asset-return vector \(R\in\mathbb{R}^N\), mean excess return \(f:=\mathbb{E}[R]\), covariance \(V\succ0\).</li>
            <li>Portfolio \(h\) has excess mean \(f_P:=h^\top f\) and variance \(\sigma_P^2:=h^\top Vh\).</li>
            <li>Sharpe ratio (for \(\sigma_P>0\)):</li>
          </ul>
          <p>\[
          \mathrm{SR}_P \;=\; \frac{f_P}{\sigma_P}.
          \]</p>
          
          <p>Let \(q\) denote the characteristic portfolio of the attribute \(a=f\):</p>
          <p>\[
          h_q \;=\; \frac{V^{-1}f}{f^\top V^{-1}f}.
          \]</p>
          
          <p>By Prop. 1:</p>
          <p>\[
          f_q \;=\; f^\top h_q \;=\; 1,
          \qquad
          \sigma_q^2 \;=\; h_q^\top Vh_q \;=\; \frac{1}{f^\top V^{-1}f},
          \qquad
          Vh_q \;=\; \sigma_q^2 f.
          \]</p>
          
          <p><strong>Step 1 — Scale invariance of \(\mathrm{SR}\) (why we can normalize \(f_P=1\))</strong></p>
          <p>For any \(\kappa>0\),</p>
          <p>\[
          f_{\kappa h}=\kappa f_P
          \]</p>
          <p>\[
          \sigma_{\kappa h}=\kappa \sigma_P
          \]</p>
          <p>\[
          \mathrm{SR}_{\kappa h}=\frac{f_{\kappa h}}{\sigma_{\kappa h}}=\frac{\kappa f_P}{\kappa \sigma_P}=\mathrm{SR}_P.
          \]</p>
          
          <p>If \(f_P<0\), replace \(h\) by \(-h\) to flip the sign (Sharpe changes sign). Thus we may restrict attention to \(f_P>0\).</p>
          
          <p><b>Normalization (the key step).</b> For any \(h\) with \(f_P>0\), choose \(\kappa:=1/f_P\) and set \(\tilde h:=\kappa h\). Then</p>
          <p>\[
          f_{\tilde P}=f^\top \tilde h=\kappa f_P=1
          \]</p>
          <p>\[
          \sigma_{\tilde P}=\kappa \sigma_P=\frac{\sigma_P}{f_P}
          \]</p>
          <p>\[
          \mathrm{SR}_{\tilde P}=\frac{f_{\tilde P}}{\sigma_{\tilde P}}=\frac{1}{\sigma_{\tilde P}}=\frac{f_P}{\sigma_P}=\mathrm{SR}_P.
          \]</p>
          
          <p>Therefore</p>
          <p>\[
          \max_P \mathrm{SR}_P
          =\max_{h:\,f^\top h=1}\frac{1}{\sigma_P}
          =\frac{1}{\min_{h:\,f^\top h=1}\sigma_P}.
          \]</p>
          
          <p><strong>Step 2 — Solve the inner minimization via the characteristic portfolio of \(f\)</strong></p>
          <p>The unit-exposure, minimum-variance problem with attribute \(f\) has the unique solution (see Prop 1 above):</p>
          <p>\[
          h_q=\frac{V^{-1}f}{f^\top V^{-1}f}.
          \]</p>
          
          <p>From Proposition 1:</p>
          <p>\[
          f_q=f^\top h_q=1 
          \]</p>
          <p>\[
          \sigma_q^2=h_q^\top Vh_q=\frac{1}{f^\top V^{-1}f}.
          \]</p>
          
          <p>Hence the maximal Sharpe is:</p>
          <p>\[
          \mathrm{SR}_q=\frac{f_q}{\sigma_q}=\frac{1}{\sigma_q}=\big(f^\top V^{-1}f\big)^{1/2}.
          \]</p>
          
          <p><strong>Step 3 — Property linking \(f\), \(h_q\), and \(\sigma_q\)</strong></p>
          <p>Apply result from Prop. 1 Item 3 \(Vh_a=\sigma_a^2 a\) to \(a=f\):</p>
          <p>\[
          f=\frac{Vh_q}{\sigma_q^2}
          \]</p>
          <p>\[
          f=\left(\frac{Vh_q}{\sigma_q}\right)\mathrm{SR}_q.
          \]</p>
          
          <p><strong>Step 4 — Any portfolio's Sharpe via correlation with \(q\)</strong></p>
          <p>Premultiply the first equality in prev. step by \(h_P^\top\) and divide by \(\sigma_P\):</p>
          <p>\[
          \mathrm{SR}_P
          =\frac{f_P}{\sigma_P}
          =\frac{h_P^\top Vh_q}{\sigma_P\,\sigma_q^2}
          =\left(\frac{\sigma_{p,q}}{\sigma_P\,\sigma_q}\right)\left(\frac{1}{\sigma_q}\right)
          =\rho_{p,q}\,\mathrm{SR}_q,
          \]</p>
          
          <p>so</p>
          <p>\[
          \mathrm{SR}_P=\rho_{p,q}\,\mathrm{SR}_q.
          \]</p>
          
          <p><strong>Step 5 — Fraction invested in risky assets for \(q\)</strong></p>
          <p>Let \(C\) be the characteristic portfolio of \(e\) (the all-ones attribute).<br>
          By Prop. 1 Item 4 applied to \(f\) and \(e\):</p>
          <p>\[
          \sigma_{q,C}=f_C\,\sigma_q^2=e_q\,\sigma_C^2
          \]</p>
          <p>\[
          e_q=\frac{f_C\,\sigma_q^2}{\sigma_C^2}.
          \]</p>
          
          <b>En ingles:</b><br>
          <ul>
            <li> \(q\) is the <b>tangency (max-Sharpe)</b> portfolio. Its weights (\(h_q\)) are the min-variance portfolio with <b>unit exposure</b> to \(\mathbf{f}\).</li>
            <li> Because \(f_q=1\) and \(\sigma_q=1/\mathrm{SR}_q\), item (3) shows a key identity: <b>expected returns</b> are proportional to <b>betas with respect to \(q\)</b>, scaled by \(\mathrm{SR}_q\).</li>
            <li> Any portfolio's Sharpe is its <b>correlation</b> with \(q\) times \(\mathrm{SR}_q\). If you're uncorrelated with \(q\), your Sharpe must be zero.</li>
            <li> \(e_q\) tells you how levered/under-invested the tangency portfolio is relative to "fully invested" \(C\).</li>
          </ul>
        </div>
      </details>
      <details class="dropdown-block">
        <summary>Seeking \(\alpha\)</summary>
        <div class="content">
          <p><strong>Portfolio \(A\)</strong></p>
          <p>Define <b>alpha</b> as</p>
          <p>\[
          \boldsymbol{\alpha} \;=\; \mathbf{f} \;-\; \boldsymbol{\beta}\,f_B,
          \]</p>
          
          <p>and let \(\mathbf{h}_\alpha\) be the <b>characteristic portfolio for alpha</b> (the min-risk portfolio with alpha \(=100\%\)). By the mixture (linear combination) corollary one can express \(\mathbf{h}_f\) in terms of \(\mathbf{h}_\beta\) and \(\mathbf{h}_q\). From Prop. 1 Item 4,</p>
          <p>\[
          \sigma_{\beta,\alpha} \;=\; \alpha_B\,\sigma_\beta^2 \;=\; \beta_\alpha\,\sigma_\alpha^2.
          \]</p>
          
          <p>But \(\alpha_B=0\) <b>by construction</b>, hence portfolios \(A\) and \(B\) are <b>uncorrelated</b>, and \(\beta_\alpha=0\).</p>
          
          <p>The text then notes it is often convenient to assume there exists a <b>fully invested portfolio</b> that explains expected excess returns (true, e.g., if \(f_C>0\)); this assumption will be used going forward.</p>
        </div>
      </details>
      <details class="dropdown-block">
        <summary>Desperately seeking alpha</summary>
        <div class="content">
          <p><strong>Definitions & setup</strong></p>
          <ul>
            <li>Benchmark \(B\) has weights \(h_B\) and beta attribute</li>
          </ul>
          <p>\[
          \beta=\frac{Vh_B}{\sigma_B^2}.
          \]</p>
          
          <ul>
            <li>Let \(f\) be expected excess returns.</li>
            <li>Define <b>alpha</b> (asset-level) as</li>
          </ul>
          <p>\[
          \alpha = f - \beta\, f_B,
          \]</p>
          
          <p>where \(f_B := f^\top h_B\).</p>
          
          <ul>
            <li>Let \(h_\alpha\) be the <b>characteristic portfolio</b> for \(\alpha\) (min-variance portfolio with unit exposure to \(\alpha\)).</li>
          </ul>
          
          <p><strong>Step 1 — Express \(h_\alpha\) as a mixture of \(h_q\) and \(h_\beta\) via Eq. (2A.5)</strong></p>
          <p>From the definition \(\alpha = 1\cdot f + (-f_B)\cdot \beta\), apply the linear-combination identity (See Mixture formula) with attributes \(d=f\) and \(f=\beta\). Recall:</p>
          
          <ul>
            <li>The characteristic portfolio of \(f\) is \(q\): \(h_q=\dfrac{V^{-1}f}{f^\top V^{-1}f}\).</li>
            <li>The characteristic portfolio of \(\beta\) is \(h_\beta=h_B\).</li>
          </ul>
          
          <p>Thus,</p>
          <p>\[
          h_\alpha
          = \left(\frac{1\cdot \sigma_\alpha^2}{\sigma_q^2}\right) h_q
          + \left(\frac{-f_B\cdot \sigma_\alpha^2}{\sigma_\beta^2}\right) h_\beta
          = \frac{\sigma_\alpha^2}{\sigma_q^2}\,h_q
          -\frac{f_B\,\sigma_\alpha^2}{\sigma_\beta^2}\,h_\beta.
          \]</p>
          
          <p>This is exactly the "matching weighted combination" statement specialized to \(\alpha=f - \beta f_B\).</p>
          
          <p><strong>Step 2 — Compute \(\alpha_B\) and show it is zero</strong></p>
          <p>By definition, the <b>exposure</b> of portfolio \(B\) to attribute \(\alpha\) is</p>
          <p>\[
          \alpha_B := \alpha^\top h_B
          = (f - \beta f_B)^\top h_B
          = f_B - f_B\,\beta^\top h_B.
          \]</p>
          
          <p>But</p>
          <p>\[
          \beta^\top h_B
          = \left(\frac{Vh_B}{\sigma_B^2}\right)^\top h_B
          = \frac{h_B^\top V h_B}{\sigma_B^2}
          = \frac{\sigma_B^2}{\sigma_B^2}
          = 1.
          \]</p>
          
          <p>Hence</p>
          <p>\[
          \alpha_B = f_B - f_B\cdot 1 = 0.
          \]</p>
          
          <p><strong>Step 3 — Use Prop. 1 Item 4 to connect covariances and exposures</strong></p>
          <p>Recall (or just look at the Prop. 1 stuff again), for any two attributes \(a,d\) with characteristic portfolios \(h_a,h_d\),</p>
          <p>\[
          \sigma_{a,d} = a_{h_d}\,\sigma_a^2 = d_{h_a}\,\sigma_d^2,
          \]</p>
          
          <p>where \(a_{h_d}:=a^\top h_d\) and \(d_{h_a}:=d^\top h_a\).</p>
          
          <p>Apply this with \(a=\beta\) and \(d=\alpha\). Then</p>
          <ul>
            <li>\(a_{h_d}=\beta_{h_\alpha}=\beta_\alpha\),</li>
            <li>\(d_{h_a}=\alpha_{h_\beta}=\alpha_B\),</li>
            <li>\(h_\beta=h_B\).</li>
          </ul>
          
          <p>Therefore,</p>
          <p>\[
          \sigma_{\beta,\alpha} = \beta_\alpha\,\sigma_\beta^2 = \alpha_B\,\sigma_\alpha^2.
          \]</p>
          
          <p>From Step 2, \(\alpha_B=0\). Since \(\sigma_\alpha^2>0\) (strictly, by \(V\succ0\) and \(\alpha\neq 0\) unless the model is degenerate), we get</p>
          <p>\[
          \sigma_{\beta,\alpha} = 0,
          \qquad
          \beta_\alpha\,\sigma_\beta^2 = 0
          \;\Rightarrow\;
          \beta_\alpha = 0
          \quad (\text{because } \sigma_\beta^2>0).
          \]</p>
          
          <p><b>Conclusions.</b></p>
          <ul>
            <li>Portfolios \(A\) and \(B\) are <b>uncorrelated</b>: \(\sigma_{\beta,\alpha}=0\).</li>
            <li>The <b>beta exposure of \(A\)</b> is zero: \(\beta_\alpha=0\) (i.e., \(h_\alpha\) is \(\beta\)-neutral).</li>
          </ul>
          
          <p><strong>Step 4 — Why the "fully invested explainer" assumption is convenient</strong></p>
          <p><b>What "fully-invested explainer" means:</b></p>
          
          <p>"\(Q\) explains \(f\)" ⇔ the expected excess-return vector \(f\) is proportional to the beta vector <b>with respect to \(Q\)</b>:</p>
          <p>\[
          f \;=\; f_C\,\beta^{(\text{w.r.t.\ }Q)}
          \quad\text{where}\quad
          \beta^{(\text{w.r.t.\ }Q)}=\frac{Vh_Q}{\sigma_Q^2}.
          \]</p>
          
          <p>Equivalently, for every asset \(i\) and every portfolio \(P\),</p>
          <p>\[
          f_i=\beta_i^{(Q)}\,f_C,
          \qquad
          f_P=\beta_P^{(Q)}\,f_C.
          \]</p>
          
          <p>So \(f_C\) is the <b>market price of risk</b> and \(\beta^{(Q)}\) are the <b>prices per unit of risk exposure</b>.</p>
          
          <p>Recall the fraction of risky assets invested in \(q\),</p>
          <p>\[
          e_q = \frac{f_C\,\sigma_q^2}{\sigma_C^2}.
          \]</p>
          
          <p>If \(f_C>0\), then \(e_q>0\). You can scale \(q\) to be fully invested without changing its Sharpe ratio and still have it <b>explain \(f\)</b> (Recall, \(f=(Vh_q/\sigma_q^2)\)). This gives a convenient <b>fully invested</b> factor that prices expected excess returns and keeps the decomposition \(\alpha = f - \beta f_B\) clean in practice.</p>
        </div>
      </details>
    </div>
  </details>
</div>
{% endcapture %}
{% include technical-appendix.html content=appendix %}
