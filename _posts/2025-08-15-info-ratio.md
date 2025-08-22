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
<div class="flashcard">
  <details>
    <summary>The Residual Frontier: The Manager's Opportunity Set</summary>
    <div class="back">
      <p><strong>Idea.</strong><br>
      Plot expected residual return \(\alpha_p\) against residual risk \(\omega_p\). The <b>ex-ante information ratio</b> determines the <i>slope</i> of the best attainable trade-off. The manager's <b>residual frontier</b> is the straight line through the origin with that slope; feasible (sub-optimal) portfolios lie on or <b>below</b> this line.</p>
      
      <p><strong>Geometry.</strong><br>
      Benchmark \(B\) and cash sit at the origin since both have zero residual return and zero residual risk. Portfolios constructed from the manager's alphas that <i>fully exploit</i> the information lie <b>on</b> the line; all others lie <b>under</b> it.</p>
      <div id="residual-frontier-fig-5-combined" style="width:980px;height:560px;"></div>
      <div id="residual-frontier-fig-5-combined-info" style="font-size:0.9em; opacity:0.95; margin-top:8px;"></div>
      
      <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
      <script>
      function renderResidualFrontierCombined() {
        // ===== Axes grid (ω in %, α in %) =====
        const toPct = x => x; // keep in [0, 0.12] but show as % via tickformat
      
        // ===== Residual frontiers (Fig. 5.2) =====
        const IRs = [
          { ir: 1.00, dash: "solid",  width: 3, name: "IR = 1.00" },
          { ir: 0.75, dash: "dot",    width: 3, name: "IR = 0.75" },
          { ir: 0.50, dash: "dash",   width: 3, name: "IR = 0.50" },
        ];
      
        const xMin = 0.0, xMax = 0.12, Nx = 121;
        const omega = Array.from({length: Nx}, (_, i) => xMin + i*(xMax - xMin)/(Nx - 1));
      
        const frontierTraces = IRs.map(({ir, dash, width, name}) => ({
          x: omega.map(toPct),
          y: omega.map(w => ir*w),
          mode: "lines",
          line: { dash, width },
          name,
          hovertemplate: "ω=%{x:.1%}<br>α=%{y:.1%}<extra>"+name+"</extra>"
        }));
      
        // ===== Points on IR=1 frontier (Fig. 5.1 P1–P6 + Q) =====
        const IR1 = 1.0;
        const Pks = [0.01, 0.02, 0.03, 0.04, 0.05, 0.06]; // 1% … 6% residual risk
        const Ptext = ["P1","P2","P3","Q","P5","P6"];     // label Q near the middle as in fig
      
        const Ptrace = {
          x: Pks,
          y: Pks.map(w => IR1*w),
          mode: "markers+text",
          type: "scatter",
          name: "Fig. 5.1 points",
          marker: { size: 9, symbol: "circle" },
          text: Ptext,
          textposition: ["bottom right","top left","bottom left","top right","bottom left","top left"],
          hovertemplate: "%{text}<br>ω=%{x:.1%}<br>α=%{y:.1%}<extra></extra>"
        };
      
        // Explicit Q (so it’s easy to style)
        const Qw = 0.04, Qa = IR1*Qw;
        const Qtrace = {
          x: [Qw], y: [Qa],
          mode: "markers+text",
          name: "Q",
          marker: { size: 11, symbol: "diamond-open" },
          text: ["Q"],
          textposition: "top center",
          hovertemplate: "Q<br>ω=%{x:.1%}<br>α=%{y:.1%}<extra></extra>"
        };
      
        // Benchmark/cash at the origin: B
        const Btrace = {
          x: [0], y: [0],
          mode: "markers+text",
          name: "B (benchmark & cash)",
          marker: { size: 10, symbol: "square" },
          text: ["B"],
          textposition: "bottom right",
          hovertemplate: "B<br>ω=0.0%<br>α=0.0%<extra></extra>"
        };
      
        // ===== Annotations to mirror captions =====
        const annotations = [
          { x: 0.095, y: 0.095, text: "IR = 1", showarrow: false, font: {size: 12}},
          { x: 0.095, y: 0.071, text: "IR = 0.75", showarrow: false, font: {size: 12}},
          { x: 0.095, y: 0.048, text: "IR = 0.50", showarrow: false, font: {size: 12}}
        ];
      
        const layout = {
          title: "Residual Frontier & Opportunities (Combined: Figures 5.1 & 5.2)",
          xaxis: { title: "ω (residual risk)", range: [0, 0.12], tickformat: ".0%", zeroline: false },
          yaxis: { title: "α (expected residual return)", range: [0, 0.12], tickformat: ".0%", rangemode: "tozero" },
          template: "plotly_white",
          legend: { orientation: "h", y: 1.12 },
          margin: { l: 70, r: 20, t: 70, b: 55 },
          annotations
        };
      
        const traces = [...frontierTraces, Ptrace, Qtrace, Btrace];
        Plotly.newPlot("residual-frontier-fig-5-combined", traces, layout,
                       {displayModeBar: true, responsive: true});
      
        // ===== Info + intuition (below the figure) =====
        document.getElementById("residual-frontier-fig-5-combined-info").innerHTML = `
        <p>
          <strong>What you're seeing (both figures combined):</strong>
          The straight rays from the origin are residual frontiers \\(\\alpha_p = IR\\,\\omega_p\\) for three information ratios
          (solid: 1.00; dotted: 0.75; dashed: 0.50). The black markers (P1–P6) and Q sit on the \\(IR=1\\) frontier,
          and B is the origin (benchmark/cash), where both residual return and residual risk are zero.
        </p>
        <ul>
          <li><em>Opportunity = slope.</em> A manager’s ex-ante information ratio fixes the frontier’s slope. Higher IR rotates the line upward, expanding the set of attainable \\((\\omega,\\alpha)\\) pairs.</li>
          <li><em>Feasible set.</em> Portfolios lie on or below the frontier implied by the manager’s IR; moving along a given frontier scales both \\(\\omega_p\\) and \\(\\alpha_p\\) proportionally.</li>
          <li><em>Comparing managers (Fig. 5.2 idea).</em> Points available on \\(IR=1\\) are not available to an \\(IR=0.5\\) manager; the latter’s best achievable \\(\\alpha\\) at any \\(\\omega\\) is lower.</li>
          <li><em>Normalization.</em> B (benchmark) and cash anchor the origin because their residual return is zero; hence \\(\\alpha_B=0\\) and \\(\\omega_B=0\\).</li>
        </ul>
        <p style="opacity:0.85;">
          <small>Note: Numerical placements are illustrative to recreate the diagrams’ geometry; the theory is the linear relation
          \\(\\alpha_p = IR\\,\\omega_p\\) and the comparison of opportunity sets across IR levels.</small>
        </p>`;
      }
      // Render now
      renderResidualFrontierCombined();
      </script>

      <details class="dropdown-block">
        <summary>Link to the optimization definition</summary>
        <div class="content">
          <p>The manager's information ratio is defined as the maximum attainable ratio over feasible portfolios:</p>
          <p>\[
          IR \;=\; \Max\{\alpha_p/\omega_p \mid P\}
          \]</p>
          <p>Any portfolio \(Q\) that attains this maximum lies on the frontier and satisfies \(IR=IR_Q\).</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Comparing managers</summary>
        <div class="content">
          <p>Different managers have different frontiers (different slopes). A higher \(IR\) rotates the frontier <b>upward</b>, enlarging the opportunity set; points available to a higher-\(IR\) manager are not available to a lower-\(IR\) manager. This does <b>not</b> mean a lower-\(IR\) manager cannot mechanically hold those same stocks; rather, their information will not <i>lead</i> them to portfolios achieving those \((\omega,\alpha)\) pairs.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>"Budget constraint" form</summary>
        <div class="content">
          <p>Along the frontier the trade-off is linear:</p>
          <p>\[
          \alpha_p \;=\; IR \cdot \omega_p 
          \]</p>
          <p>At best, increases in expected residual return require <b>proportional</b> increases in residual risk; scaling active positions moves you <i>along</i> the line (both \(\alpha_p\) and \(\omega_p\) scale together, leaving \(IR\) unchanged).</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>En ingles (and a lil bit o' math.)</summary>
        <div class="content">
          <ul>
            <li>The residual frontier is the active-risk analogue of the mean-variance capital market line: it is the set \(\{(\omega_p,\alpha_p): \alpha_p \le IR \cdot \omega_p\}\) with equality for optimized portfolios.</li>
            <li>\(IR\) is the <i>sufficient statistic</i> for opportunity quality; it fully characterizes the frontier's slope and, hence, the manager's achievable conversion of information into residual return per unit of active risk.</li>
            <li>Benchmarks/cash anchor the origin; feasible portfolios live on/below the ray; improving information (better forecasts or better use of them) <b>raises the slope</b>.</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>
<div class="flashcard">
  <details>
    <summary>The Active Management Objective</summary>
    <div class="back">
      <details class="dropdown-block">
        <summary>Objective</summary>
        <div class="content">
          <p>Maximize <b>value added</b> from residual (active) return. Define</p>
          <p>\[
          \text{VA}[P] \;=\; \alpha_p \;-\; \lambda_r \cdot \omega_p^{2}
          \]</p>
          
          <ul>
            <li>\(\alpha_p\): expected <b>residual return</b> of portfolio \(P\).</li>
            <li>\(\omega_p\): <b>residual risk</b> (active risk; st. dev.).</li>
            <li>\(\lambda_r>0\): <b>aversion to residual risk</b>; converts residual <i>variance</i> into a <b>loss in alpha</b>.</li>
          </ul>
          
          <p><b>Wat It Mean.</b><br>
          VA credits forecasted skill (\(\alpha_p\)) and debits risk (\(\lambda_r \omega_p^2\)). The quadratic penalty mirrors mean-variance preferences specialized to residual (benchmark-neutral) returns: utility is linear in mean, quadratic in variance.</p>
          
          <p><b>NB:</b><br>
          Benchmark timing is ignored, so <b>active return = residual return</b> and <b>active risk = residual risk</b>.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Loss in alpha (risk penalty)</summary>
        <div class="content">
          <p>For any fixed \(\lambda_r\), the <b>loss in alpha</b> due to bearing residual risk \(\omega_p\) is</p>
          <p>\[
          \text{Loss}(\omega_p) \;=\; \lambda_r \cdot \omega_p^{2}.
          \]</p>
          
          <p>Higher \(\lambda_r\) ⇒ steeper penalty; the loss rises with the <b>square</b> of risk.</p>
          <!-- Figure 5.3 — Loss in alpha (separate block) -->
          <div id="fig-5-3" style="width:960px;height:520px;"></div>
          <div id="fig-5-3-info" style="font-size:0.9em; opacity:0.95; margin:8px 0 24px;"></div>
          
          <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
          <script>
          (function renderFig53() {
            // Percent tick helpers
            const tickVals = (max=12, step=2) => Array.from({length: Math.floor(max/step)+1}, (_,i)=> i*step);
            const tickText = vals => vals.map(v => v.toFixed(0) + "%");
          
            // ω from 0%..12% sampled finely (use "percent points" axis)
            const wMaxPP = 12, Nw = 121;
            const wPP = Array.from({length: Nw}, (_,i)=> i*(wMaxPP)/(Nw-1)); // 0..12
          
            // Loss in alpha curves: Loss(ω) = λ_r * ω^2  (three λ_r levels)
            const lambdas = [
              {lam: 0.05, dash: "dot",    name: "λ = 0.05"},
              {lam: 0.10, dash: "dash",   name: "λ = 0.10"},
              {lam: 0.15, dash: "solid",  name: "λ = 0.15"}
            ];
            const lossTraces = lambdas.map(({lam, dash, name}) => ({
              x: wPP,
              y: wPP.map(w => lam*w*w),
              mode: "lines",
              line: {width: 3, dash},
              name,
              hovertemplate: "ω=%{x:.1f}%<br>Loss in α=%{y:.2f}%<extra>"+name+"</extra>"
            }));
          
            const xt = tickVals(12,2), yt = tickVals(16,2);
            const layout53 = {
              title: "Figure 5.3 — Loss in α:  λ<sub>r</sub> · ω²",
              xaxis: {title: "ω", range: [0,12], tickvals: xt, ticktext: tickText(xt), zeroline: false},
              yaxis: {title: "Loss in α", range: [0,16], tickvals: yt, ticktext: tickText(yt), rangemode: "tozero"},
              template: "plotly_white",
              legend: {orientation: "h", y: 1.12},
              margin: {l: 70, r: 20, t: 70, b: 55}
            };
          
            Plotly.newPlot("fig-5-3", lossTraces, layout53, {displayModeBar:true, responsive:true});
          
            document.getElementById("fig-5-3-info").innerHTML = `
              <p><strong>Loss in α.</strong> With residual-risk aversion \\(\\lambda_r\\),
              the penalty for bearing residual risk \\(\\omega\\) is quadratic: \\(\\text{Loss}(\\omega)=\\lambda_r\\,\\omega^2\\).
              Higher \\(\\lambda_r\\) means greater aversion, so the curve bends up more sharply; for a fixed \\(\\lambda_r\\),
              loss grows with the square of risk.</p>
            `;
          })();
          </script>

        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Lines of equal value added (indifference curves)</summary>
        <div class="content">
          <p>Holding VA constant at some level \(c\), rearrange the objective:</p>
          <p>\[
          \alpha_p \;=\; c \;+\; \lambda_r \cdot \omega_p^{2}.
          \]</p>
          
          <p>These are <b>upward-opening parabolas</b> in the \((\omega_p,\alpha_p)\) plane. For a given \(\lambda_r\) they are <b>parallel</b> (same curvature) and represent all portfolios that deliver the same certainty-equivalent value added \(c\).</p>
          <!-- Figure 5.4 — Constant value-added lines (separate block) -->
          <div id="fig-5-4" style="width:960px;height:520px;"></div>
          <div id="fig-5-4-info" style="font-size:0.9em; opacity:0.95; margin-top:8px;"></div>
          
          <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
          <script>
          (function renderFig54() {
            const tickVals = (max=12, step=2) => Array.from({length: Math.floor(max/step)+1}, (_,i)=> i*step);
            const tickText = vals => vals.map(v => v.toFixed(0) + "%");
          
            const wMaxPP = 12, Nw = 121;
            const wPP = Array.from({length: Nw}, (_,i)=> i*(wMaxPP)/(Nw-1)); // 0..12
          
            // α(ω) for constant value added: α = VA + λ_r * ω^2  (λ_r = 0.10 as in figure)
            const lambdaVA = 0.10;
            const VAlevels = [
              {va: 2.500, dash: "dash",    name: "VA = 2.500%"},
              {va: 1.400, dash: "dashdot", name: "VA = 1.400%"},
              {va: 0.625, dash: "solid",   name: "VA = 0.625%"}
            ];
            const aTraces = VAlevels.map(({va, dash, name}) => ({
              x: wPP,
              y: wPP.map(w => va + lambdaVA*w*w),
              mode: "lines",
              line: {width: 3, dash},
              name,
              hovertemplate: "ω=%{x:.1f}%<br>α=%{y:.2f}%<extra>"+name+"</extra>"
            }));
          
            const xt = tickVals(12,2), yt = tickVals(14,2);
            const layout54 = {
              title: "Figure 5.4 — Constant Value-Added Lines:  α = VA + λ<sub>r</sub> · ω²  (λ<sub>r</sub>=0.10)",
              xaxis: {title: "ω", range: [0,12], tickvals: xt, ticktext: tickText(xt), zeroline: false},
              yaxis: {title: "α", range: [0,14], tickvals: yt, ticktext: tickText(yt), rangemode: "tozero"},
              template: "plotly_white",
              legend: {orientation: "h", y: 1.12},
              margin: {l: 70, r: 20, t: 70, b: 55}
            };
          
            Plotly.newPlot("fig-5-4", aTraces, layout54, {displayModeBar:true, responsive:true});
          
            document.getElementById("fig-5-4-info").innerHTML = `
              <p><strong>Constant value-added curves.</strong>
                For fixed \\(\\lambda_r\\), an indifference set is \\(\\alpha = \\text{VA} + \\lambda_r\\,\\omega^2\\).
                These parabolas are parallel; higher \\(\\text{VA}\\) shifts the curve upward.
                Each point on a given curve yields the same risk-adjusted residual return (same VA): increasing \\(\\omega\\)
                requires a compensating rise in \\(\\alpha\\) equal to \\(\\lambda_r\\,\\omega^2\\).</p>
            `;
          })();
          </script>

        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Certainty-equivalent interpretation</summary>
        <div class="content">
          <p>VA is the <span class="define">certainty-equivalent residual return
            <div class="tooltip">
              <div style="max-width: 500px">
                <h4>Gettin' assy (economicsy): What is a certainty equivalent (CE)?</h4>
                <p><b>Definition (general).</b> For any risky payoff \(X\) and utility \(U(\cdot)\), the <b>certainty equivalent</b> \(c\) is the sure amount that makes you indifferent to \(X\):</p>
                <p>\[
                U(c)=\mathbb{E}[U(X)].
                \]</p>
                
                <p><b>Here (residual, mean-variance form).</b> Utility for an active portfolio \(P\) is taken to be</p>
                <p>\[
                U(P)=\alpha_p-\lambda_r\,\omega_p^2,
                \]</p>
                <p>i.e., linear in expected residual return \(\alpha_p\) and quadratic penalty in residual variance \(\omega_p^2\) with aversion \(\lambda_r>0\).</p>
                
                <p>A <b>residual risk-free</b> payoff of amount \(c\) has \(\omega=0\), so its utility is \(U(c)=c\). Indifference to the risky active \(P\) means</p>
                <p>\[
                c=\alpha_p-\lambda_r\,\omega_p^2.
                \]</p>
                
                <p>That \(c\) is the <b>certainty-equivalent residual return</b>:</p>
                <p>\[
                \boxed{\text{CE}=\alpha_p-\lambda_r\,\omega_p^2\;}
                \]</p>
                
                <h4>En ingles</h4>
                <p>CE is the <b>risk-adjusted alpha</b>: the guaranteed residual return you'd accept instead of taking the risky active position \((\alpha_p,\omega_p)\) given aversion \(\lambda_r\).<br>
                Equivalently, the <b>residual risk premium</b> you're implicitly paying is</p>
                <p>\[
                \alpha_p-\text{CE}=\lambda_r\,\omega_p^2.
                \]</p>
              </div>
            </div>
          </span>:</p>
          <p>\[
          \text{CE} \;=\; \alpha_p \;-\; \lambda_r \cdot \omega_p^{2}.
          \]</p>
          
          <p>An investor with residual-risk aversion \(\lambda_r\) is indifferent between a risky active portfolio \((\alpha_p,\omega_p)\) and receiving the sure residual return <b>CE</b> on a residual risk-free investment.</p>
        </div>
      </details>
      
      <details class="dropdown-block">
        <summary>Connection to the residual frontier</summary>
        <div class="content">
          <p>With opportunity set (frontier) \(\alpha_p = IR \cdot \omega_p\), the VA to be maximized is</p>
          <p>\[
          \text{VA}(\omega_p) \;=\; IR \cdot \omega_p \;-\; \lambda_r \cdot \omega_p^{2}.
          \]</p>
          
          <p>First-order condition (tangency of frontier and indifference parabola):</p>
          
          <ul>
            <li>Differentiate w.r.t. \(\omega_p\):</li>
          </ul>
          <p>\[
          \frac{d}{d\omega_p}\mathrm{VA}(\omega_p) \;=\; IR \;-\; 2\lambda_r\,\omega_p .
          \]</p>
          
          <ul>
            <li>Set the derivative to zero:</li>
          </ul>
          <p>\[
          IR - 2\lambda_r\,\omega_p^{*}=0
          \quad\Longrightarrow\quad
          \boxed{\ \omega_p^{*}=\dfrac{IR}{2\lambda_r}\ }.
          \]</p>
          
          <ul>
            <li>Equivalently, rearranging the FOC:</li>
          </ul>
          <p>\[
          \boxed{\ IR \;=\; 2\lambda_r\,\omega_p^{*}\ }.
          \]</p>
          
          <ul>
            <li>Second derivative (concavity check)</li>
          </ul>
          <p>\[
          \frac{d^2}{d\omega_p^2}\mathrm{VA}(\omega_p) = -2\lambda_r \;<\;0
          \]</p>
          
          <p>(since \(\lambda_r>0\). So the critical point is a <b>global maximum</b>.)</p>
          
          <p>Hence the <b>optimal active risk</b> and <b>return</b> are</p>
          <p>\[
          \omega_p^{*} \;=\; \frac{IR}{2\lambda_r},
          \qquad
          \alpha_p^{*} \;=\; IR \cdot \omega_p^{*} \;=\; \frac{IR^{2}}{2\lambda_r},
          \]</p>
          
          <p>and the <b>maximum value added</b> is</p>
          <p>\[
          \text{VA}^{*} \;=\; \frac{IR^{2}}{4\lambda_r}.
          \]</p>
          
          <p><b>Interpretation</b></p>
          <ul>
            <li>\(IR\) = <b>frontier slope</b> (opportunity quality).</li>
            <li>\(\lambda_r\) = <b>curvature</b> of the indifference parabola (tolerance for residual risk).</li>
            <li>Optimal aggressiveness scales <b>up</b> with \(IR\) and <b>down</b> with \(\lambda_r\):
              \(\omega_p^{*}\propto IR/\lambda_r\), \(\alpha_p^{*}\propto IR^{2}/\lambda_r\), \(\mathrm{VA}^{*}\propto IR^{2}/\lambda_r\).</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>
