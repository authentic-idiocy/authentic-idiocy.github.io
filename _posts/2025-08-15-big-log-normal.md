---
layout: post
title: "Big Log(-normal)"
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "Stock prices are in league with the freeway."
---

<div class="flashcard">
  <details>
    <summary>A Normal Review</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>Normal density and notation</summary>
        <div class="content">
          <ul>
            <li>A r.v. \(x\) is <strong>normally distributed</strong> if it has density \(\phi\). The (two-parameter) density is
              \[
                \phi(x;\mu,\sigma)\equiv \frac{1}{\sigma\sqrt{2\pi}}\,\exp\!\left[-\tfrac12\!\left(\frac{x-\mu}{\sigma}\right)^{\!2}\right].
              \]
            </li>
            <li>"Two-parameter" = fully characterized by <strong>mean</strong> \(\mu\) (location) and <strong>std. dev.</strong> \(\sigma\) (scale/spread).</li>
            <li><strong>Standard normal density</strong>: \(\mu=0,\sigma=1\). Write \(\phi(z)\) when standardizing, and \(z\sim\mathcal N(0,1)\).</li>
            <li><strong>Symmetry about \(\mu\)</strong>:
              \[
                \phi(\mu+a;\mu,\sigma)=\phi(\mu-a;\mu,\sigma).
              \]
            </li>
            <li>Distribution notation: \(x\sim\mathcal N(\mu,\sigma^2)\).</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>CDF, areas, and probabilities</summary>
        <div class="content">
          <p>The <strong>cumulative distribution function</strong> (standard normal) is</p>
          \[
            N(a)\equiv\int_{-\infty}^{\,a}\frac{1}{\sqrt{2\pi}}e^{-\,\tfrac12 z^2}\,dz.
          \]
          <p>Geometrically: shaded area under \(\phi(z)\) to the <strong>left</strong> of \(a\). Key limits: \(N(-\infty)=0\), \(N(\infty)=1\).</p>
          <p><strong>Symmetry identity</strong>:</p>
          \[
            N(-a)=1-N(a).
          \]
          <p><strong>Between two symmetric points</strong>:</p>
          \[
            \Pr(-a<z<a)=N(a)-N(-a)=2N(a)-1.
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Standardizing and de-standardizing</summary>
        <div class="content">
          <p>Given \(x\sim\mathcal N(\mu,\sigma^2)\), define the <strong>z-score</strong></p>
          \[
            z=\frac{x-\mu}{\sigma}.
          \]
          <p>Then \(z\sim\mathcal N(0,1)\) and</p>
          \[
            \Pr(x<b)=\Pr\!\left(z<\frac{b-\mu}{\sigma}\right)=N\!\left(\frac{b-\mu}{\sigma}\right)
          \]
          \[
            \Pr(x>b)=1-\Pr(x<b)=N\!\left(\frac{\mu-b}{\sigma}\right).
          \]
          <p>Conversely, to <strong>generate</strong> a normal from a standard normal:</p>
          \[
            x=\mu+\sigma z,\quad z\sim\mathcal N(0,1).
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Sums (and affine combinations) of normals</summary>
        <div class="content">
          <p>Let \(x_i\) be jointly distributed with \(E(x_i)=\mu_i\), \(\operatorname{Var}(x_i)=\sigma_i^2\), and \(\sigma_{ij}=\operatorname{Cov}(x_i,x_j)=\rho_{ij}\sigma_i\sigma_j\). For arbitrary weights \(\omega_i\),</p>
          \[
            E\!\left(\sum_{i=1}^{n}\omega_i x_i\right)=\sum_{i=1}^{n}\omega_i\mu_i,
          \]
          \[
            \operatorname{Var}\!\left(\sum_{i=1}^{n}\omega_i x_i\right)=\sum_{i=1}^{n}\sum_{j=1}^{n}\omega_i\omega_j\sigma_{ij}.
          \]
          <p>If the \(x_i\) are <strong>jointly normal</strong>, then the weighted sum is <strong>normal</strong>:</p>
          \[
            \sum_{i=1}^{n}\omega_i x_i \sim \mathcal N\!\left(\sum_{i=1}^{n}\omega_i\mu_i,\;\sum_{i=1}^{n}\sum_{j=1}^{n}\omega_i\omega_j\sigma_{ij}\right).
          \]
          <p><strong>Two-variable special case:</strong></p>
          \[
            a x_1+b x_2 \sim \mathcal N\!\Big(a\mu_1+b\mu_2,\;a^2\sigma_1^2+b^2\sigma_2^2+2ab\,\rho\,\sigma_1\sigma_2\Big).
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>The Central Limit Theorem (CLT) — why normal is ubiquitous</summary>
        <div class="content">
          <ul>
            <li><strong>Idea.</strong> Sums of many small, <strong>independent</strong> (or merely uncorrelated) shocks with finite variance are <strong>approximately normal</strong>. Measurement error is the canonical example; many independent error sources aggregate to a bell curve.</li>
            <li><strong>Interpretation for returns.</strong> Longer-horizon continuously-compounded returns are sums of many short-horizon shocks. If those shocks are (roughly) independent with finite variance, longer-horizon returns tend toward normal—even if daily returns are not perfectly normal.</li>
          </ul>
        </div>
      </details>

      <p><strong>Top</strong> = 2 normal densities, \(\sigma=1\) vs. \(\sigma=1.5\);<br>
      <strong>Bottom</strong> = standard normal density with the area left of \(z=0.3\) shaded.</p>

      <div id="normals-combo" style="width:900px;height:620px;"></div>
      <div id="normals-combo-info" style="font-size:0.9em; opacity:0.95; margin-top:8px;"></div>

      <script>
        // ===== Helpers =====
        const phi = (x, mu=0, sig=1) =>
          (1/(sig*Math.sqrt(2*Math.PI))) * Math.exp(-0.5*Math.pow((x-mu)/sig, 2));

        // erf approximation (Abramowitz–Stegun 7.1.26) for CDF
        function erf(x){
          const a1=0.254829592,a2=-0.284496736,a3=1.421413741,a4=-1.453152027,a5=1.061405429,p=0.3275911;
          const sign = x<0 ? -1 : 1; x = Math.abs(x);
          const t = 1/(1+p*x);
          const y = 1 - ((((a5*t+a4)*t+a3)*t+a2)*t+a1)*t*Math.exp(-x*x);
          return sign*y;
        }
        const Phi = z => 0.5*(1+erf(z/Math.SQRT2));

        // ===== Grid =====
        const xL=-6, xR=6, N=1201;
        const xs = Array.from({length:N}, (_,i)=> xL + i*(xR-xL)/(N-1));

        // ===== Top panel: \u03C6(x;0,1) vs \u03C6(x;0,1.5) =====
        const traceStd = {
          x: xs, y: xs.map(x=>phi(x,0,1)), mode:"lines", name:"\u03C6(x; 0, 1)", line:{width:3},
          xaxis:"x", yaxis:"y", hovertemplate:"x=%{x:.2f}<br>\u03C6=%{y:.4f}<extra></extra>"
        };
        const traceWide = {
          x: xs, y: xs.map(x=>phi(x,0,1.5)), mode:"lines", name:"\u03C6(x; 0, 1.5)", line:{width:3, dash:"dash"},
          xaxis:"x", yaxis:"y", hovertemplate:"x=%{x:.2f}<br>\u03C6=%{y:.4f}<extra></extra>"
        };

        // ===== Bottom panel: shaded area left of z = a =====
        const a = 0.3;
        const pdf = { x: xs, y: xs.map(x=>phi(x)), mode:"lines", name:"\u03C6(z) (standard normal)",
                      xaxis:"x2", yaxis:"y2", line:{width:3},
                      hovertemplate:"z=%{x:.2f}<br>\u03C6=%{y:.4f}<extra></extra>" };

        const xLeft = xs.filter(x=>x<=a);
        const areaShade = {
          x: xLeft, y: xLeft.map(x=>phi(x)), xaxis:"x2", yaxis:"y2",
          mode:"lines", name:`Area left of z=${a}`, fill:"tozeroy", line:{width:0},
          hovertemplate:"z=%{x:.2f}<br>\u03C6=%{y:.4f}<extra></extra>"
        };

        // ===== Layout: two stacked subplots =====
        const layout = {
          title:"Normal Curves — Fig. 18.1 (top) and Fig. 18.2 top panel (bottom)",
          template:"plotly_white",
          grid:{rows:2, columns:1, pattern:"independent"},
          legend:{orientation:"h", y:1.18},
          margin:{l:55, r:20, t:70, b:40},
          xaxis:{title:"x", range:[xL,xR]},
          yaxis:{title:"Density", rangemode:"tozero"},
          xaxis2:{title:"z", range:[xL,xR]},
          yaxis2:{title:"Density", rangemode:"tozero"},
          shapes:[
            {type:"line", xref:"x2", yref:"y2", x0:a, x1:a, y0:0, y1:phi(0), line:{width:1, dash:"dot", color:"#666"}}
          ],
          annotations:[
            {xref:"x", yref:"y", x: 1.8, y: phi(1.8,0,1), text:"\u03C6(x;0,1)", showarrow:false},
            {xref:"x", yref:"y", x: -3.6, y: phi(-3.6,0,1.5), text:"\u03C6(x;0,1.5)", showarrow:false},
            {xref:"x2",yref:"y2", x:-1.8, y: 0.18, text:`Area = N(${a})`, showarrow:false, font:{size:12}}
          ]
        };

        Plotly.newPlot("normals-combo", [traceStd, traceWide, pdf, areaShade], layout,
                       {displayModeBar:true, responsive:true});

        // ===== Info / intuition =====
        const area = Phi(a);
        const phi0 = phi(0), phiWide0 = phi(0,0,1.5);
        document.getElementById("normals-combo-info").innerHTML = `
          <p>
            Normal density: \\(\phi(x;\mu,\sigma) = \dfrac{1}{\sigma\sqrt{2\pi}}
            \exp\!\Big(-\tfrac12\big(\tfrac{x-\mu}{\sigma}\big)^2\Big)\\).
            <strong>Top:</strong> with the same mean (0), increasing \\(\sigma\\) from 1 to 1.5
            lowers the peak (from \\(\phi(0;0,1)\approx ${phi0.toFixed(4)}\\) to
            \\(\phi(0;0,1.5)\approx ${phiWide0.toFixed(4)}\\)) and spreads mass toward the tails
            — but the curve remains symmetric about \\(\mu=0\\).
          </p>
          <p>
            <strong>Bottom:</strong> shading shows \\(\Pr(Z<a)=N(a)\\) for standard normal \\(Z\\).
            At \\(a=${a}\\), \\(N(${a})\approx ${area.toFixed(4)}\\), matching the shaded area.
            Symmetry gives \\(N(-a)=1-N(a)\\), and a central band probability
            \\(\Pr(-a<Z<a)=2N(a)-1\\).
          </p>
        `;

        if (window.MathJax && MathJax.typesetPromise) {
          MathJax.typesetPromise();
        }
      </script>

      <p><strong>Intuition:</strong></p>
      <ul>
        <li>Bigger \(\sigma\) ⇒ wider bell, lower peak, more probability in the shoulders/tails; symmetry around \(\mu\) is preserved.</li>
        <li>The shaded area under the standard normal pdf to the <strong>left</strong> of \(a\) is exactly the CDF value \(N(a)\). Using symmetry \(N(-a)=1-N(a)\), the central mass between \(-a\) and \(a\) is \(2N(a)-1\).</li>
      </ul>

    </div>
  </details>
</div>
