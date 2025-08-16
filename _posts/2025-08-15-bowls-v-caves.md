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
