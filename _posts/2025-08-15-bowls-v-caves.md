---
layout: post
title: "Bowls v. Caves"
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "'Let's get ready to RUMBLEEEE' -- Jensen"
---

<div class="flashcard">
  <details>
    <summary>The Inequality, Jensen's</summary>
    <div class="back">

      <p><strong>Proposition</strong>: Let \(x\) be a random variable with mean \(E(x)\), and let \(f(x)\) be a <strong>convex</strong> function of \(x\). Then</p>

      \[
      \mathbb{E}\!\left[f(x)\right]\;\ge\; f\!\left(\mathbb{E}[x]\right).\tag{C.1}
      \]

      <p>If \(f(x)\) is <strong>concave</strong>, the inequality is <strong>reversed</strong>.</p>

      <p><strong>In english.</strong> Apply a convex function <em>before</em> averaging ⇒ larger (or equal) value than applying it <em>after</em> averaging. For concave, the opposite ordering holds.</p>

      <p><strong>NB</strong> Convex looks like a bowl \(\cup\); concave looks like an upside-down bowl (a “cave”). Now you understand the title of the post.</p>

      <details class="dropdown-block">
        <summary>Proof of Jensen’s Inequality, not Jensen's</summary>
        <div class="content">

          <p><strong>Convexity (precise form).</strong> For any \(x,y\) and \(\lambda\in[0,1]\), with \(z=\lambda x+(1-\lambda)y\),</p>

          \[
          f(z)\;\le\;\lambda f(x)+(1-\lambda)f(y).\tag{C.2}
          \]

          <p><strong>Supporting line idea.</strong> If \(f\) is convex, there exists a line \(L(x)=a+bx\) that <strong>supports</strong> \(f\) at a chosen point and never lies above \(f\):</p>

          <ul>
            <li>Pick the point \(z\) and draw a line \(L(x)\) through \(\big(z,f(z)\big)\) such that \(f(x)\ge L(x)\) for all \(x\).</li>
            <li>Because \(L\) is linear,<br />
              \[
              \mathbb{E}[L(x)]=L\!\left(\mathbb{E}[x]\right).
              \]
            </li>
            <li>Let \(L^{\ast}(x)\) be the <strong>tangent</strong> line to \(f\) at \(\big(E(x),f(E(x))\big)\). By convexity, \(f(x)\ge L^{\ast}(x)\) for all \(x\) and equality holds at \(x=E(x)\).</li>
          </ul>

          <p>Then</p>

          \[
          \mathbb{E}[f(x)]\;\ge\;\mathbb{E}\!\left[L^{\ast}(x)\right]
          = L^{\ast}\!\left(E(x)\right)
          = f\!\left(E(x)\right),
          \]

          <p>which proves the proposition.</p>

          <p><strong>In english.</strong> A convex curve always sits <strong>above</strong> each of its tangent lines. Average first: you stay on/above the tangent evaluated at the average; evaluate first: you land <strong>on</strong> the curve at the average—therefore below or equal to the average of curve values.</p>

          <p><strong>NB 2 (context).</strong> The proof invokes the standard convex-analysis fact that a convex function admits a supporting (tangent) line at each point and that linear functions commute with expectation.</p>

        </div>
      </details>

    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Example: the exponential function (Team Bowl)</summary>
    <div class="back">

      <p>Take \(f(x)=e^{x}\) (convex). Let \(x\sim \text{Binomial}(-1,1;0.5)\), i.e., \(x\in\{-1,1\}\) with equal probability.</p>

      \[
      E(x)=0.5 \cdot (-1)+0.5 \cdot 1=0.
      \]

      <p>Function values:</p>

      \[
      f(1)=e^{1}=2.7183,\qquad f(-1)=e^{-1}=0.3679.
      \]

      <p>Then</p>

      \[
      f\!\left(E(x)\right)=e^{E(x)}=e^{0}=1,
      \]

      \[
      \mathbb{E}[f(x)]=0.5\,e^{1}+0.5\,e^{-1}=1.5431.
      \]

      <p>Hence \(\mathbb{E}[f(x)]=1.5431>1=f(E(x))\), consistent with the proposition.</p>

      <p>On the below graph \(y=e^{x}\), the <strong>chord</strong> joining \(\big(-1,e^{-1}\big)\) and \(\big(1,e^{1}\big)\) lies <strong>above</strong> the point \(\big(0,f(0)\big)=(0,1)\). Averaging \(f(-1)\) and \(f(1)\) gives the \(y\)-value of the chord at \(x=0\), which exceeds \(f(0)\); that’s Jensen for a two-point distribution.</p>
      <div id="jensen-c1" style="max-width:900px;height:520px;margin:0 auto;"></div>
      <div id="jensen-c1-numbers" style="font-size:0.9em;opacity:0.9;margin-top:8px;margin-left:auto;margin-right:auto;max-width:900px;"></div>
      <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
      <script>
        // ===== Parameters for Figure C.1 =====
        const xL = -1.5, xR = 1.5;
        const x1 = -1, x2 = 1;           // support points
        const f  = x => Math.exp(x);
      
        // Function values
        const f1 = f(x1), f2 = f(x2), f0 = f(0);
        const Ef = 0.5*(f1+f2);          // E[f(X)] for X ∈ {-1,1}, p=0.5
      
        // Chord through (-1, e^{-1}) and (1, e^1): y = a + b x
        const bChord = (f2 - f1) / (x2 - x1);
        const aChord = f1 - bChord*x1;
        const yChord = x => aChord + bChord*x;
      
        // Smooth curve y = e^x
        const grid = Array.from({length: 401}, (_, i) => xL + i*(xR - xL)/400);
        const yExp  = grid.map(f);
        const yLine = grid.map(yChord);
      
        // Traces
        const expTrace = {
          x: grid, y: yExp, mode: "lines", name: "y = e^x",
          line: {width: 3}, hovertemplate: "x=%{x:.2f}<br>e^x=%{y:.4f}<extra></extra>"
        };
      
        const chordTrace = {
          x: grid, y: yLine, mode: "lines", name: "Chord through (-1,e^{-1}) and (1,e^1)",
          line: {dash: "dash"}, hovertemplate: "x=%{x:.2f}<br>Chord=%{y:.4f}<extra></extra>"
        };
      
        const endpoints = {
          x: [x1, x2], y: [f1, f2], mode: "markers+text", name: "Endpoints",
          text: ["(-1, e^{-1})", "(1, e^1)"], textposition: "top left",
          marker: {size: 9}, hovertemplate: "x=%{x}<br>y=%{y:.4f}<extra></extra>"
        };
      
        const midpoints = {
          x: [0, 0], y: [f0, Ef], mode: "markers+text", name: "At x = E[X] = 0",
          text: ["f(E[X]) = e^0 = 1", "E[f(X)] = ½(e^{-1}+e^1)"], textposition: ["bottom right","top right"],
          marker: {size: 10, symbol: ["circle","diamond"]},
          hovertemplate: "y=%{y:.4f}<extra></extra>"
        };
      
        // Vertical guides at x = -1, 0, 1 (drawn as shapes)
        const vline = x => ({type:"line", x0:x, x1:x, y0:0, y1:Math.max(f(x), yChord(x)),
                              line:{color:"#aaa", width:1, dash:"dot"}});
        const shapes = [vline(-1), vline(0), vline(1)];
      
        const layout = {
          title: "Figure C.1 — Jensen’s Inequality with f(x)=e^x",
          xaxis: {title: "x", range: [xL, xR], zeroline: false},
          yaxis: {title: "y", rangemode: "tozero", tickformat: ".2f"},
          template: "plotly_white",
          legend: {orientation: "h", y: 1.12},
          margin: {l: 50, r: 20, t: 60, b: 40},
          shapes,
          annotations: [
            {x: 0.02, y: yChord(0), xref: "x", yref: "y", showarrow: true, ax: 40, ay: -20,
             text: "E[f(X)] = chord at x=0"},
            {x: 0, y: f0, xref:"x", yref:"y", showarrow: true, ax: -40, ay: 20,
             text: "f(E[X]) = e^0 = 1"}
          ]
        };
      
        Plotly.newPlot("jensen-c1", [expTrace, chordTrace, endpoints, midpoints], layout,
                       {displayModeBar: true, responsive: true});
      
        // ===== Numbers + intuition text =====
        const num = v => v.toFixed(4);
        const numbers = document.getElementById("jensen-c1-numbers");
        numbers.innerHTML = `
          <p>
            With \( X \in \{-1,1\} \) and \( \mathbb{P}(X{=}-1)=\mathbb{P}(X{=}1)=0.5 \), we have
          </p>
      
          \[
            \mathbb{E}[X]=0,\quad f(x)=e^{x},\quad f(\mathbb{E}[X])=e^{0}=1.
          \]
      
          \[
            \mathbb{E}[f(X)]=\tfrac{1}{2}\big(e^{-1}+e^{1}\big)=${num(Ef)} \;>\; 1=f(\mathbb{E}[X]).
          \]
      
          <p style="opacity:0.9">
            <strong>Intuition.</strong> For a convex \(f\), the curve lies <em>below</em> any chord between two points.
            Averaging function values (the chord’s height at \(x=\mathbb{E}[X]\)) exceeds the function at the average.
            That is Jensen’s inequality: \( \mathbb{E}[f(X)] \ge f(\mathbb{E}[X]) \).
          </p>
        `;
        if (window.MathJax && MathJax.typesetPromise) {
          MathJax.typesetPromise();
        }
      </script>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Why this post is in Finance Shit</summary>
    <div class="back">
      <h2>Why this post is in Finance Shit</h2>
      <ul>
        <li>With \(f=\exp\), Jensen explains why <strong>cc averages</strong> \(\frac{1}{T}\ln(\text{gross return})\) differ from averages of <strong>effective</strong> rates: \(\mathbb{E}[e^{x}]\ge e^{\mathbb{E}[x]}\).</li>
        <li>With \(f=\log\) (concave), Jensen reverses: \(\mathbb{E}[\log S]\le \log \mathbb{E}[S]\); averaging logs (e.g., utility, growth-rate calculations) penalizes dispersion.</li>
      </ul>
    </div>
  </details>
</div>
