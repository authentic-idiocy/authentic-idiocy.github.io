---
layout: post
title:  "1 Pill, 2 Pill, Red Pill Blue Pill"
date:   2025-07-18 10:00:00 -0700
categories: basic-bitch-shit        # <- must match the section header
description: "Your Guide to the Matrix"
---
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
          <div class="define"><small>pull out the zip?</small>
            <div class="tooltip">
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
            </div>
          </div>
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

<div class="flashcard">
  <details>
    <summary>We've reached the singularity.</summary>
    <div class="back">

      <details class="dropdown-block">
        <summary>Matrix & size notation</summary>
        <div class="content">
          <p>
            A matrix \(A\) with entries \(a_{ij}\) and size \(n\times m\) is written
          </p>
          \[
          A=\big(a_{ij}\big)_{n\times m}
          =
          \begin{pmatrix}
          a_{11}&a_{12}&\cdots&a_{1m}\\
          a_{21}&a_{22}&\cdots&a_{2m}\\
          \vdots&\vdots&\ddots&\vdots\\
          a_{n1}&a_{n2}&\cdots&a_{nm}
          \end{pmatrix}.
          \]
          <p>The size may be subscripted when needed. </p>
          <p><i>Vectors:</i> column \(n\times 1\) and row \(1\times m\) matrices are often called vectors:
          \(\;x=\big(x_1,\dots,x_n\big)^T,\; y=(y_1,\dots,y_m)\).</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Special matrices</summary>
        <div class="content">
          <ul>
            <li><b>Square:</b> \(n\times n\); “main diagonal” runs upper-left \(\to\) lower-right.</li>
            <li><b>Zero matrix:</b> \(0_{n\times m}\) (all entries \(0\)).</li>
            <li><b>Identity:</b> \(I_n\) (diagonal \(1\)’s, elsewhere \(0\)); behaves like “1” in matrix arithmetic.</li>
          </ul>
          \[
          0_{n\times m}=\begin{pmatrix}0&\cdots&0\\ \vdots&\ddots&\vdots\\ 0&\cdots&0\end{pmatrix},\qquad
          I_n=\begin{pmatrix}1&0&\cdots&0\\0&1&\cdots&0\\ \vdots&\vdots&\ddots&\vdots\\0&0&\cdots&1\end{pmatrix}.
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Arithmetic on matrices</summary>
        <div class="content">
          <ul>
            <li><b>Add/Subtract (same size only):</b> \((a_{ij})\pm(b_{ij})=(a_{ij}\pm b_{ij})\).</li>
            <li><b>Scalar multiply:</b> \(\alpha(a_{ij})=(\alpha\,a_{ij})\).</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Matrix multiplication</summary>
        <div class="content">
          <p>
            If \(A_{n\times p}\) and \(B_{p\times m}\), then the product \(C=AB\) is \(n\times m\) with
            \[
            c_{ij}=\sum_{k=1}^{p} a_{ik}\,b_{kj}.
            \]
            <b>Compatibility:</b> columns of \(A\) must equal rows of \(B\). <b>Non-commutativity:</b> even when both are defined, \(AB\) need not equal \(BA\).
          </p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Determinant</summary>
        <div class="content">
          <p>
            The determinant maps a square matrix to a number: \(\det(A)=|A|\).
            For \(2\times2\) and \(3\times3\),
          </p>
          \[
          \left|\begin{array}{cc} a&c\\ b&d\end{array}\right|=ad-cb,\qquad
          \left|\begin{array}{ccc}
          a_{11}&a_{12}&a_{13}\\
          a_{21}&a_{22}&a_{23}\\
          a_{31}&a_{32}&a_{33}
          \end{array}\right|=
          a_{11}\left|\begin{array}{cc}a_{22}&a_{23}\\ a_{32}&a_{33}\end{array}\right|
          -a_{12}\left|\begin{array}{cc}a_{21}&a_{23}\\ a_{31}&a_{33}\end{array}\right|
          +a_{13}\left|\begin{array}{cc}a_{21}&a_{22}\\ a_{31}&a_{32}\end{array}\right|.
          \]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Inverse matrix</summary>
        <div class="content">
          <p>
            For square \(A\), an inverse \(A^{-1}\) satisfies \(AA^{-1}=A^{-1}A=I_n\).
            To compute: augment with identity and row-reduce
            \[
            \big(A\;\big|\;I_n\big)\;\longrightarrow\;\big(I_n\;\big|\;A^{-1}\big),
            \]
            if possible; failure means the inverse does not exist.
          </p>
          <p><b>Fact.</b> If \(A\) is <i>nonsingular</i>, then \(A^{-1}\) exists; if \(A\) is <i>singular</i>, \(A^{-1}\) does not exist.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Systems in matrix form</summary>
        <div class="content">
          <p>
            A system can be written \(A\vec x=\vec b\) with augmented matrix \((A\;\vec b)\).
            Three possibilities: no solution, exactly one, or infinitely many.
            For square \(A\):
          </p>
          <ul>
            <li>If \(A\) is nonsingular ⇒ exactly one solution.</li>
            <li>If \(A\) is singular ⇒ either none or infinitely many.</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Homogeneous systems</summary>
        <div class="content">
          <p>
            \(A\vec x=\vec 0\) always has the trivial solution \(\vec x=\vec 0\).
            If \(A\) is nonsingular ⇒ only the trivial solution; if \(A\) is singular ⇒ infinitely many nonzero solutions.
          </p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Linear independence / dependence</summary>
        <div class="content">
          <p>
            Vectors \(\{\vec x_1,\dots,\vec x_n\}\) are <b>linearly dependent</b> if
            \[
            c_1\vec x_1+\cdots+c_n\vec x_n=\vec 0
            \]
            for some constants not all zero; otherwise they are <b>linearly independent</b>.
          </p>
          <p>
            If each vector has \(n\) components, form
            \[
            X=\big(\vec x_1\ \vec x_2\ \cdots\ \vec x_n\big).
            \]
            Then: \(X\) nonsingular (\(\det X\ne 0\)) ⇒ independent; \(X\) singular (\(\det X=0\)) ⇒ dependent, and the constants come from solving \(X\vec c=\vec 0\).
          </p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Non-examples & cautions</summary>
        <div class="content">
          <ul>
            <li>\(A+B\) undefined if sizes differ.</li>
            <li>Even when both defined, \(AB\ne BA\) in general.</li>
            <li>Inverse need not exist (singular matrices).</li>
          </ul>
        </div>
      </details>

    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Leave it to the Germans to prefix one of the most hated concepts in linear algebra.</summary>
    <div class="back">
      <small>Yeah, <span class="define">'eigen'<span class="tooltip">Oh, apparently it was Hilbert. Translates to 'own' or 'self'. Idk I'd go with the prefix 'scheisse-' (I'll let you look that one up.)</span></span> is German.</small>
      <details class="dropdown-block">
        <summary>Definition & core rewrite</summary>
        <div class="content">
          <p>
            For a square matrix \(A\), a scalar \(\lambda\) and nonzero vector \(\vec\eta\) with
            \[
            A\vec\eta=\lambda\vec\eta
            \]
            make \(\lambda\) an <b>eigenvalue</b> and \(\vec\eta\) an <b>eigenvector</b> of \(A\).
            Equivalently,
            \[
            (A-\lambda I)\vec\eta=\vec 0 .
            \]
            To get nontrivial \(\vec\eta\) we need \(A-\lambda I\) singular, i.e.
            \[
            \det(A-\lambda I)=0 .
            \]
          </p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Characteristic polynomial & multiplicity</summary>
        <div class="content">
          <ul>
            <li>\(\det(A-\lambda I)=0\) is an \(n^{\text{th}}\)-degree polynomial in \(\lambda\) (the <b>characteristic polynomial</b>).</li>
            <li>Counting multiplicity, an \(n\times n\) matrix has \(n\) eigenvalues.</li>
            <li><b>Simple</b> eigenvalue: occurs once in the list; corresponding eigenvectors are linearly independent across distinct simple eigenvalues.</li>
            <li>Eigenvalue of multiplicity \(k>1\): has between \(1\) and \(k\) linearly independent eigenvectors.</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Complex pairs (real matrices)</summary>
        <div class="content">
          <p>
            If \(A\) is real and \(\lambda=a+bi\) is an eigenvalue with eigenvector \(\vec\eta\),
            then \(\overline{\lambda}=a-bi\) is also an eigenvalue with eigenvector \(\overline{\vec\eta}\)
            (complex conjugates occur in pairs).
          </p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Computation procedure (consolidated)</summary>
        <div class="content">
          <ol>
            <li>Form the characteristic equation \(\det(A-\lambda I)=0\) and solve for eigenvalues.</li>
            <li>For each eigenvalue \(\lambda\), solve the homogeneous system \((A-\lambda I)\vec\eta=\vec0\) to get the eigenvectors (any nonzero vector in the null space).</li>
            <li>For repeated eigenvalues, find as many linearly independent eigenvectors as the null space allows (between 1 and the algebraic multiplicity).</li>
          </ol>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Example: Finding eigenvalues/eigenvectors of \(A=\begin{pmatrix}0&1&1\\[2pt]1&0&1\\[2pt]1&1&0\end{pmatrix}\)</summary>
        <div class="content">
          <p><b>Step 1 — Eigenvalues.</b></p>
          \[
          \det(A-\lambda I)
          =\left|\begin{array}{ccc}
          -\lambda&1&1\\
          1&-\lambda&1\\
          1&1&-\lambda
          \end{array}\right|
          =-\lambda^{3}+3\lambda+2
          =(\lambda-2)(\lambda+1)^2 .
          \]
          \[
          \Rightarrow\quad \lambda_1=2,\qquad \lambda_{2,3}=-1\ (\text{double}).
          \]

          <p><b>Step 2 — Eigenvectors for \(\lambda=2\).</b></p>
          Solve \((A-2I)\vec\eta=\vec0\):
          \[
          \left[\begin{array}{ccc|c}
          -2&1&1&0\\
          1&-2&1&0\\
          1&1&-2&0
          \end{array}\right]
          \;\xrightarrow{\text{row ops}}\;
          \left[\begin{array}{ccc|c}
          1&0&-1&0\\
          0&1&-1&0\\
          0&0&0&0
          \end{array}\right].
          \]
          From the reduced system: \(\eta_1=\eta_3,\ \eta_2=\eta_3\).
          Hence \(\vec\eta=(t,t,t)\). Choose \(t=1\):
          \[
          \boxed{\ \vec\eta^{(1)}=\begin{pmatrix}1\\[2pt]1\\[2pt]1\end{pmatrix}\ }.
          \]

          <p><b>Step 3 — Eigenvectors for \(\lambda=-1\).</b></p>
          Solve \((A+I)\vec\eta=\vec0\):
          \[
          \left[\begin{array}{ccc|c}
          1&1&1&0\\
          1&1&1&0\\
          1&1&1&0
          \end{array}\right]
          \ \Rightarrow\ \eta_1+\eta_2+\eta_3=0 .
          \]
          A convenient parametrization is
          \[
          \vec\eta=\begin{pmatrix}-\eta_2-\eta_3\\[2pt]\eta_2\\[2pt]\eta_3\end{pmatrix}.
          \]
          One possible basis for the eigenspace:
          \[
          \boxed{\ \begin{aligned}
          \vec\eta^{(2)}&=\begin{pmatrix}-1\\1\\0\end{pmatrix},\\
          \vec\eta^{(3)}&=\begin{pmatrix}-1\\0\\1\end{pmatrix}
          \end{aligned}\ }
          \quad\text{(two linearly independent eigenvectors).}
          \]

          <p><b>Summary.</b> \(\ \lambda_1=2\) with eigenspace \(\operatorname{span}\{(1,1,1)^T\}\); \(\ \lambda_{2,3}=-1\) with a two-dimensional eigenspace orthogonal to \((1,1,1)^T\) (e.g., spanned by the two vectors above).</p>
        </div>
      </details>

    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Primal (LP)</summary>
    <div class="back">
      <p><strong>Standard & Slack</strong></p>
      <ul>
        <li>Two useful representations for linear programs are introduced: <b>standard form</b> (all constraints are inequalities) and <b>slack form</b> (all constraints are equalities with nonnegativity as needed).</li>
      </ul>

      <details class="dropdown-block">
        <summary>Standard form (data, variables, and program)</summary>
        <div class="content">
          <p>Given:</p>
          <ul>
            <li>$n$ real numbers $c_1,\dots,c_n$ (objective coefficients),</li>
            <li>$m$ real numbers $b_1,\dots,b_m$ (right-hand sides),</li>
            <li>$m n$ real numbers $a_{ij}$ for $i=1,\dots,m,\; j=1,\dots,n$ (constraint matrix entries).</li>
          </ul>
          <p>We seek real decision variables $x_1,\dots,x_n$ that solve:</p>
          <p>\[
          \text{maximize}\quad \sum_{j=1}^{n} c_j x_j
          \]</p>
          <p>\[
          \text{subject to}\quad \sum_{j=1}^{n} a_{ij} x_j \;\le\; b_i \quad \text{for } i=1,2,\dots,m
          \]</p>
          <p>\[
          x_j \;\ge\; 0 \quad \text{for } j=1,2,\dots,n .
          \]</p>
          <p>The last inequalities are the <b>nonnegativity constraints</b>.</p>

          <h4>Compact matrix–vector notation</h4>
          <p>Let $A=(a_{ij})\in\mathbb{R}^{m\times n}$, $b=(b_i)\in\mathbb{R}^{m}$, $c=(c_j)\in\mathbb{R}^{n}$, and $x=(x_j)\in\mathbb{R}^{n}$. Then the same program is:</p>
          <p>\[
          \text{maximize}\quad c^{\mathsf T} x
          \]</p>
          <p>\[
          \text{subject to}\quad A x \;\le\; b
          \]</p>
          <p>\[
          x \;\ge\; 0 .
          \]</p>
          <p>Here, $c^{\mathsf T}x$ is the inner product, $Ax$ is a matrix–vector product, and $x\ge 0$ means each component of $x$ is nonnegative. A linear program in standard form is thus specified by the tuple $(A,b,c)$ with the dimensions above.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Solution terminology</summary>
        <div class="content">
          <ul>
            <li><b>Feasible solution.</b> A vector $\tilde{x}$ that satisfies <i>all</i> constraints</li>
            <li><b>Infeasible solution.</b> Any vector that violates at least one constraint.</li>
            <li><b>Objective value.</b> The scalar $c^{\mathsf T}\tilde{x}$ associated with a (feasible or infeasible) $\tilde{x}$.</li>
            <li><b>Optimal solution.</b> A feasible $\tilde{x}$ whose objective value is maximal among all feasible solutions.</li>
            <li><b>Optimal objective value.</b> The maximum value $c^{\mathsf T}\tilde{x}$ attained by an optimal solution.</li>
            <li><b>Feasible / infeasible program.</b> If there exists at least one feasible solution, the program is <b>feasible</b>; otherwise <b>infeasible</b>.</li>
            <li><b>Unbounded program.</b> Feasible, but the objective can be made arbitrarily large (no finite optimal objective value).
              (NB: A program can have a <b>finite</b> optimal value even if its feasible region is <b>unbounded</b>.)</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>En Ingles</summary>
        <div class="content">
          <ul>
            <li>Standard form asks: choose nonnegative decision variables $x$ to <b>maximize a linear score</b> $c^{\mathsf T}x$, while staying inside a <b>polyhedron</b> cut out by the linear inequalities $Ax\le b$.</li>
            <li>Nonnegativity $x\ge 0$ pins the search to the first orthant, which simplifies both algorithms (e.g., simplex) and theory (e.g., duality statements in later sections).</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Converting LPs to their standard form</summary>
    <div class="back">
      <details class="dropdown-block">
        <summary>When an LP is <b>not</b> in standard form</summary>
        <div class="content">
          <p>Reasons it might differ:</p>
          <ol>
            <li>Objective is a <b>minimization</b> (not maximization).</li>
            <li>Some variables <b>lack nonnegativity</b> constraints.</li>
            <li>There are <b>equality</b> constraints $=$.</li>
            <li>There are <b>$\ge$</b> (rather than $\le$) constraints.</li>
          </ol>
          <p>We want transformations that preserve <b>equivalence</b>: solutions correspond one-for-one with the <b>same</b> objective value (for max↔max), or with the <b>negated</b> value (for min→max).</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Step 1 — Flip the objective</summary>
        <div class="content">
          <p>Replace a minimization objective $\min c^{\mathsf T}x$ by a maximization with negated coefficients:</p>
          <p>\[
          \text{maximize}\; (-c)^{\mathsf T}x .
          \]</p>
          <p>Feasible set unchanged; every feasible $x$ keeps its magnitude but <b>objective value changes sign</b>, so the optima correspond.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Step 2 — Make all variables nonnegative (split "free" variables)</summary>
        <div class="content">
          <p>If some $x_j$ has no nonnegativity constraint, replace it by a <b>difference</b> of two new nonnegative variables:</p>
          <p>\[
          x_j \;=\; x'_j \;-\; x''_j, \qquad x'_j \ge 0,\; x''_j \ge 0 .
          \]</p>
          <p>Substitute everywhere:</p>
          <ul>
            <li>Objective term $c_j x_j \to c_j x'_j - c_j x''_j$.</li>
            <li>Constraint term $a_{ij} x_j \to a_{ij} x'_j - a_{ij} x''_j$.</li>
          </ul>
          <p>Mapping of solutions is exact:</p>
          <ul>
            <li>From old to new: $x'_j=\max\{x_j,0\}$, $x''_j=\max\{-x_j,0\}$.</li>
            <li>From new to old: $x_j=x'_j-x''_j$.
              Thus objective values are identical after substitution.</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Step 3 — Convert equalities to inequalities</summary>
        <div class="content">
          <p>Each equality $f(x)=b$ becomes <b>two</b> inequalities:</p>
          <p>\[
          f(x) \le b, \qquad f(x) \ge b .
          \]</p>
          <p>This preserves exactly the feasible solutions satisfying the equality.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Step 4 — Convert $\ge$ to $\le$</summary>
        <div class="content">
          <p>Multiply by $-1$ (flip both sides and the comparator):</p>
          <p>\[
          \sum_{j=1}^{n} a_{ij} x_j \ge b_i
          \quad\Longleftrightarrow\quad
          \sum_{j=1}^{n} (-a_{ij}) x_j \le -b_i .
          \]</p>
          <p>Do this for every $\ge$ constraint that remains (including those produced in Step 3).</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Step 5 — Throw it all together</summary>
        <div class="content">
          <p>After the above edits—and optional renaming so variables are $x_1,\dots,x_n$ again—the LP is in standard form:</p>
          <p>\[
          \text{maximize}\; c^{\mathsf T}x
          \]</p>
          <p>\[
          \text{subject to}\; A x \le b
          \]</p>
          <p>\[
          x \ge 0 .
          \]</p>
          <p>Here $A\in\mathbb{R}^{m\times n}$, $b\in\mathbb{R}^{m}$, $c\in\mathbb{R}^{n}$; all entries satisfy the transformed coefficients, and every variable is constrained to be nonnegative.</p>
        </div>
      </details>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>From standard to slacker</summary>
    <div class="back">
      <p><strong>Goal</strong></p>
      <p>For SIMPLEX, we prefer a representation in which the <b>only</b> inequalities are the nonnegativity constraints; all other constraints are <b>equalities</b>.</p>

      <details class="dropdown-block">
        <summary>One inequality → one equality &amp; a nonnegativity constraint</summary>
        <div class="content">
          <p>Given the standard-form inequality</p>

          <p>\[
          \sum_{j=1}^{n} a_{ij}x_j \le b_i
          \]</p>

          <p>introduce a new variable \( s \) (the <b>slack</b>) and write</p>

          <p>\[
          s \;=\; b_i - \sum_{j=1}^{n} a_{ij}x_j
          \],</p>

          <p>\[
          s \;\ge\; 0
          \].</p>

          <p>The std-form inequality holds iff both constraints describing the slack version hold. When converting a whole LP, rename the slack for the \( i \)-th inequality as \( x_{n+i} \) and write</p>

          <p>\[
          x_{n+i} \;=\; b_i - \sum_{j=1}^{n} a_{ij}x_j , \qquad x_{n+i} \ge 0
          \].</p>
        </div>
      </details>

      <hr>

      <details class="dropdown-block">
        <summary>The general slacker</summary>
        <div class="content">
          <p>Let an LP be in slack form with:</p>
          <ul>
            <li>\( N \) = indices of <b>nonbasic</b> variables, \( |N|=n \).</li>
            <li>\( B \) = indices of <b>basic</b> variables, \( |B|=m \).</li>
            <li>\( N\cup B=\{1,2,\dots,n+m\} \) and \( N\cap B=\varnothing \).</li>
            <li>Coefficients \( A=(a_{ij})_{i\in B,\,j\in N} \), right-hand sides \( b=(b_i)_{i\in B} \), reduced costs \( c=(c_j)_{j\in N} \), and optional constant \( \nu \) in the objective.</li>
          </ul>

          <p>All variables are constrained to be nonnegative. The slack form is</p>

          <p>\[
          z = \nu + \sum_{j\in N} c_j\,x_j
          \]</p>

          <p>\[
          x_i = b_i - \sum_{j\in N} a_{ij}\,x_j \quad \text{for } i\in B
          \]</p>

          <h4>Sign convention</h4>
          <p>Because the sum \( \sum_{j\in N} a_{ij}x_j \) is subtracted on the right of the slack system, the stored \( a_{ij} \) are the <b>negatives</b> of the coefficients as they visually appear in those equations.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>What this buys us (why would we want slackers?)</summary>
        <div class="content">
          <ul>
            <li><b>Basic feasible solution (BFS).</b> Set all nonbasics to zero: \( x_j=0 \) for \( j\in N \). Then basics read off as \( x_i=b_i \) for \( i\in B \). This BFS is feasible iff \( b_i\ge 0 \) for all \( i\in B \). Degeneracy occurs if some \( b_i=0 \).</li>
            <li>SIMPLEX moves between slack forms by <b>pivoting</b> (swapping one \( j\in N \) into the basis and one \( i\in B \) out), preserving the structure.</li>
            <li>The constant term \( \nu \) makes it trivial to read the current <b>objective value</b> at a BFS: set \( x_j=0 \) for \( j\in N \) in the objective, giving \( z=\nu \).</li>
            <li><b>Optimality test (reduced costs).</b> If \( c_j\le 0 \) for <b>all</b> \( j\in N \), no entering variable can improve \( z \); the current BFS is <b>optimal</b> for the maximization LP.</li>
            <li><b>Link back to standard form.</b> Each row in the slack system corresponds to an original \( \le \) constraint after introducing a <b>slack variable</b>: \( x_{n+i}=b_i-\sum_{j\in N} a_{ij}x_j \). The partition \( (B,N) \) simply records which variables are currently “solved for” (left side) versus “free to move” (right side).
              <ul>
                <li>Partitioning into \( (B,N) \) cleanly separates <b>state</b> (the equalities for basics) from <b>controls</b> (the nonbasics), which is exactly what the tableau manipulates.</li>
              </ul>
            </li>
            <li><b>State tuple.</b> A slack form is completely specified by the tuple \( (N,B,A,b,c,\nu) \). Simplex updates this tuple while preserving nonnegativity of all variables and the equality structure.</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>En Ingles</summary>
        <div class="content">
          <ul>
            <li>Slack variables measure the <b>gap</b> between the left and right sides of \( \le \) constraints.</li>
            <li>By introducing one slack per constraint, the feasible region is described by <b>equalities plus nonnegativity</b>, a format on which SIMPLEX operates by systematic swaps of basic/nonbasic roles while tracking the objective via \( \nu \) and the reduced costs \( c_j \).</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>
