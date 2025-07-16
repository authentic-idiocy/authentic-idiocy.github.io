---
layout: post
title:  "Probability Theory Aperitif"
date:   2025-07-15 10:00:00 -0700
categories: basic-bitch-shit        # <- must match the section header
description: "Prob. Theory Refresher"
---
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
  </head>
  <body>
    <!----- Front of the flashcard –-->
    <div class="flashcard">
    <details>
      <summary>5 "Fun"-damental Prob Rules</summary>
      <!----- Back of the flashcard –-->
      <div class="back">
        <h3>Probability of a Union</h3>
        <p>\(P(A \cup B) = P(A) + P(B) - P(A \cap B)\)<br>
        \(= P(A) + P(B)\) if \(A \cap B = \varnothing\)</p>
        <h3>Probability of a Joint (Product Rule)</h3>
        <p>
        \( p_{X,Y}(x,y)
              = p_{Y\mid X}(y\mid x)\,p_X(x)
              = p_{X\mid Y}(x\mid y)\,p_Y(y) \)
        </p>
        <h3>Marginalization (Total Probability)</h3>
        <p>
        \( p_X(x)
              = \displaystyle\int_{\mathbb R} p_{X,Y}(x,y)\,dy
              = \int_{\mathbb R} p_{X\mid Y}(x\mid y)\,p_Y(y)\,dy \)
        </p>
        <h3>Chain Rule for Densities</h3>
        <p>\(p(x_{1:D}) = p(x_1)\,p(x_2\mid x_1)\,p(x_3\mid x_{1:2})\dots p(x_D\mid x_{1:D-1})\)</p>
        <h3>Conditional Probability</h3>
        <p>\(p_{X\mid Y}(x\mid y) = \dfrac{p_{X,Y}(x,y)}{p_Y(y)}\), \(p_Y(y)>0\)</p>
      </div>
    </details>
    </div>
    <!----- Front of the flashcard 2 –-->
    <div class="flashcard">
    <details>
      <summary>Conditional + Joint + Total = Bae's Rule</summary>
      <!----- Back of the flashcard 2 –-->
      <div class="back">
        <p>Start with the definition of a conditional density<br>
        \( p_{X\mid Y}(x\mid y)=\dfrac{p_{X,Y}(x,y)}{p_Y(y)} \)</p>
        <p>Use the <strong>product rule</strong> for the joint<br>
        \( p_{X,Y}(x,y)=p_{Y\mid X}(y\mid x)\,p_X(x) \)</p>
        <p>Apply the <strong>law of total probability</strong> to the denominator<br>
        \( p_Y(y)=\displaystyle\int_{\mathbb R} p_{Y\mid X}(y\mid x')\,p_X(x')\,dx' \)</p>
        <p>Substitute both expressions</p>
        <p>\[
        p_{X\mid Y}(x\mid y)=
           \frac{p_{Y\mid X}(y\mid x)\,p_X(x)}
                {\displaystyle\int_{\mathbb R} p_{Y\mid X}(y\mid x')\,p_X(x')\,dx'}
        \]</p>
        <p><strong>Concise form</strong><br>
        \( p_{X\mid Y}(x\mid y)\;\propto\;p_{Y\mid X}(y\mid x)\,p_X(x) \)</p>
      </div>
    </details>
    </div>
  </body>
</html>



