---
layout: post
title:  "Heads, Shoulders, Knees, and ELBOs"
date:   2025-07-18 10:00:00 -0700
categories: ai-shit        # <- must match the section header
description: "Your VAE bae"
---

<div class="flashcard">
  <details>
    <summary>Scene</summary>
    <div class="back">
      <p><strong>Goal.</strong></p>
      <p>Maximize the likelihood of data \( x \) under a parameterized family \( p_\theta(x)=p(x\mid\theta) \). A simple and common choice for the noise model is Gaussian \( \mathcal N(x\mid \mu,\sigma) \). When a prior over latents \( z \) is used, the data likelihood is a marginal over \( z \):</p>

\[
p_\theta(x)=\int_{z} p_\theta(x,z)\,dz
\]

      <p><strong>Ch-Chain-Chain</strong><br>
      Rewrite the joint as likelihood \( \times \) prior:</p>

\[
p_\theta(x)=\int_{z} p_\theta(x\mid z)\,p_\theta(z)\,dz
\]

      <details class="dropdown-block">
        <summary>An unruly butt (i.e. intractable posterior)</summary>
        <div class="content">
          <p><strong>The different parts of Bayes Rule that I always forget.</strong></p>
          <ul>
            <li>Prior \( p_\theta(z) \)</li>
            <li>Evidence \( p_\theta(x) \)</li>
            <li>Likelihood \( p_\theta(x\mid z) \)</li>
            <li>Posterior \( p_\theta(z\mid x) \)</li>
          </ul>

          <p><strong>Bayes’ rule (general form)</strong></p>

\[
p_\theta(z \mid x)
=
\frac{p_\theta(x \mid z)\,p_\theta(z)}{p_\theta(x)}
\]

          <p>with the <b>evidence</b> (marginal likelihood)</p>

\[
p_\theta(x)
=
\int p_\theta(x \mid z)\,p_\theta(z)\,dz
\]

          <p><strong>The usual VAE choices</strong></p>
          <p>Vanilla VAE:</p>

\[
p_\theta(z)=\mathcal{N}(z \mid 0,I),
\qquad
p_\theta(x \mid z)=\mathcal{N}\!\big(x \mid \mu_\theta(z),\,\Sigma_\theta(z)\big)
\]

          <p>Hence</p>

\[
p_\theta(z \mid x)
\;\propto\;
\mathcal{N}\!\big(x \mid \mu_\theta(z),\,\Sigma_\theta(z)\big)\;
\mathcal{N}(z \mid 0,I)
\]

          <ul>
            <li>If \( \mu_\theta(\cdot) \) is <b>nonlinear</b>, this posterior is <b>not</b> Gaussian and the normalizer
              \( p_\theta(x)=\int \mathcal{N}(x \mid \mu_\theta(z),\Sigma_\theta(z))\,\mathcal{N}(z \mid 0,I)\,dz \)
              has no closed form ⇒ we approximate \( p_\theta(z \mid x) \) by \( q_\phi(z \mid x) \).</li>
          </ul>

          <p><strong>Solution: "Amortized inference."</strong><br>
          Computing \( p_\theta(z\mid x) \) is expensive/intractable, so introduce an approximate posterior</p>

\[
q_\phi(z\mid x)\approx p_\theta(z\mid x)
\]

          <p>with learnable real-valued parameters \( \phi \). This “amortized inference” lets us infer \( z \) from \( x \) quickly once \( q_\phi \) is trained.</p>

          <p><strong>Probabilistic autoencoder view:</strong></p>
          <ul>
            <li><b>Probabilistic decoder \( D_\theta \)</b> computing \( p_\theta(x\mid z) \)</li>
            <li><b>Probabilistic encoder \( E_\phi \)</b> computing \( q_\phi(z\mid x) \)</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>

<div class="flashcard">
  <details>
    <summary>Discrimination Info (i.e. 'Dickle')</summary>
    <div class="back">
      <blockquote>
        <p>'The damn thing ain't symmetric, so how the f*** can you call it a 'divergence'?!' -- Solomon Kullback</p>
      </blockquote>

      <details class="dropdown-block">
        <summary>Scene</summary>
        <div class="content">
          <p>Let \( p \) and \( q \) be two probability laws on the same space \( \mathcal X \).</p>
          <ul>
            <li><b>Absolute continuity requirement:</b> we need \( q \ll p \), i.e., whenever \( p(x)=0 \) we must also have \( q(x)=0 \). If not, \( D_{KL}(q\Vert p)=+\infty \).</li>
            <li>Expectations are written \( \mathbb E_q[\cdot] \) when \( X\sim q \).</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Defns</summary>
        <div class="content">
          <p><b>Discrete \( \mathcal X \):</b></p>