<div class="flashcard">
  <details>
    <summary>Duality — The double checker</summary>
    <div class="back">
      <p><strong>Purpose</strong></p>
      <p>Duality is used to <b>certify optimality</b> of linear programs. For a maximization LP (the <b>primal</b>) we construct a related <b>dual</b> minimization LP whose <b>optimal value equals</b> the primal’s optimal value. This lets us prove a candidate primal solution is optimal by exhibiting a matching-value dual solution.</p>

      <details class="dropdown-block">
        <summary>From the standard form primal to the dual</summary>
        <div class="content">

\[
\text{minimize}\quad \sum_{i=1}^{m} b_i\, y_i
\]

\[
\text{subject to}\quad \sum_{i=1}^{m} a_{ij}\, y_i \ge c_j \quad \text{for } j=1,\dots,n
\]

\[
y_i \ge 0 \quad \text{for } i=1,\dots,m
\]

          <p><b>Mapping rules:</b></p>
          <ol>
            <li>maximize ↦ minimize</li>
            <li>RHS coefficients \( b \) become the dual objective</li>
            <li>each primal constraint \( i \) gets a dual variable \( y_i \)</li>
            <li>each primal variable \( x_j \) induces a dual constraint \( j \)</li>
            <li>every “\( \le \)” becomes “\( \ge \)”</li>
            <li>nonnegativity flips consistently.</li>
          </ol>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Weak Duality Lemma</summary>
        <div class="content">
          <p>If \( \tilde{x} \) is <b>feasible</b> for the primal and \( \tilde{y} \) is <b>feasible</b> for the dual, then</p>

