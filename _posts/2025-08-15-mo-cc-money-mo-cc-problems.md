---
layout: post
title: "Mo Continuously Compounded Money, Mo Continuously Compounded Problems"
date: 2025-08-12 00:00:00 +0000
categories: [finance-shit]
description: "-- Biggie Smalls, probably."
---
<div class="flashcard">
  <details>
    <summary>Who hot, who not</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>The logarithmic function computes continuously-compounded returns from prices.</summary>
        <div class="content">
          <p>Let $S_t$ and $S_{t+h}$ be stock prices at times $t$ and $t+h$. Define the continuously-compounded return between $t$ and $t+h$ by</p>
          \[
          r_{t,t+h}=\ln\!\left(\frac{S_{t+h}}{S_t}\right).
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>The exponential function computes prices from continuously-compounded returns.</summary>
        <div class="content">
          <p>If you know $r_{t,t+h}$, recover the future price by</p>
          \[
          S_{t+h}=S_t\,e^{\,r_{t,t+h}}.
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Continuously-compounded returns are additive over subperiods.</summary>
        <div class="content">
          <p>For consecutive subperiods of length $h$ (e.g., $n$ steps),</p>
          \[
          r_{t,t+nh}=\sum_{i=1}^{n} r_{t+(i-1)h,\,t+ih}.
          \]
          <p><strong>Derivation (core step):</strong></p>
          \[
          \begin{aligned}
          r_{t,t+2h}
          &=\ln\!\left(\frac{S_{t+2h}}{S_t}\right) \\
          &=\ln\!\left(\frac{S_{t+2h}}{S_{t+h}}\cdot\frac{S_{t+h}}{S_t}\right) \\
          &=\ln\!\left(\frac{S_{t+2h}}{S_{t+h}}\right)+\ln\!\left(\frac{S_{t+h}}{S_t}\right) \\
          &= r_{t+h,\,t+2h}+r_{t,\,t+h},
          \end{aligned}
          \]
          <p>...induction, yada yada... derived for $n$.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Useful equivalences</summary>
        <div class="content">
          <p>Simple return $R_{t,t+h}:=\dfrac{S_{t+h}-S_t}{S_t}$ relates to the continuous return via</p>
          \[
          r_{t,t+h}=\ln(1+R_{t,t+h}),\qquad R_{t,t+h}=e^{\,r_{t,t+h}}-1.
          \]
          <p>For small moves, \(r\approx R\) (first-order Taylor).</p>
        </div>
      </details>

    </div>
  </details>
</div>
