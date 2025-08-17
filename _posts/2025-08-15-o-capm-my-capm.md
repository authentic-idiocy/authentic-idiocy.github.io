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
            <li>\\(\\beta_p\\) measures how much <strong>market risk</strong> \\(P\\) carries per unit of market variance.</li>
            <li>The arithmetic decomposition is a <strong>projection</strong>: \\(r_p\\) is orthogonally projected onto \\(r_M\\). The fitted part \\(\\beta_p r_M\\) is the market-driven return; the miss \\(\\theta_p\\) is everything <em>not</em> explained by the market.</li>
            <li>Because \\(\\theta_p \\perp r_M\\), total variance splits additively. This is the statistical backbone behind phrases like “systematic vs. idiosyncratic risk.”</li>
            <li>None of this assumes CAPM or equilibrium—only linear projection and definitions. CAPM later stipulates how <strong>expected</strong> returns relate to \\(\\beta\\) and says residuals shouldn’t earn systematic premia.</li>
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

      <p><strong>Idea.</strong> Ex-ante (CAPM), expected total return lies on the Security Market Line
      \( \mathbb{E}[R_P]= i_F + \beta_P\,\mu_M \) (intercept \(i_F\), slope \( \mu_M \)).
      Ex-post, after realization, plot \( R_P = i_F + \beta_P\, r_M \) (intercept \(i_F\), slope = realized market excess \(r_M\)).
      Vertical gaps from this ex-post line are residuals \( \varepsilon_P = R_P - (i_F+\beta_P r_M)\).
      Value-weighted residuals across the universe sum to ~0.</p>

      <div id="sml-expost-card" style="max-width: 920px;"></div>
      <div id="residual-sum" style="font-size: 0.9em; opacity: 0.8; margin-top: 6px;"></div>

      <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
      <script>
        // ===== Parameters (edit these to taste) =====
        const iF = 0.02;          // risk-free rate (intercept)
        const muM = 0.06;         // expected market excess return (ex-ante slope)
        const rM = 0.03;          // realized market excess return (ex-post slope)

        // Sample assets: choose betas, weights, and residuals ε so that ∑ w_i ε_i ≈ 0
        // (here exactly 0 with equal weights)
        const assets = [
          {name: "A", beta: 0.70, w: 0.25, eps:  +0.020},
          {name: "B", beta: 1.00, w: 0.25, eps:  -0.010},
          {name: "C", beta: 1.30, w: 0.25, eps:  +0.005},
          {name: "D", beta: 1.00, w: 0.25, eps:  -0.015}
        ];

        // ===== Build lines =====
        const betaGrid = Array.from({length: 201}, (_, i) => -0.2 + i*(2.0/200)); // [-0.2, 1.8]
        const yExAnte  = betaGrid.map(b => iF + muM*b);
        const yExPost  = betaGrid.map(b => iF + rM*b);

        const traceExAnte = {
          x: betaGrid, y: yExAnte, mode: "lines",
          name: "Ex-ante SML: i_F + β·μ_M",
          hovertemplate: "β=%{x:.2f}<br>E[R]=i_F + β·μ_M = %{y:.2%}<extra></extra>"
        };

        const traceExPost = {
          x: betaGrid, y: yExPost, mode: "lines",
          name: "Ex-post line: i_F + β·r_M",
          line: {dash: "dash"},
          hovertemplate: "β=%{x:.2f}<br>R = i_F + β·r_M = %{y:.2%}<extra></extra>"
        };

        // Key points: risk-free and market (expected vs realized)
        const riskFree = {
          x: [0], y: [iF], mode: "markers+text", name: "Risk-free i_F",
          text: ["i_F"], textposition: "bottom right", marker: {size: 9},
          hovertemplate: "β=0<br>i_F=%{y:.2%}<extra></extra>"
        };

        const marketExpected = {
          x: [1], y: [iF + muM], mode: "markers+text", name: "Market (expected)",
          text: ["M (expected)"], textposition: "top left", marker: {size: 9},
          hovertemplate: "β=1<br>E[R_M]=i_F+μ_M=%{y:.2%}<extra></extra>"
        };

        const marketRealized = {
          x: [1], y: [iF + rM], mode: "markers+text", name: "Market (realized)",
          text: ["M (realized)"], textposition: "bottom left", marker: {size: 9},
          hovertemplate: "β=1<br>R_M=i_F+r_M=%{y:.2%}<extra></extra>"
        };

        // ===== Sample assets with vertical residual "sticks" =====
        const assetMarkers = {
          x: [], y: [], mode: "markers+text", name: "Assets (realized)",
          text: [], textposition: "top center", marker: {size: 9},
          hovertemplate: "β=%{x:.2f}<br>R=%{y:.2%}<extra></extra>"
        };

        const residualLines = []; // one trace per asset (vertical line)
        let wResidualSum = 0.0;

        assets.forEach(a => {
          const yPred = iF + rM * a.beta;      // ex-post line value at β_i
          const yReal = yPred + a.eps;          // realized total return
          assetMarkers.x.push(a.beta);
          assetMarkers.y.push(yReal);
          assetMarkers.text.push(a.name);

          // vertical segment from predicted to realized
          residualLines.push({
            x: [a.beta, a.beta],
            y: [yPred, yReal],
            mode: "lines",
            name: `ε_${a.name}`,
            hovertemplate: `Asset ${a.name}<br>ε = ${a.eps.toLocaleString(undefined,{style:"percent", minimumFractionDigits:2})}<extra></extra>`
          });

          wResidualSum += a.w * a.eps;
        });

        // ===== Layout =====
        const layout = {
          title: "Ex-ante SML vs. Ex-post Line (Notation: i_F, μ_M, β, r_M)",
          xaxis: {title: "β (beta)"},
          yaxis: {title: "Return (total)", tickformat: ".0%"},
          template: "plotly_white",
          legend: {orientation: "h", y: 1.1},
          margin: {l: 40, r: 10, t: 60, b: 40},
          width: 900, height: 520,
          annotations: [
            {x: 1.6, y: iF + muM*1.6, text: "slope = μ_M", showarrow: false, yshift: 10},
            {x: 1.6, y: iF + rM*1.6, text: "slope = r_M (realized)", showarrow: false, yshift: -10}
          ]
        };

        Plotly.newPlot(
          "sml-expost-card",
          [traceExAnte, traceExPost, riskFree, marketExpected, marketRealized, assetMarkers, ...residualLines],
          layout,
          {displayModeBar: true, responsive: true}
        );

        // Display the value-weighted residual sum
        const pct = (wResidualSum*100).toFixed(2);
        document.getElementById("residual-sum").innerHTML =
          `Value-weighted residuals: <strong>${pct}%</strong> (constructed to be ~0).`;
      </script>

      <p style="font-size:0.9em; opacity:0.8; margin-top:8px;">
        Hover the lines/points: solid = ex-ante SML \(i_F+\beta\,\mu_M\); dashed = ex-post line \(i_F+\beta\,r_M\).
        Vertical segments show residuals \( \varepsilon \). We chose betas/weights/residuals so that
        \( \sum w_i\varepsilon_i \approx 0 \), illustrating the “value-weighted residuals sum to zero” fact.
      </p>
    </div>
  </details>
</div>


