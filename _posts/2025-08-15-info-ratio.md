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
          <!-- One figure with TWO side-by-side plots:
               LEFT = Fig. 5.4 & Fig. 5.5 combined
               RIGHT = Fig. 5.6
          -->
          <div style="display:flex; gap:18px; width:1220px; max-width:100%;">
            <div id="fig-5455-left" style="flex:1; min-width:520px; height:520px;"></div>
            <div id="fig-56-right" style="flex:1; min-width:520px; height:520px;"></div>
          </div>
          <div id="fig-54556-info" style="font-size:0.9em; opacity:0.95; margin-top:10px;"></div>
          
          <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
          <script>
          (function render54556() {
            // ===== helpers =====
            const tickVals = (max=12, step=2) => Array.from({length: Math.floor(max/step)+1}, (_,i)=> i*step);
            const tickText = vals => vals.map(v => v.toFixed(0) + "%");
            const wPP = Array.from({length: 121}, (_,i)=> i*(12)/(121-1)); // ω from 0%..12% in "percent points"
          
            // ===== parameters from the screenshots' captions =====
            const lambda_r = 0.10;   // moderate residual-risk aversion
            const IR = 0.75;         // residual frontier slope in Fig. 5.5
          
            // ===== LEFT PLOT (Fig. 5.4 + Fig. 5.5 combined) =====
            // Constant VA parabolas: α = VA + λ_r * ω^2
            const VAlevels = [
              {va: 2.500, dash: "dash",    name: "VA = 2.500%"},
              {va: 1.400, dash: "dashdot", name: "VA = 1.400%"},
              {va: 0.625, dash: "solid",   name: "VA = 0.625%"}
            ];
            const vaTraces = VAlevels.map(({va, dash, name}) => ({
              x: wPP,
              y: wPP.map(w => va + lambda_r*w*w),
              mode: "lines",
              line: {width: 3, dash},
              name,
              hovertemplate: "ω=%{x:.1f}%<br>α=%{y:.2f}%<extra>"+name+"</extra>"
            }));
          
            // Residual frontier: α = IR * ω
            const frontier = {
              x: wPP,
              y: wPP.map(w => IR*w),
              mode: "lines",
              line: {width: 3},
              name: "Residual Frontier (IR=0.75)",
              hovertemplate: "ω=%{x:.1f}%<br>α=%{y:.2f}%<extra>Residual Frontier</extra>"
            };
          
            // Tangency / optimum (P*): ω* = IR/(2 λ_r), α* = IR * ω*
            const wStar = IR/(2*lambda_r);              // 3.75%
            const aStar = IR * wStar;                   // 2.8125%
            const Pstar = {
              x: [wStar], y: [aStar],
              mode: "markers+text",
              marker: {size: 11, symbol: "diamond-open"},
              text: ["P*"],
              textposition: "top center",
              name: "P*",
              hovertemplate: "P*<br>ω=%{x:.2f}%<br>α=%{y:.2f}%<extra></extra>"
            };
          
            // One feasible point on the frontier with lower VA (P0): solve VA = 0.625 on α=IR ω
            const VA0 = 0.625;
            const disc = Math.sqrt(IR*IR - 4*lambda_r*VA0);
            const w0_small = (IR - disc)/(2*lambda_r);  // smaller intersection
            const a0 = IR * w0_small;
            const P0 = {
              x: [w0_small], y: [a0],
              mode: "markers+text",
              marker: {size: 9, symbol: "circle"},
              text: ["P0"],
              textposition: "bottom right",
              name: "P0",
              hovertemplate: "P0<br>ω=%{x:.2f}%<br>α=%{y:.2f}%<extra></extra>"
            };
          
            // Origin label "B" (benchmark & cash)
            const B = {
              x: [0], y: [0],
              mode: "markers+text",
              marker: {size: 10, symbol: "square"},
              text: ["B"],
              textposition: "bottom right",
              name: "B",
              hovertemplate: "B<br>ω=0.00%<br>α=0.00%<extra></extra>"
            };
          
            const xt = tickVals(12,2), ytLeft = tickVals(14,2);
            const layoutLeft = {
              title: "Figures 5.4 + 5.5 — Constant Value-Added Lines & Residual Frontier (λ<sub>r</sub>=0.10, IR=0.75)",
              xaxis: {title: "ω (residual risk)", range: [0,12], tickvals: xt, ticktext: tickText(xt), zeroline: false},
              yaxis: {title: "α (expected residual return)", range: [0,14], tickvals: ytLeft, ticktext: tickText(ytLeft), rangemode: "tozero"},
              template: "plotly_white",
              legend: {orientation: "h", y: 1.12},
              margin: {l: 70, r: 20, t: 70, b: 55}
            };
          
            Plotly.newPlot("fig-5455-left", [...vaTraces, frontier, Pstar, P0, B], layoutLeft,
                           {displayModeBar:true, responsive:true});
          
            // ===== RIGHT PLOT (Fig. 5.6) — VA(ω) = IR·ω − λ_r·ω², show P* maximum =====
            const wPP10 = Array.from({length: 101}, (_,i)=> i*(10)/(101-1)); // 0..10%
            const VAcurve = {
              x: wPP10,
              y: wPP10.map(w => IR*w - lambda_r*w*w),
              mode: "lines",
              line: {width: 3},
              name: "VA(ω) = IR·ω − λ<sub>r</sub>·ω²",
              hovertemplate: "ω=%{x:.1f}%<br>VA=%{y:.2f}%<extra>Value Added</extra>"
            };
            const VAmax = {
              x: [wStar], y: [IR*wStar - lambda_r*wStar*wStar],
              mode: "markers+text",
              marker: {size: 11, symbol: "diamond-open"},
              text: ["P*"],
              textposition: "top center",
              name: "P*",
              hovertemplate: "P* (max VA)<br>ω=%{x:.2f}%<br>VA=%{y:.2f}%<extra></extra>"
            };
          
            const ytRight = [-3,-2,-1,0,1,2];
            const ytRightText = ytRight.map(v => (v>=0? v.toFixed(0): v.toFixed(0)) + "%");
            const layoutRight = {
              title: "Figure 5.6 — Value Added vs. Residual Risk (IR=0.75, λ<sub>r</sub>=0.10)",
              xaxis: {title: "ω", range: [0,10], tickvals: tickVals(10,2), ticktext: tickText(tickVals(10,2)), zeroline: false},
              yaxis: {title: "Value Added", range: [-3, 2], tickvals: ytRight, ticktext: ytRightText},
              template: "plotly_white",
              legend: {orientation: "h", y: 1.12},
              margin: {l: 70, r: 20, t: 70, b: 55},
              shapes: [
                // vertical guide at ω*
                {type:"line", xref:"x", yref:"paper", x0:wStar, x1:wStar, y0:0, y1:1, line:{width:1, dash:"dot"}}
              ],
              annotations: [
                {x:wStar, y:-2.7, text:"ω* = IR/(2λ)", showarrow:false, font:{size:11}}
              ]
            };
          
            Plotly.newPlot("fig-56-right", [VAcurve, VAmax], layoutRight,
                           {displayModeBar:true, responsive:true});
          
            // ===== Info / intuition =====
            document.getElementById("fig-54556-info").innerHTML = `
              <p><strong>Left (Figures 5.4 + 5.5 combined).</strong>
                The curved lines are constant value–added sets \\(\\alpha = \\text{VA} + \\lambda_r\\,\\omega^2\\) with \\(\\lambda_r=0.10\\)
                and VA levels 0.625%, 1.400%, and 2.500%. The straight ray from the origin is the residual frontier
                \\(\\alpha = IR\\,\\omega\\) with \\(IR=0.75\\). Tangency at <em>P*</em> (\\(\\omega^* = IR/(2\\lambda_r) = 3.75\\%\\))
                is the optimal active risk: any higher VA curve lies <em>above</em> the frontier (infeasible),
                and any other point on the frontier yields lower VA (e.g., <em>P0</em> on the VA=0.625% curve).
                Benchmark/cash sits at B = (0,0).</p>
          
              <p><strong>Right (Figure 5.6).</strong>
                Holding the frontier fixed, value added as a function of aggressiveness is a concave parabola
                \\(\\text{VA}(\\omega)= IR\\,\\omega - \\lambda_r\\,\\omega^2\\). The maximum occurs at the same
                \\(\\omega^* = IR/(2\\lambda_r)\\) as on the left. This is the tangency condition in a different view:
                slope of VA (\\(IR - 2\\lambda_r\\,\\omega\\)) equals zero at \\(\\omega^*\\).</p>
          
              <p style="opacity:0.85;"><small>Numbers chosen only to mirror the chapter’s figures:
                \\(IR=0.75\\), \\(\\lambda_r=0.10\\). Labels and styling replicate the screenshots’ annotations.</small></p>
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
          \text{VA}^{*} \;=\; \text{VA}[\omega_p^{*}]
          \;=\; \frac{IR^{2}}{4\lambda_r}
          \;=\; \frac{\omega_p^{*} \cdot IR}{2}
          \]</p>
          
          <p><b>Interpretation</b></p>
          <ul>
            <li>\(IR\) = <b>frontier slope</b> (opportunity quality).</li>
            <li>\(\lambda_r\) = <b>curvature</b> of the indifference parabola (tolerance for residual risk).</li>
            <li>Optimal aggressiveness scales <b>up</b> with \(IR\) and <b>down</b> with \(\lambda_r\):
              \(\omega_p^{*}\propto IR/\lambda_r\), \(\alpha_p^{*}\propto IR^{2}/\lambda_r\), \(\mathrm{VA}^{*}\propto IR^{2}/\lambda_r\).
              <ul>
                <li>Specifically:
                  <ul>
                    <li>Ability to add value <b>increases with the square</b> of \(IR\).</li>
                    <li>Ability to add value <b>decreases</b> as residual risk aversion \(\lambda_r\) rises.</li>
                    <li>A manager's \(IR\) therefore determines their <b>potential</b> to add value, while \(\lambda_r\) governs how aggressively that potential is used.</li>
                  </ul>
                </li>
              </ul>
            </li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>
<div class="flashcard">
  <details>
    <summary>The Information Ratio is the Key to Active Management</summary>
    <div class="back">
      <p>The results from maximizing the value added objective highlight a central result: regardless of risk tolerance, investors who maximize value added will <b>choose the strategy/manager with the highest \(IR\)</b>. Differences across investors arise only in <b>aggressiveness</b> (how far along the frontier they move), which is pinned down by</p>
      
      <p>\[
      \omega_p^{*} \;=\; \frac{IR}{2\lambda_r}
      \]</p>
      
      <p>and yields</p>
      
      <p>\[
      \alpha_p^{*} \;=\; IR \cdot \omega_p^{*} \;=\; \frac{IR^{2}}{2\lambda_r},
      \qquad
      \text{VA}^{*} \;=\; \frac{IR^{2}}{4\lambda_r}.
      \]</p>
      
      <details class="dropdown-block">
        <summary>The \(\beta=1\) Frontier</summary>
        <div class="content">
          <p><b>Definition.</b> In the total-risk / total-return view (ignoring benchmark timing), the portfolios selected will lie on the <b>\(\beta=1\) frontier</b>: the set of efficient portfolios with <b>beta equal to 1</b> that minimize total risk for each expected return. These need not be fully invested.</p>
          
          <p><b>Comparative geometry.</b></p>
          <ul>
            <li>"Efficient frontier" (with a risk-free asset) is the straight line through the risk-free point \(F\) and a tangency portfolio \(Q\).</li>
            <li>The <b>fully invested</b> efficient frontier begins at \(C\) and passes through \(Q\).</li>
            <li>The <b>\(\beta=1\) efficient frontier</b> starts at the <b>benchmark</b> \(B\) and runs through a point \(P\).</li>
          </ul>
          
          <p><b>Interpretation.</b></p>
          <ul>
            <li>The benchmark \(B\) is the <b>minimum-risk</b> \(\beta=1\) portfolio because it has <b>zero residual risk</b>.</li>
            <li>Any other \(\beta=1\) portfolio has the same systematic risk as \(B\) but <b>more residual risk</b>.</li>
            <li>Some portfolios outside the \(\beta=1\) frontier can dominate it in mean-variance terms, but they typically involve <b>large active risk</b>, exposing the manager to <b>business risk</b> of poor <b>relative</b> performance.</li>
          </ul>
          
          <p><b>Intersection and constraints.</b></p>
          <ul>
            <li>The \(\beta=1\) frontier and the fully invested frontier <b>cross</b> at a point that typically involves <b>high residual risk</b>.</li>
            <li>If we impose a <b>no-active-cash</b> condition, the \(\beta=1\) no-active-cash frontier is a <b>parabola centered at \(B\)</b> and passing through a portfolio \(Y\).</li>
            <li>Combining constraints (full investment + \(\beta=1\)) <b>reduces opportunities</b>; unconstrained frontiers dominate constrained ones.</li>
          </ul>

          <!-- One figure with TWO side-by-side plots:
               LEFT = Fig. 5.7  (efficient frontiers: CML, fully-invested, β=1)
               RIGHT = Fig. 5.8 (β=1 frontier + β=1 no-active-cash parabola; crossing & Y)
          -->
          <div style="display:flex; gap:18px; width:1220px; max-width:100%;">
            <div id="fig-57-left"  style="flex:1; min-width:520px; height:520px;"></div>
            <div id="fig-58-right" style="flex:1; min-width:520px; height:520px;"></div>
          </div>
          <div id="fig-57-58-info" style="font-size:0.9em; opacity:0.95; margin-top:10px;"></div>
          
          <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
          <script>
          (function render57and58() {
            // ===== Shared helpers & parameters =====
            const sigmaGrid = (max=45, n=181) => Array.from({length:n}, (_,i)=> i*max/(n-1)); // σ from 0..45
            const tick = (max, step) => ({vals: Array.from({length: Math.floor(max/step)+1}, (_,i)=> i*step),
                                          text: Array.from({length: Math.floor(max/step)+1}, (_,i)=> (i*step).toFixed(0))});
          
            // "Book-like" stylized parameters to recreate geometry (illustrative, not data-driven)
            const mu_f = 5.0;          // risk-free return level (F on μ-axis)
            const slopeCML = 0.70;     // capital-market-line slope (Sharpe)
            const muB  = 8.0;          // benchmark μ (point B)
            const sigB = 15.0;         // benchmark σ (point B)
            // Fully-invested efficient frontier (concave): μ_FI(σ) = a + b σ − c σ²
            const aFI = 1.0, bFI = 0.95, cFI = 0.010;
          
            // β=1 frontier (starts at B, concave up): μ_β1(σ) = μB + b1(σ−sigB) − k1(σ−sigB)²
            const b1 = 0.90, k1 = 0.020;
          
            // ===== LEFT: Figure 5.7 =====
            const sL = sigmaGrid(45, 181);
            const muCML   = sL.map(s => mu_f + slopeCML*s);
            const muFI    = sL.map(s => aFI + bFI*s - cFI*s*s);
            const muBeta1 = sL.map(s => muB + b1*(s - sigB) - k1*(s - sigB)*(s - sigB));
          
            // Points (approximate placements to mirror the diagram)
            const sC = 10,  muC = aFI + bFI*sC - cFI*sC*sC;             // C on FI frontier
            // Q = intersection of CML and FI
            function intersectLineCurve() {
              // Solve for s where mu_f + m s = a + b s − c s²  =>  c s² + (m-b)s + (mu_f - a) = 0
              const A = cFI, B = (slopeCML - bFI), C0 = (mu_f - aFI);
              const disc = Math.sqrt(B*B - 4*A*C0);
              const s1 = (-B + disc)/(2*A), s2 = (-B - disc)/(2*A);
              return s1 > 0 ? s1 : s2;
            }
            const sQ = intersectLineCurve(), muQ = mu_f + slopeCML*sQ;
          
            // Choose a representative P on β=1 frontier (inside CML)
            const sP = 22, muP = muB + b1*(sP - sigB) - k1*(sP - sigB)*(sP - sigB);
          
            // Down-sloping dominated line "R" (purely visual, to echo the sketch)
            const muR = sL.map(s => mu_f - 0.9*s);
          
            const leftTraces = [
              // Efficient frontier (fully invested)
              {x:sL, y:muFI, mode:"lines", name:"Fully-invested frontier", line:{width:3, dash:"dot"},
               hovertemplate:"σ=%{x:.0f}<br>μ=%{y:.1f}<extra>Fully invested</extra>"},
              // β=1 frontier (starts at benchmark B)
              {x:sL, y:muBeta1, mode:"lines", name:"β = 1 frontier", line:{width:3, dash:"dash"},
               hovertemplate:"σ=%{x:.0f}<br>μ=%{y:.1f}<extra>β = 1</extra>"},
              // Capital market line
              {x:sL, y:muCML, mode:"lines", name:"Efficient frontier (CML)", line:{width:3},
               hovertemplate:"σ=%{x:.0f}<br>μ=%{y:.1f}<extra>CML</extra>"},
              // Downward line R (dominated)
              {x:sL, y:muR, mode:"lines", name:"R (dominated region guide)", line:{width:2, dash:"dashdot"},
               hovertemplate:"σ=%{x:.0f}<br>μ=%{y:.1f}<extra>R</extra>"},
              // Points F, C, Q, B, P
              {x:[0], y:[mu_f], mode:"markers+text", name:"F", marker:{size:10, symbol:"square"},
               text:["F"], textposition:"left center", hovertemplate:"F<br>σ=0<br>μ="+mu_f.toFixed(1)+"<extra></extra>"},
              {x:[sC], y:[muC], mode:"markers+text", name:"C", marker:{size:9, symbol:"circle"},
               text:["C"], textposition:"bottom right", hovertemplate:"C<br>σ=%{x:.0f}<br>μ=%{y:.1f}<extra></extra>"},
              {x:[sQ], y:[muQ], mode:"markers+text", name:"Q", marker:{size:11, symbol:"diamond-open"},
               text:["Q"], textposition:"top left", hovertemplate:"Q<br>σ=%{x:.0f}<br>μ=%{y:.1f}<extra></extra>"},
              {x:[sigB], y:[muB], mode:"markers+text", name:"B", marker:{size:10, symbol:"square"},
               text:["B"], textposition:"right center", hovertemplate:"B<br>σ="+sigB.toFixed(0)+"<br>μ="+muB.toFixed(1)+"<extra></extra>"},
              {x:[sP], y:[muP], mode:"markers+text", name:"P", marker:{size:9, symbol:"circle"},
               text:["P"], textposition:"bottom left", hovertemplate:"P<br>σ=%{x:.0f}<br>μ=%{y:.1f}<extra></extra>"}
            ];
          
            const xt = tick(45,5), yt = tick(35,5);
            const layoutLeft = {
              title: "Efficient Frontiers (CML, Fully Invested, and β = 1)",
              xaxis: {title:"σ (total risk)", range:[0,45], tickvals:xt.vals, ticktext:xt.text, zeroline:false},
              yaxis: {title:"μ (expected total return)", range:[-15,35], tickvals:yt.vals, ticktext:yt.text},
              template:"plotly_white",
              legend:{orientation:"h", y:1.12},
              margin:{l:70, r:20, t:70, b:55}
            };
          
            Plotly.newPlot("fig-57-left", leftTraces, layoutLeft, {displayModeBar:true, responsive:true});
          
            // ===== RIGHT: Figure 5.8 =====
            // β=1 frontier (same as left)
            const beta1Trace = {x:sL, y:muBeta1, mode:"lines", name:"β = 1 frontier", line:{width:3, dash:"dash"},
              hovertemplate:"σ=%{x:.0f}<br>μ=%{y:.1f}<extra>β = 1</extra>"};
          
            // Fully invested frontier (same as left)
            const fiTrace = {x:sL, y:muFI, mode:"lines", name:"Fully-invested frontier", line:{width:3, dash:"dot"},
              hovertemplate:"σ=%{x:.0f}<br>μ=%{y:.1f}<extra>Fully invested</extra>"};
          
            // No-active-cash β=1 frontier: parabola centered at B and passing through Y
            // Choose Y on the CML at σ_Y; solve a so that μ_parab(σ_Y) = μ_CML(σ_Y)
            const sigY = 28.0, muY = mu_f + slopeCML*sigY;
            const aParab = (muY - muB)/((sigY - sigB)*(sigY - sigB)); // μ = μB + a(σ−σB)^2
            const muParab = sL.map(s => muB + aParab*(s - sigB)*(s - sigB));
          
            const nacTrace = {x:sL, y:muParab, mode:"lines", name:"β = 1 (no active cash) — parabola",
              line:{width:3}, hovertemplate:"σ=%{x:.0f}<br>μ=%{y:.1f}<extra>β = 1, no active cash</extra>"};
          
            // Crossing point (β=1 with fully-invested): solve numerically
            function intersectCurves(y1, y2, xs) {
              let sCross = xs[0], minGap = 1e9;
              xs.forEach((s,i)=>{const g=Math.abs(y1[i]-y2[i]); if(g<minGap){minGap=g; sCross=s;}});
              const i = xs.indexOf(sCross);
              return {s:sCross, mu:(y1[i]+y2[i])/2};
            }
            const cross = intersectCurves(muBeta1, muFI, sL); // approx crossing
          
            const rightTraces = [
              fiTrace, beta1Trace, nacTrace,
              {x:[sigB], y:[muB], mode:"markers+text", name:"B", marker:{size:10, symbol:"square"},
               text:["B"], textposition:"right center", hovertemplate:"B<br>σ="+sigB.toFixed(0)+"<br>μ="+muB.toFixed(1)+"<extra></extra>"},
              {x:[sigY], y:[muY], mode:"markers+text", name:"Y", marker:{size:11, symbol:"diamond-open"},
               text:["Y"], textposition:"top center", hovertemplate:"Y<br>σ=%{x:.0f}<br>μ=%{y:.1f}<extra></extra>"},
              {x:[cross.s], y:[cross.mu], mode:"markers+text", name:"Crossing", marker:{size:9, symbol:"circle"},
               text:["cross"], textposition:"bottom left", hovertemplate:"Crossing<br>σ=%{x:.0f}<br>μ=%{y:.1f}<extra></extra>"},
              {x:[0], y:[mu_f], mode:"markers+text", name:"F", marker:{size:10, symbol:"square"},
               text:["F"], textposition:"left center", hovertemplate:"F<br>σ=0<br>μ="+mu_f.toFixed(1)+"<extra></extra>"}
            ];
          
            const layoutRight = {
              title: "Figure 5.8 — β = 1 Frontier with No-Active-Cash Constraint (Parabola through Y, centered at B)",
              xaxis: {title:"σ (total risk)", range:[0,45], tickvals:xt.vals, ticktext:xt.text, zeroline:false},
              yaxis: {title:"μ (expected total return)", range:[-15,35], tickvals:yt.vals, ticktext:yt.text},
              template:"plotly_white",
              legend:{orientation:"h", y:1.12},
              margin:{l:70, r:20, t:70, b:55}
            };
          
            Plotly.newPlot("fig-58-right", rightTraces, layoutRight, {displayModeBar:true, responsive:true});
          
            // ===== Info / intuition =====
            document.getElementById("fig-57-58-info").innerHTML = `
              <p><strong>Left (Figure 5.7).</strong>
                Three efficient objects are overlaid: the straight <em>capital market line</em> (CML) from risk-free \\(F\\) through \\(Q\\),
                the <em>fully-invested</em> frontier (concave curve via \\(C\\) and \\(Q\\)), and the <em>β = 1</em> frontier that starts at the benchmark \\(B\\).
                The benchmark is the minimum-risk portfolio with \\(β=1\\) (zero residual risk). Any other \\(β=1\\) portfolio (e.g., \\(P\\))
                has the <em>same</em> systematic risk but <em>more</em> residual risk. Portfolios above the \\(β=1\\) frontier often carry large active risk,
                which creates business risk of poor <em>relative</em> performance.</p>
          
              <p><strong>Right (Figure 5.8).</strong>
                The \\(β=1\\) frontier and the fully-invested frontier <em>cross</em> at high \\(σ\\) (marked “cross”).
                Imposing a <em>no-active-cash</em> condition yields the <em>β=1</em> no-active-cash frontier, a parabola centered at \\(B\\)
                and passing through \\(Y\\). This constraint shrinks opportunity: the unconstrained frontiers dominate the constrained one.
                (Geometry replicated; numbers are illustrative to match the page diagrams.)</p>
            `;
          })();
          </script>

        </div>
      </details>
    </div>
  </details>
</div>
<div class="flashcard">
  <details>
    <summary>Forecast Alphas Directly!</summary>
    <div class="back">
      <p><b>Premise.</b> We manage <b>relative to a benchmark</b> and (fur now, KISS) ignore <b>benchmark timing</b>. Therefore we <b>need alphas</b>. Rather than forecasting expected returns and then transforming them, we can <b>skip the intermediates and forecast alphas directly</b>.</p>
      
      <p><b>A simple direct-forecasting recipe.</b></p>
      <ol>
        <li>Rank stocks into bins (e.g., strong buy / buy / hold / sell / strong sell).</li>
        <li>Assign each bin an <b>alpha</b> (e.g., \(+2\%, +1\%, 0\%, -1\%, -2\%\)).</li>
        <li>Compute the <b>benchmark average alpha</b>. If it equals zero, stop. If not, <b>neutralize</b> by subtracting "benchmark-average \(\times\) beta" from each stock's alpha so that the benchmark-weighted alpha is zero.</li>
      </ol>
      
      <p><b>Theory point.</b><br>
      This construction <b>avoids forecasting quantities</b> (like the benchmark's expected return) that <b>don't affect</b> the active portfolio and yields a <b>benchmark-neutral</b> alpha vector. With no constraints, the optimal portfolio produced by these alphas will have <b>\(\beta=1\)</b>.</p>
      
      <p><b>Why this is enough.</b></p>
      <ul>
        <li>We <b>don't need laserlike precision</b> in alpha forecasts; FLAM shows that even <b>low per-asset accuracy</b> can produce useful portfolio-level results if we keep the signal simple and pointed in the right direction.</li>
        <li>It is <b>not difficult</b> to forecast <b>alphas directly</b>, even if forecasting the full set of expected returns with precision is hard.</li>
        <li>The approach extends: e.g., do the ranking <b>by sector</b> first, then assign alphas within sectors; ensure <b>benchmark neutrality</b> after any refinement.</li>
      </ul>
      
      <details class="dropdown-block">
        <summary>Formal link to \(\beta=1\) Proof There it Is</summary>
        <div class="content">
          <p><strong>Problem</strong></p>
          <p>Given stock alphas \(\alpha\), covariance \(V\succ0\), residual-risk aversion \(\lambda_r>0\), benchmark weights \(h_B\), and stock betas \(\beta=\dfrac{Vh_B}{\sigma_B^2}\), choose <b>active</b> holdings \(h_p^{a}\) to</p>
          <p>\[
          \max_{h_p^{a}}\;\; \Phi(h_p^{a})
          := (h_p^{a})^\top \alpha\;-\;\lambda_r\,(h_p^{a})^\top V h_p^{a}.
          \]</p>
          <p>("Ignoring constraints" = unconstrained, so no Lagrange multiplier is needed.)</p>
          
          <p><strong>Gradient and first-order condition (FOC)</strong></p>
          <p>Write \(\Phi(h)=h^\top\alpha-\lambda_r\,h^\top Vh\) with \(h:=h_p^{a}\).</p>
          <ul>
            <li>\(\nabla_h(h^\top\alpha)=\alpha\).</li>
            <li>Since \(V=V^\top\), \(\nabla_h(h^\top Vh)=(V+V^\top)h=2Vh\).</li>
          </ul>
          <p>Thus</p>
          <p>\[
          \nabla_h\Phi(h)=\alpha-2\lambda_r Vh.
          \]</p>
          <p>FOC Set gradient to zero:</p>
          <p>\[
          \alpha-2\lambda_r Vh=0
          \quad\Longrightarrow\quad
          Vh=\frac{1}{2\lambda_r}\,\alpha
          \quad\Longrightarrow\quad
          \boxed{\,h_p^{a}=\frac{1}{2\lambda_r}\,V^{-1}\alpha\,}.
          \]</p>
          <p>Because \(-\lambda_r h^\top Vh\) is strictly concave ( \(V\succ0\) ), this stationary point is the unique maximizer.</p>
          
          <p><strong>Zero active beta (uses the benchmark-neutralization step)</strong></p>
          <p>Let the <b>benchmark-weighted alpha</b> be \(\alpha_B:=\alpha^\top h_B\). By the recipe's neutralization, \(\alpha_B=0\).</p>
          <p>Start from the FOC in the form \( \alpha=2\lambda_r Vh_p^{a}\) and premultiply by \(h_B^\top\):</p>
          <p>\[
          \underbrace{h_B^\top \alpha}_{=\alpha_B=0}
          \;=\;
          2\lambda_r\,h_B^\top V h_p^{a}.
          \]</p>
          <p>Use the identity from \(\beta=\dfrac{Vh_B}{\sigma_B^2}\):</p>
          <p>\[
          h_B^\top V \;=\; (Vh_B)^\top=\big(\sigma_B^2\beta\big)^\top
          =\sigma_B^2\beta^\top.
          \]</p>
          <p>Therefore</p>
          <p>\[
          0 \;=\; 2\lambda_r\,\sigma_B^2\,\beta^\top h_p^{a}
          \quad\Longrightarrow\quad
          \boxed{\,\beta^\top h_p^{a}=0\,}
          \qquad\text{(zero active beta)}.
          \]</p>
          
          <p><strong>Portfolio beta equals 1</strong></p>
          <p>Total holdings \(h_p=h_B+h_p^{a}\). Portfolio beta (relative to \(B\)) is</p>
          <p>\[
          \beta(h_p)=\beta^\top h_p
          =\beta^\top h_B+\beta^\top h_p^{a}.
          \]</p>
          <p>By definition of \(\beta\), the benchmark's own beta is one:</p>
          <p>\[
          \beta^\top h_B
          =\frac{(Vh_B)^\top h_B}{\sigma_B^2}
          =\frac{h_B^\top Vh_B}{\sigma_B^2}
          =\frac{\sigma_B^2}{\sigma_B^2}=1.
          \]</p>
          <p>Combine with \(\beta^\top h_p^{a}=0\):</p>
          <p>\[
          \boxed{\,\beta(h_p)=1\,}.
          \]</p>
          
          <p><b>En Ingles</b></p>
          <ul>
            <li>The unconstrained mean-variance active optimizer is \(h_p^{a}\propto V^{-1}\alpha\).</li>
            <li>Benchmark-neutralization (\(\alpha_B=0\)) forces the optimizer's <b>active beta to zero</b>.</li>
            <li>Adding this active to the benchmark leaves the <b>total portfolio's beta at 1</b>.</li>
          </ul>
        </div>
      </details>
      <div id="alpha-forecasting-fig" style="width:980px;height:560px;"></div>
      <div id="alpha-forecasting-fig-info" style="font-size:0.9em; opacity:0.95; margin-top:8px;"></div>
      
      <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
      <script>
        // ============================================================
        // Plot: Direct-forecasting recipe → neutral alphas → β=1 frontier
        // ============================================================
        function renderAlphaForecasting() {
          // ---------- 1) Synthetic universe ----------
          const N = 40;                                  // stocks
          const rng = () => Math.random();
      
          // Helper: Dirichlet(1,...,1) for benchmark weights h_B
          const dirichlet1 = (n) => {
            const xs = Array.from({length: n}, () => -Math.log(1 - rng())); // Exp(1)
            const s = xs.reduce((a,b)=>a+b,0);
            return xs.map(v => v/s);
          };
      
          const hB = dirichlet1(N);                      // benchmark weights (sum=1)
      
          // Idiosyncratic variances (diagonal V for clarity)
          const idioVar = Array.from({length:N}, () => {
            const s = 0.15 + 0.25*rng();                 // st.dev in [15%, 40%] (arbitrary units)
            return s*s;
          });
      
          // Covariance V = diag(idioVar); its inverse
          const VinvDiag = idioVar.map(v => 1.0/v);
      
          // Make betas consistent with h_B: β = (V h_B) / (h_B^T V h_B)
          const VhB = hB.map((w,i) => idioVar[i]*w);
          const sigmaB2 = hB.reduce((acc, w, i) => acc + w*VhB[i], 0);
          const beta = VhB.map(x => x / sigmaB2);
      
          // ---------- 2) Direct-forecasting recipe ----------
          // (a) Rank→bins via a noisy score; (b) assign bin alphas; (c) neutralize by α ← α - α_B β
          // Five bins: strong sell / sell / hold / buy / strong buy
          const binLabels = ['SSell','Sell','Hold','Buy','SBuy'];
          const binAlpha  = [-0.02, -0.01, 0.00, 0.01, 0.02];   // ±2%, ±1%, 0%
      
          // Rank via score; compute quantile thresholds
          const score = Array.from({length:N}, () => (Math.sqrt(-2*Math.log(1-rng()))*Math.cos(2*Math.PI*rng()))); // N(0,1)
          const idx = [...Array(N).keys()].sort((i,j)=>score[i]-score[j]);
          const q = [0.2,0.4,0.6,0.8,1.0].map(x => Math.floor(x*N)-1);
      
          const bin = Array(N).fill(0);
          idx.forEach((id, k) => {
            bin[id] = (k<=q[0])?0:(k<=q[1])?1:(k<=q[2])?2:(k<=q[3])?3:4;
          });
      
          const alphaRaw = bin.map(b => binAlpha[b]);
          const alphaB = alphaRaw.reduce((acc,a,i)=>acc + a*hB[i], 0);       // benchmark-average alpha
          const alphaNeu = alphaRaw.map((a,i) => a - alphaB*beta[i]);        // α ← α - α_B β
      
          // ---------- 3) Active optimizer direction (unconstrained) ----------
          // h_A ∝ V^{-1} α (scale irrelevant for geometry)
          const hA = alphaNeu.map((a,i) => VinvDiag[i]*a);
      
          // Checks (theory): α_B = 0 by construction; active beta β^T h_A should be 0.
          const activeBeta = beta.reduce((acc,b,i)=>acc + b*hA[i], 0);       // ≈ 0 numerically
      
          // Residual risk & return along the active ray t·h_A (β=0 so total β stays 1 when added to h_B)
          const alphaA = alphaNeu.reduce((acc,a,i)=>acc + a*hA[i], 0);
          const omegaA = Math.sqrt(hA.reduce((acc,hi,i)=>acc + hi*hi*idioVar[i], 0));
          const IR_A   = alphaA / omegaA;
      
          // Sample the β=1 frontier created by total portfolios h(t)=h_B + t h_A (in residual (α,ω)-space)
          const tMax = 2.0, Nt = 60;
          const tGrid = Array.from({length:Nt}, (_,k)=> -tMax + 2*tMax*k/(Nt-1));
          const alphaLine = tGrid.map(t => t*alphaA);
          const omegaLine = tGrid.map(t => Math.abs(t)*omegaA);
      
          // ---------- 4) Panel A: stock-level scatter before vs after neutralization ----------
          const colors = ['#e64b5d','#f28e2b','#9e9e9e','#4e79a7','#59a14f']; // 5 bins
          const traceRaw = {
            x: beta,
            y: alphaRaw,
            mode: 'markers',
            name: 'α (raw)',
            marker: {size: 8, opacity: 0.85, color: bin.map(b=>colors[b])},
            hovertemplate: 'β=%{x:.2f}<br>α_raw=%{y:.2%}<br>bin=%{text}<extra></extra>',
            text: bin.map(b=>binLabels[b]),
            xaxis: 'x', yaxis: 'y'
          };
      
          const traceNeu = {
            x: beta,
            y: alphaNeu,
            mode: 'markers',
            name: 'α (neutral)',
            marker: {size: 9, symbol: 'star', line:{width:1}, color: '#111'},
            hovertemplate: 'β=%{x:.2f}<br>α_neu=%{y:.2%}<extra></extra>',
            xaxis: 'x', yaxis: 'y'
          };
      
          // Connect each stock (raw→neutral) with a dashed segment
          const xSeg = [], ySeg = [];
          for (let i=0;i<N;i++){
            xSeg.push(beta[i]);   ySeg.push(alphaRaw[i]);
            xSeg.push(beta[i]);   ySeg.push(alphaNeu[i]);
            xSeg.push(null);      ySeg.push(null); // gap between segments
          }
          const traceSeg = {
            x: xSeg, y: ySeg, mode: 'lines', name: 'neutralization: α ← α - α_B β',
            line: {dash: 'dot', width: 1.5, color: 'rgba(50,50,50,0.5)'},
            hoverinfo: 'skip', xaxis: 'x', yaxis: 'y', showlegend: true
          };
      
          // α_B horizontal line
          const shapeAlphaB = {
            type: 'line', xref: 'x', yref: 'y',
            x0: Math.min(...beta)-0.05, x1: Math.max(...beta)+0.05, y0: alphaB, y1: alphaB,
            line:{color:'#d62728', width:1.5, dash:'dash'}
          };
      
          // ---------- 5) Panel B: β=1 frontier in residual (α, ω) space ----------
          const traceFrontier = {
            x: omegaLine, y: alphaLine, mode:'lines',
            name: 'β=1 frontier: h = h_B + t·h_A',
            line: {width: 3, color: '#4e79a7'},
            hovertemplate: 'ω=%{x:.2%}<br>α=%{y:.2%}<extra></extra>',
            xaxis: 'x2', yaxis: 'y2'
          };
      
          const traceApoint = {
            x: [omegaA], y: [alphaA], mode: 'markers+text',
            name: 'A (unit active)',
            marker: {size: 10, color:'#111'},
            text: ['A'], textposition: 'top center',
            hovertemplate: 'ω_A=%{x:.2%}<br>α_A=%{y:.2%}<extra></extra>',
            xaxis: 'x2', yaxis: 'y2'
          };
      
          const traceOrigin = {
            x: [0], y: [0], mode: 'markers+text',
            name: 'B (no active)',
            marker: {size: 9, color:'#9e9e9e'},
            text: ['B'], textposition: 'top right',
            hovertemplate: 'ω=0<br>α=0<extra></extra>',
            xaxis: 'x2', yaxis: 'y2'
          };
      
          // Slope annotation line (IR_A)
          const slopeShape = {
            type:'line', xref:'x2', yref:'y2',
            x0: 0, y0: 0, x1: omegaA, y1: alphaA,
            line: {color:'#111', width:1.5, dash:'dot'}
          };
      
          // ---------- 6) Layout (two panels) ----------
          const layout = {
            template: 'plotly_white',
            margin: {l:60, r:30, t:55, b:55},
            legend: {orientation:'h', y: 1.16},
            title: {text: "Direct Forecasting → Benchmark-Neutral α and the β = 1 Frontier"},
            grid: {rows:1, columns:2, pattern:'independent'},
            // Panel A
            xaxis:  {title: "β (stock)", zeroline:false},
            yaxis:  {title: "α (stock)", tickformat: ".1%", zeroline:false},
            shapes: [shapeAlphaB, slopeShape],
            annotations: [
              // Panel A annotations
              {
                x: Math.max(...beta), y: alphaB, xref:'x', yref:'y',
                text: "benchmark-average α_B", showarrow:false, xanchor:'right', yanchor:'bottom',
                font:{color:'#d62728', size:12}, bgcolor:'rgba(255,255,255,0.4)', bordercolor:'#d62728'
              },
              {
                x: 0.02, y: 1.12, xref:'paper', yref:'paper',
                text: "<b>Panel A</b>: stock-level α before (colored by bin) and after neutralization (★).",
                showarrow:false, align:'left'
              },
              // Panel B annotations
              {
                x: 0.98, y: 1.12, xref:'paper', yref:'paper',
                text: "<b>Panel B</b>: residual (α, ω) line for total portfolios h = h_B + t·h_A (β≡1).",
                showarrow:false, align:'right'
              },
              {
                x: omegaA, y: alphaA, xref:'x2', yref:'y2',
                text: `IR_A = α_A / ω_A = ${IR_A.toFixed(2)}`,
                showarrow:true, ax:-30, ay:-30, arrowwidth:1.2, borderpad:3,
                bgcolor:'rgba(255,255,255,0.7)'
              },
              {
                x: 0, y: 0, xref:'x2', yref:'y2',
                text: "slope = IR_A", showarrow:false, yshift:-22, font:{size:12, color:'#111'}
              }
            ],
            // Panel B axes
            xaxis2: {title: "ω (residual risk)", tickformat: ".1%", rangemode:'tozero', zeroline:false},
            yaxis2: {title: "α (residual return)", tickformat: ".1%", rangemode:'tozero', zeroline:false}
          };
      
          const data = [traceSeg, traceRaw, traceNeu, traceFrontier, traceOrigin, traceApoint];
      
          Plotly.newPlot("alpha-forecasting-fig", data, layout,
                         {displayModeBar: true, responsive: true});
      
          // ---------- 7) Info/intuition below plot ----------
          const avgAlphaRaw = (100*alphaB).toFixed(2);
          const betaDothA   = activeBeta; // ~ 0
          const betaDotStr  = Math.abs(betaDothA) < 1e-10 ? "≈ 0" : betaDothA.toFixed(6);
      
          document.getElementById("alpha-forecasting-fig-info").innerHTML = `
            <p><strong>Direct-forecasting recipe (Panel A).</strong>
            Stocks are ranked into bins and assigned bin-level alphas \\(\\alpha_i\\in\\{-2\\%,-1\\%,0,1\\%,2\\%\\}\\).
            The benchmark-average alpha is \\(\\alpha_B=\\alpha^\\top h_B=${avgAlphaRaw}\\%\\).
            To <em>neutralize</em>, set \\(\\tilde\\alpha\\leftarrow \\alpha-\\alpha_B\\,\\beta\\).
            Then \\(\\tilde\\alpha^\\top h_B=\\alpha_B-\\alpha_B\\,\\beta^\\top h_B=0\\) since \\(\\beta^\\top h_B=1\\).
            The dashed segments show the per-stock adjustment \\(\\alpha_i\\to\\tilde\\alpha_i\\).</p>
      
            <p><strong>β-neutral optimal active & the β=1 frontier (Panel B).</strong>
            With neutralized alphas, the unconstrained mean–variance active is
            \\(h_A\\propto V^{-1}\\tilde\\alpha\\).
            Its beta is <em>zero</em>: \\(\\beta^\\top h_A = (Vh_B/\\sigma_B^2)^\\top V^{-1}\\tilde\\alpha
            = h_B^\\top\\tilde\\alpha/\\sigma_B^2 = 0\\).
            Therefore total portfolios \\(h(t)=h_B+t\\,h_A\\) satisfy \\(\\beta(h(t))\\equiv 1\\) for all \\(t\\).
            In residual (\\(\\alpha,\\omega\\)) space, this generates a straight line through the origin with slope
            \\(IR_A=\\alpha_A/\\omega_A\\) (dotted segment). Point <b>B</b> is “benchmark only” (no active);
            point <b>A</b> is one unit of the optimal active.</p>
      
            <p><strong>Takeaways.</strong>
            (i) Neutralization removes irrelevant level effects (benchmark timing) by enforcing \\(\\alpha_B=0\\).
            (ii) The optimizer then produces a β-neutral active, so scaling that active on top of the benchmark
            moves you along the <em>β=1 frontier</em>.
            (iii) The slope equals the information ratio of the active, so sizing is a one-parameter choice.</p>
          `;
        }
      
        // Render on load
        renderAlphaForecasting();
      </script>

    </div>
  </details>
</div>