\[
D_{KL}(q\Vert p)
=
\sum_{x\in \mathcal X} q(x)\,\ln\!\frac{q(x)}{p(x)}
\]

          <p><b>Continuous \( \mathcal X \) with densities \( q(x),p(x) \):</b></p>

\[
D_{KL}(q\Vert p)
=
\int_{\mathcal X} q(x)\,\ln\!\frac{q(x)}{p(x)}\,dx
\]

          <p>The base of the logarithm sets the <b>units</b>: natural log ⇒ nats; base-2 log ⇒ bits.</p>

          <p>Equivalently, with the <b>log-likelihood ratio</b></p>

\[
\ell(x) \;:=\; \ln\!\frac{q(x)}{p(x)}
\]

          <p>we have</p>

\[
D_{KL}(q\Vert p) \;=\; \mathbb E_q[\ell(X)]
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>'Expected Extra Surprise' the oxymoron of 1951</summary>
        <div class="content">
          <p>Define <b>entropy</b> and <b>cross-entropy</b>:</p>

\[
H(q) \;:=\; -\mathbb E_q[\ln q(X)]
\]

\[
H(q,p) \;:=\; -\mathbb E_q[\ln p(X)]
\]

          <p>Then</p>

\[
D_{KL}(q\Vert p)
=
\mathbb E_q[\ln q(X)-\ln p(X)]
=
H(q,p) - H(q)
\]

          <p>This shows KL is the <b>excess code length</b>: the expected extra surprise when coding data drawn from \( q \) using a code optimized for \( p \) instead of the optimal one for \( q \).</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Non-negativity (Gibbs/Jensen proof)</summary>
        <div class="content">
          <p>Start from the definition and rewrite with \( -\ln \) (a convex function):</p>

\[
D_{KL}(q\Vert p)
=
\mathbb E_q\!\left[-\ln\!\frac{p(X)}{q(X)}\right]
\]

          <p>Apply Jensen to the convex \( -\ln(\cdot) \) with the random variable \( Y:=\frac{p(X)}{q(X)} \):</p>

\[
\mathbb E_q[-\ln Y] \;\ge\; -\ln\!\big(\mathbb E_q[Y]\big)
\]

          <p>But</p>

\[
\mathbb E_q[Y]
=
\mathbb E_q\!\left[\frac{p(X)}{q(X)}\right]
=
\int q(x)\,\frac{p(x)}{q(x)}\,dx
=
\int p(x)\,dx
=
1
\]

          <p>Hence</p>

\[
D_{KL}(q\Vert p)
\;\ge\;
-\ln 1
=
0
\]

          <p>Moreover, equality holds <b>iff</b> \( Y \) is almost surely constant under \( q \), i.e., \( \frac{p(x)}{q(x)}=1 \) for \( q \)-a.e. \( x \), which means \( p=q \) almost everywhere.</p>

\[
D_{KL}(q\Vert p)\ge 0
\quad\text{and}\quad
D_{KL}(q\Vert p)=0 \iff p=q \text{ a.e.}
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>What KL <b>ain't</b></summary>
        <div class="content">
          <ul>
            <li><b>not symmetric:</b> generally \( D_{KL}(q\Vert p)\ne D_{KL}(p\Vert q) \)</li>
            <li><b>not a metric:</b> fails symmetry and triangle inequality</li>
          </ul>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Useful identities and properties</summary>
        <div class="content">
          <ul>
            <li><b>Likelihood form:</b></li>
          </ul>

\[
D_{KL}(q\Vert p) = \mathbb E_q[\ln q] - \mathbb E_q[\ln p]
\]

          <ul>
            <li><b>Chain rule (decomposition):</b> for joint laws on \( (X,Y) \),</li>
          </ul>

\[
D_{KL}\!\big(q_{XY}\Vert p_{XY}\big)
=
D_{KL}\!\big(q_X\Vert p_X\big)
+
\mathbb E_{q_X}\!\left[D_{KL}\!\big(q_{Y\mid X}\Vert p_{Y\mid X}\big)\right]
\]

          <ul>
            <li><b>Relation to mutual information:</b></li>
          </ul>

\[
I(X;Y) \;=\; D_{KL}\!\big(p_{XY}\Vert p_X p_Y\big)
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>En Ingles</summary>
        <div class="content">
          <ul>
            <li>\( D_{KL}(q\Vert p) \) is the <b>expected log-ratio</b> of the two laws when the data are actually drawn from \( q \).</li>
            <li>It measures how <b>inefficient</b> it is to pretend the world is \( p \) when it is \( q \): extra nats/bits per observation.</li>
            <li>It is zero if and only if the two laws match almost everywhere, and grows as the laws diverge—more heavily penalizing places where \( q \) puts mass that \( p \) does not.</li>
          </ul>
        </div>
      </details>
    </div>
  </details>
</div>


<div class="flashcard">
  <details>
    <summary>ELBOw: Evidence Lower Bound whaddup.</summary>
    <div class="back">
      <p><b>Notation recap.</b></p>
      <ul>
        <li>Prior \( p_\theta(z) \)</li>
        <li>Evidence \( p_\theta(x) \)</li>
        <li>Likelihood \( p_\theta(x\mid z) \)</li>
        <li>Joint \( p_\theta(x,z)=p_\theta(x\mid z)\,p_\theta(z) \)</li>
        <li>Posterior \( p_\theta(z\mid x) \)</li>
        <li>Variational posterior \( q_\phi(z\mid x) \).</li>
      </ul>

      <hr>

      <details class="dropdown-block">
        <summary>Step 1 — Start from the evidence (marginal likelihood)</summary>
        <div class="content">
          <p>(NB: We <b>choose</b> to work with the log–evidence because \( \ln(\cdot) \) is monotone and concave.)</p>

\[
\ln p_\theta(x)
= \ln \int p_\theta(x,z)\,dz
\]

          <p>Insert the identity \( \frac{q_\phi(z\mid x)}{q_\phi(z\mid x)}=1 \) inside the integral.</p>

\[
\ln p_\theta(x)
= \ln \int q_\phi(z\mid x)\,\frac{p_\theta(x,z)}{q_\phi(z\mid x)}\,dz
\]
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Step 2 — Apply Jensen’s inequality to \( \ln(\cdot) \)</summary>
        <div class="content">
          <p><b>Jensen (concave case).</b> If \( \varphi \) is concave and \( Y\ge 0 \) is integrable under a distribution \( q \),</p>

\[
\varphi\!\big(\mathbb E_q[Y]\big) \;\ge\; \mathbb E_q[\varphi(Y)]
\]

          <p>Since \( \ln(\cdot) \) is concave, take \( \varphi=\ln \) and let</p>

\[
Y(z) \;=\; \frac{p_\theta(x,z)}{q_\phi(z\mid x)}
\]

          <p>Then, because \( \int q_\phi(z\mid x)\,Y(z)\,dz \;=\; \int p_\theta(x,z)\,dz \;=\; p_\theta(x) \),</p>

\[
\ln p_\theta(x)
\;=\;
\ln \mathbb E_{q_\phi(z\mid x)}[Y(z)]
\;\ge\;
\mathbb E_{q_\phi(z\mid x)}\!\big[\ln Y(z)\big]
\]

          <p>i.e.,</p>

\[
\ln p_\theta(x)
\;\ge\;
\mathbb E_{q_\phi(z\mid x)}\!\Big[\ln p_\theta(x,z) - \ln q_\phi(z\mid x)\Big]
\]

          <p>Define the <b>evidence lower bound</b> (ELBO) as the right-hand side.</p>

\[
\operatorname{ELBO}(\theta,\phi; x)
\;:=\;
\mathbb{E}_{z\sim q_\phi(\cdot\mid x)}
\!\left[
\ln p_\theta(x,z) - \ln q_\phi(z\mid x)
\right]
\]

          <p>Because of the inequality direction for concave \( \ln \), ELBO is a <b>lower bound</b> on \( \ln p_\theta(x) \).</p>

\[
\ln p_\theta(x)
\;\ge\;
\mathbb{E}_{z\sim q_\phi(\cdot\mid x)}
\!\left[
\ln \frac{p_\theta(x,z)}{q_\phi(z\mid x)}
\right]
\]

          <p>Thus \( \operatorname{ELBO}(\theta,\phi; x)\le \ln p_\theta(x) \).</p>
        </div>
      </details>

      <details class="dropdown-block">
        <summary>Step 3 — Equivalent identity via a KL decomposition (pedantic algebra)</summary>
        <div class="content">
          <p>Begin with the KL divergence between \( q_\phi(z\mid x) \) and the true posterior \( p_\theta(z\mid x) \).</p>

\[
D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z\mid x)\big)
=
\mathbb{E}_{z\sim q_\phi(\cdot\mid x)}
\!\left[
\ln \frac{q_\phi(z\mid x)}{p_\theta(z\mid x)}
\right]
\]

          <p>Use Bayes’ rule
          \( p_\theta(z\mid x)=\frac{p_\theta(x,z)}{p_\theta(x)} \).</p>

\[
D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z\mid x)\big)
=
\mathbb{E}_{z\sim q_\phi(\cdot\mid x)}
\!\left[
\ln \frac{q_\phi(z\mid x)\,p_\theta(x)}{p_\theta(x,z)}
\right]
\]

          <p>Pull \( \ln p_\theta(x) \) outside the expectation since it does not depend on \( z \).</p>