\[
\sum_{j=1}^{n} c_j \tilde{x}_j \;\le\; \sum_{i=1}^{m} b_i \tilde{y}_i
\]

          <p><b>Proof:</b></p>

\[
\sum_{j=1}^{n} c_j \tilde{x}_j
\;\le\;
\sum_{j=1}^{n} \Big( \sum_{i=1}^{m} a_{ij}\tilde{y}_i \Big)\tilde{x}_j
=
\sum_{i=1}^{m} \Big( \sum_{j=1}^{n} a_{ij}\tilde{x}_j \Big)\tilde{y}_i
\;\le\;
\sum_{i=1}^{m} b_i \tilde{y}_i
\]

          <ul>
            <li>The first inequality uses the dual constraints</li>
            <li>the last uses primal constraints.</li>
          </ul>

          <p><strong>Weak Duality Corollary</strong></p>
          <p>If feasible \( \tilde{x},\tilde{y} \) satisfy</p>

\[
\sum_{j=1}^{n} c_j \tilde{x}_j \;=\; \sum_{i=1}^{m} b_i \tilde{y}_i
\]

          <p>then \( \tilde{x} \) and \( \tilde{y} \) are <b>optimal</b> for their respective programs (neither can be improved by weak duality).</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Extracting an optimal dual from the primal’s final slack form</summary>
        <div class="content">
          <p>Running SIMPLEX on the primal yields a final <b>slack form</b> with basis \( B \), nonbasis \( N \),</p>

\[
z \;=\; v' \;+\; \sum_{j\in N} c'_j\, x_j
\]

\[
x_i \;=\; b'_i \;-\; \sum_{j\in N} a'_{ij}\, x_j \quad \text{for } i\in B
\]

          <p>From this we read an optimal <b>dual</b> solution by setting the below:</p>

\[
\bar{y}_i \;=\;
\begin{cases}
-\,c'_{n+i}, & \text{if } (n+i)\in N,\\
0, & \text{otherwise}.
\end{cases}
\]

          <p>Producing a matching-value dual via the final slack form simultaneously proves primal optimality.</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>En Ingles</summary>
        <div class="content">
          <ul>
            <li>Dual variables \( y_i \) act like <b>shadow prices</b> on the primal constraints; any feasible \( y \) sets an upper bound on the primal’s value.</li>
            <li>SIMPLEX’s final tableau contains exactly the information needed to <b>construct</b> such prices achieving the same value as the primal optimum, closing the gap.</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>
