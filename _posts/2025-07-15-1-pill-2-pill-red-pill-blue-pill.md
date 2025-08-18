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
      <small>Yeah, <span class="define">'eigen'<span class="tooltip>Oh, apparently it was Hilbert. Translates to 'own' or 'self'. Idk I'd go with the prefix 'scheisse-' (I'll let you look that one up.</span></span> is German.</small>
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

