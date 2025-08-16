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
          <p>For small moves, \(r\approx R\) (<span class="define" data-def="$$&#10;\\textbf{Taylor about }a:\\quad&#10;f(x)=\\sum_{k=0}^{n}\\frac{f^{(k)}(a)}{k!}(x-a)^k \\;+\\; R_{n+1}(x).&#10;$$&#10;$$&#10;\\textbf{Maclaurin about }0:\\quad&#10;f(x)=\\sum_{k=0}^{n}\\frac{f^{(k)}(0)}{k!}x^k \\;+\\; R_{n+1}(x).&#10;$$&#10;$$&#10;\\textbf{First order (}n=1\\textbf{):}\\quad&#10;f(x)\\approx f(a)+f'(a)(x-a)\\quad\\text{or}\\quad f(x)\\approx f(0)+f'(0)x.&#10;$$&#10;Let&#10;$$&#10;R:=\\frac{S_{t+h}-S_t}{S_t}=\\frac{S_{t+h}}{S_t}-1,\\qquad&#10;r:=\\ln\\!\\left(\\frac{S_{t+h}}{S_t}\\right)=\\ln(1+R).&#10;$$&#10;Expand \\(\\ln(1+x)\\) about \\(x=0\\):&#10;$$&#10;\\ln(1+x)=x-\\frac{x^{2}}{2}+\\frac{x^{3}}{3}-\\cdots&#10;=\\sum_{k=1}^{\\infty}(-1)^{k+1}\\frac{x^{k}}{k},\\quad |x|&lt;1\\ (\\text{also converges at }x=1).&#10;$$&#10;With \\(x=R\\),&#10;$$&#10;r=\\ln(1+R)=R-\\frac{R^{2}}{2}+O(R^{3})=R+O(R^{2}).&#10;$$&#10;Hence, to first order, \\(r\\approx R\\).">first-order Taylor</span>).</p>
        </div>
      </details>

    </div>
  </details>
</div>