\[
D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z\mid x)\big)
=
\ln p_\theta(x)
+
\mathbb{E}_{z\sim q_\phi(\cdot\mid x)}
\!\left[
\ln \frac{q_\phi(z\mid x)}{p_\theta(x,z)}
\right]
\]

          <p>Rearrange to isolate \( \ln p_\theta(x) \).</p>

\[
\ln p_\theta(x)
=
\mathbb{E}_{z\sim q_\phi(\cdot\mid x)}
\!\left[
\ln p_\theta(x,z) - \ln q_\phi(z\mid x)
\right]
+
D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z\mid x)\big)
\]

          <p>Recognize the first term as the ELBO.</p>

\[
\ln p_\theta(x)
=
\operatorname{ELBO}(\theta,\phi; x)
+
D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z\mid x)\big)
\]

          <p>Since \( D_{KL}\ge 0 \), it follows that \( \operatorname{ELBO}(\theta,\phi; x)\le \ln p_\theta(x) \).</p>

\[
\forall x:\quad
\operatorname{ELBO}(\theta,\phi; x)\ \le\ \ln p_\theta(x)
\]

          <p>Maximizing the ELBO therefore tightens the bound by reducing the KL gap.</p>
        </div>
      </details>
      <details class="dropdown-block">
        <summary>Forward KL vs. Reverse KL (alt. Boxer-Briefs vs. Boxers)</summary>
        <div class="content">
          <ul>
            <li><b>KL is not symmetric.</b> \( D_{KL}(P\Vert Q)\ne D_{KL}(Q\Vert P) \) except when \( P=Q \). So we distinguish <b>forward KL</b> \( D_{KL}(P\Vert Q) \) and <b>reverse KL</b> \( D_{KL}(Q\Vert P) \).</li>
            <li><b>Why reverse KL in VI? (as you shall soon see)</b> Using forward KL would require being able to compute \( p(Z\mid X) \) (the very thing we don’t know); hence reverse KL is used in the standard derivation there.</li>
          </ul>
      
          <hr>
      
          <strong>Forward KL \( D_{KL}(P\Vert Q) \)</strong>
          <p>Forward KL is an expectation of the “penalty” \( \log \frac{p(z)}{q(z)} \) under the <b>weighting function</b> \( p(z) \):</p>
      
      \[
      D_{KL}(P\Vert Q)
      =
      \sum_{z} p(z)\,\log \frac{p(z)}{q(z)}
      =
      \mathbb{E}_{p(z)}\!\left[\log \frac{p(z)}{q(z)}\right]
      \]
      
          <ul>
            <li>Contribution is large wherever \( p(Z)>0 \) and \( q(Z) \) is small, since \( \lim_{q(z)\to 0}\log \frac{p(z)}{q(z)}\to \infty \) for \( p(z)>0 \).</li>
            <li>Minimizing forward KL therefore encourages <b>coverage</b>: ensure \( q(z)>0 \) wherever \( p(z)>0 \). This is called <b>zero-avoiding</b>.</li>
          </ul>
      
          <strong>Reverse KL \( D_{KL}(Q\Vert P) \)</strong>
          <p>Reverse KL swaps the roles:</p>
      
      \[
      D_{KL}(Q\Vert P)
      =
      \sum_{z} q(z)\,\log \frac{q(z)}{p(z)}
      =
      \mathbb{E}_{q(z)}\!\left[\log \frac{q(z)}{p(z)}\right]
      \]
      
          <ul>
            <li>To keep this finite, we must have \( q(Z)=0 \) wherever \( p(Z)=0 \); otherwise the denominator \( p(Z) \) is zero and the term blows up. This is called <b>zero-forcing</b>.</li>
            <li>Minimizing reverse KL therefore encourages <b>squeezing</b> \( Q \) to sit <b>under</b> \( P \), often concentrating mass on the highest-probability regions rather than covering all modes.</li>
          </ul>
      
          <strong>Takeaways</strong>
          <ul>
            <li><b>Forward KL</b> tends to <b>stretch/cover</b> \( P(Z) \) “like a tarp” (zero-avoiding).</li>
            <li><b>Reverse KL</b> tends to <b>squeeze/mode-seek</b> under \( P(Z) \) (zero-forcing).</li>
          </ul>
      
          <h4>NB:</h4>
          <p>with a mean-field \( Q \) fit to a <b>multimodal</b> \( P \), reverse KL can yield more <b>false negatives</b> (there is probability mass in \( P(Z) \) where \( Q(Z) \) puts none).</p>
        </div>
      </details>

           <details class="dropdown-block">
            <summary>Step 4 — Split the joint to expose the two VAE terms</summary>
            <div class="content">
              <p>We start from the ELBO definition obtained in Step 2:</p>
    
    \[
    \operatorname{ELBO}(\theta,\phi;x)
    =\mathbb E_{q_\phi}\!\Big[\ln p_\theta(x,z) - \ln q_\phi(z\mid x)\Big]
    \]
    
              <p>Now expand \( p_\theta(x,z) \) using the chain rule:</p>
    
    \[
    p_\theta(x,z) \;=\; p_\theta(x\mid z)\,p_\theta(z)
    \]
    
              <p>Apply \( \ln \) and split the sum:</p>
    
    \[
    \ln p_\theta(x,z) \;=\; \ln p_\theta(x\mid z) + \ln p_\theta(z)
    \]
    
              <p>Plug this into the ELBO and distribute the expectation:</p>
    
    \[
    \operatorname{ELBO}
    =
    \underbrace{\mathbb E_{q_\phi}\!\big[\ln p_\theta(x\mid z)\big]}_{\text{expected reconstruction log-likelihood}}
    \;+\;
    \mathbb E_{q_\phi}\!\big[\ln p_\theta(z)\big]
    \;-\;
    \mathbb E_{q_\phi}\!\big[\ln q_\phi(z\mid x)\big]
    \]
    
              <p>Recognize the <b>KL divergence to the prior</b>:</p>
    
    \[
    D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z)\big)
    =
    \mathbb E_{q_\phi}\!\big[\ln q_\phi(z\mid x) - \ln p_\theta(z)\big]
    \]
    
              <p>Rearrange that identity:</p>
    
    \[
    \mathbb E_{q_\phi}\!\big[\ln p_\theta(z)\big]
    -
    \mathbb E_{q_\phi}\!\big[\ln q_\phi(z\mid x)\big]
    =
    -\,D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z)\big)
    \]
    
              <p>Substitute back:</p>
    
    \[
    \operatorname{ELBO}(\theta,\phi; x)
    =
    \mathbb{E}_{z\sim q_\phi(\cdot\mid x)}
    \!\left[
    \ln p_\theta(x\mid z)
    \right]
    -
    D_{KL}\!\big(q_\phi(z\mid x)\,\Vert\,p_\theta(z)\big)
    \]
    
              <ul>
                <li>The first term is the <b>expected reconstruction log-likelihood</b>.</li>
                <li>The second term is a <b>regularizer</b> that pushes \( q_\phi(z\mid x) \) toward the prior \( p_\theta(z) \).</li>
              </ul>
            </div>
          </details>
    
          <details class="dropdown-block">
            <summary>Step 5 — Training objective</summary>
            <div class="content">
              <p>For a dataset \( \{x^{(i)}\}_{i=1}^N \), optimize</p>
    
    \[
    \max_{\theta,\phi}\;
    \sum_{i=1}^{N}
    \operatorname{ELBO}(\theta,\phi; x^{(i)})
    \qquad\Longleftrightarrow\qquad
    \min_{\theta,\phi}\;
    -\sum_{i=1}^{N}
    \operatorname{ELBO}(\theta,\phi; x^{(i)})
    \]
    
              <p>This is differentiable and trained by backpropagation.</p>
            </div>
          </details>
        </div>
      </details>
    </div>
