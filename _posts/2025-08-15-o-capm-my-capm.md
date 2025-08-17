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

    </div>
  </details>
</div>


