---
layout: post
title:  "1 Pill, 2 Pill, Red Pill Blue Pill"
date:   2025-07-18 10:00:00 -0700
categories: basic-bitch-shit        # <- must match the section header
description: "Your Guide to the Matrix"
---
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
  </head>
  <body>
    <div class="flashcard">
      <details>
        <summary>We so f***ing high, row-echelon (straight up)</summary>
        <div class="back">
    
          <details class="dropdown-block">
            <summary>Setup</summary>
            <div class="content">
              <ul>
                <li><b>Linear system</b> \(A\mathbf{x} = \mathbf{b}\)
                  with \(A \in \mathbb{R}^{m \times n}\), \(\mathbf{x} \in \mathbb{R}^{n}\), \(\mathbf{b} \in \mathbb{R}^{m}\) (all column vectors).</li>
                <li><b>Augmented matrix</b></li>
              </ul>
              \[
              \begin{pmatrix}
              a_{11} & a_{12} & \dots & a_{1n} & \big| & b_{1}\\
              a_{21} & a_{22} & \dots & a_{2n} & \big| & b_{2}\\
              \vdots & \vdots & \ddots & \vdots & \big| & \vdots\\
              a_{m1} & a_{m2} & \dots & a_{mn} & \big| & b_{m}
              \end{pmatrix}
              \]
              <ul>
                <li><b>Triangular form</b>: all entries below the main diagonal are \(0\).</li>
              </ul>
            </div>
          </details>
    
          <details class="dropdown-block">
            <summary>Elementary row operations</summary>
            <div class="content">
              <ol>
                <li>Row swap \(R_i \leftrightarrow R_j\)</li>
                <li>Row scaling \(c\,R_i \;\to\; R_i\) (\(c \neq 0\))</li>
                <li>Row replacement \(c\,R_i + R_j \;\to\; R_j\)</li>
              </ol>
            </div>
          </details>
    
          <details class="dropdown-block">
            <summary>Gaussian-elimination (diagonal) procedure</summary>
            <div class="content">
              <ol>
                <li>Form the augmented matrix \([\!A\,|\,\mathbf{b}\!]\).</li>
                <li>Use elementary operations to create zeros below the diagonal.</li>
                <li>Read off equations and back-solve.</li>
              </ol>
              <small>
                <span class="define">pull out the zip?
                  <span class="tooltip">
                    <div style="max-width: 380px">
                      <p><b>Goal:</b> Solve the system by elementary row operations.</p>
              
                      <p><b>System</b></p>
                      \[
                      \begin{cases}
                      x + y = 3 \\
                      2x + 3y = 8
                      \end{cases}
                      \]
              
                      <p><b>Augmented matrix</b></p>
                      \[
                      \left[
                      \begin{array}{cc|c}
                      1 & 1 & 3 \\
                      2 & 3 & 8
                      \end{array}
                      \right]
                      \]
              
                      <ol style="margin-left:1.1rem">
                        <li><b>Make zeros below the first pivot.</b><br>
                          Row replacement \(R_2 \leftarrow R_2 - 2R_1\).
                          \[
                          \left[
                          \begin{array}{cc|c}
                          1 & 1 & 3 \\
                          0 & 1 & 2
                          \end{array}
                          \right]
                          \]
                        </li>
              
                        <li><b>Back-solve (upper-triangular reached).</b><br>
                          From row 2: \(y = 2\).<br>
                          From row 1: \(x + y = 3 \Rightarrow x = 1\).
                        </li>
              
                        <li><i>(Optional RREF cleanup.)</i><br>
                          Row replacement \(R_1 \leftarrow R_1 - R_2\).
                          \[
                          \left[
                          \begin{array}{cc|c}
                          1 & 0 & 1 \\
                          0 & 1 & 2
                          \end{array}
                          \right]
                          \]
                        </li>
                      </ol>
              
                      <p><b>Solution</b></p>
                      \[
                      (x,\,y) = (1,\,2).
                      \]
                    </div>
                  </span>
                </span>
              </small>
            </div>
          </details>
    
          <details class="dropdown-block">
            <summary>Solution counts (non-homogeneous)</summary>
            <div class="content">
              <ul>
                <li><b>No solution</b>: contradictory row \(0 = c\).</li>
                <li><b>Unique solution</b>: every variable determined.</li>
                <li><b>Infinitely many solutions</b>: at least one free variable, e.g.</li>
              </ul>
              \[
              (x_1, x_2, x_3) = (-t - 4,\; t - 1,\; t), \qquad t \in \mathbb{R}.
              \]
            </div>
          </details>
    
          <details class="dropdown-block">
            <summary>Homogeneous case \(A\mathbf{x} = \mathbf{0}\)</summary>
            <div class="content">
              <ul>
                <li>Always has the <b>trivial solution</b> \(\mathbf{x} = 0\).</li>
                <li>Otherwise the same "unique vs. infinite" dichotomy applies.</li>
              </ul>
            </div>
          </details>
    
          <details class="dropdown-block">
            <summary>Rectangular systems</summary>
            <div class="content">
              <ul>
                <li><b>Underdetermined</b> (\(m < n\)) — free variables ⇒ infinite parametric family.</li>
                <li><b>Overdetermined</b> (\(m > n\)) — may be inconsistent (contradictory row); if consistent, solve as usual.</li>
              </ul>
            </div>
          </details>
    
        </div>
      </details>
    </div>
  </body>
</html>


