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
