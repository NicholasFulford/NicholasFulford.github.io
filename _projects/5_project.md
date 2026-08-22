---
layout: page
title: CATAM Projects
description: My final year Cambridge CATAM projects.
img: assets/img/catam.png
importance: 1
category: Academic
permalink: /catam/
---

<p>
  The CATAM (Computer-Aided Teaching of All Mathematics) projects are a modular coursework component of the Cambridge Mathematics tripos, centered around the use of computers to aid an investigation into a mathematics problem, which may itself be analytically intractable. Below are the four projects I completed in my third year, each with a summary of the project, key results, and a link to the full write-up.
</p>

<div class="catam-grid">

  <!-- ============================================================ -->
  <!-- PROJECT 1 : Parabolic Partial Differential Equations         -->
  <!-- ============================================================ -->
  <div class="catam-tile">
    <button class="catam-tile-header" type="button" aria-expanded="false">
      <div class="catam-tile-header-text">
        <span class="catam-badge">Numerical Analysis</span>
        <h4>Parabolic Partial Differential Equations</h4>
        <p class="catam-subtitle">
          Analytic vs. finite-difference solutions of the 1D heat equation with a time-varying boundary condition.
        </p>
      </div>
      <span class="catam-chevron" aria-hidden="true">&#9662;</span>
    </button>

    <div class="catam-tile-body">
      <div class="catam-tile-body-inner">

        <h5>The Project:</h5>
        <p>
          We consider the 1D diffusion equation on the unit interval, where the temperature at one end
          varies smoothly in time as \(f(t) = t(1-t)\), while the other end is held at zero. 
          First deriving an analytic Fourier-series solution by substitution and a Fourier sine
          series expansion, we then implement and compare three finite-difference time-marching
          schemes: explicit forward differencing in time, a centred leapfrog scheme, and an 
          implicit scheme. We evaluate each for stability, order of accuracy,
          and computational cost against the analytic benchmark.
        </p>

        <h5>Key Results:</h5>
        <ul>
          <li>Derived the closed-form Fourier sine series solution and its long-time asymptotic limit.</li>
          <li>Implemented all three finite-difference schemes in MATLAB, exploiting the sparsity of the tridiagonal
              matrix equation for the implicit scheme.</li>
          <li>Found the centred leapfrog scheme to be unconditionally unstable, confirming the
              theoretical prediction, and excluded it from further analysis.</li>
          <li>Identified special parameter choices (e.g. &nu; = 1/6 for the explicit scheme; specific
              &nu;&ndash;&rho; pairings for the implicit scheme) at which local truncation error
              jumps from second to fourth order due to cancellation of leading error terms.</li>
          <li>Compared total operation count vs. accuracy for the two remaining candidate protocols and
              recommended the implicit scheme with &nu; = 1/5, &rho; = 1/12 as the most
              efficient choice for a given accuracy target.</li>
          <li>Verified numerically that the solution converges to the derived long-time asymptotic
              limit as t &rarr; &infin;.</li>
        </ul>

        <div class="catam-figrow">
        <figure class="catam-fig">
            <figcaption>Plots of the analytic Fourier series solution for 𝜃(𝑥) at various times, each found by summing the first 100 terms</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_analytic.jpg' | relative_url }}" alt="Analytic solution evolution">
        </figure>
        <figure class="catam-fig">
            <figcaption>Plots of log(Computational time 𝑇) against log(Numerical step length 𝑁) for each protocol evaluated at 𝑡 = 0.5, 1 & 2</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_error.jpg' | relative_url }}" alt="Numerical error comparison">
        </figure>
        <figure class="catam-fig">
            <figcaption>Plots of the reduced temperature function 𝜙(𝑥, 𝑡) found numerically with protocol 2 and the asymptotic limit of the analytic solution for 𝜙 found in question 1</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_asymptotic.jpg' | relative_url }}" alt="Convergence to asymptotic limit">
        </figure>
        </div>

        <a class="catam-btn" href="{{ '/assets/pdf/catam_1.3_Parabolic_PDEs.pdf' | relative_url }}" target="_blank">
          Download full report (PDF)
        </a>

      </div>
    </div>
  </div>

  <!-- ============================================================ -->
  <!-- PROJECT 2 : placeholder — replace title/text/links           -->
  <!-- ============================================================ -->
  <div class="catam-tile">
    <button class="catam-tile-header" type="button" aria-expanded="false">
      <div class="catam-tile-header-text">
        <span class="catam-badge">Numerical Analysis</span>
        <h4>Padé Approximants</h4>
        <p class="catam-subtitle">
        Rational function approximants vs. truncated power series for estimating functions from their Taylor coefficients.</p>
      </div>
      <span class="catam-chevron" aria-hidden="true">&#9662;</span>
    </button>

    <div class="catam-tile-body">
      <div class="catam-tile-body-inner">

        <h5>The Project:</h5>
        <p>
          Given a power series \(f(x) = \sum c_k x^k\), we construct the \([L,M]\) Padé approximant \(R_{L,M}(x)\) (a rational function whose own power series matches \(f(x)\)'s to the highest possible order) by solving two linear systems for its numerator and denominator coefficients. Applying this to \(f_1(x) = (1+x)^{1/2}\) and \(f_2(x) = \int_0^\infty e^{-t}(1+xt)^{-1}dt\), we compare convergence, accuracy, and range of validity against the truncated power series. Finally, we investigate the pole/zero structure of the Padé approximants for six test functions to relate anomalous poles/zeros to branch cuts and singularities of the approximated function.
        </p>
        <h5>Key Results:</h5>
        <ul>
          <li>Wrote two general-purpose MATLAB routines to (A) - solve the Padé linear systems with optional iterative
              improvement for numerical accuracy, and to (B) - extract polynomial roots given the coefficients.</li>
          <li>Derived the power series for \((1+x)^{1/2}\) and showed the partial sum error in estimating \(\sqrt{2}\)
              decays as a power law \(|\epsilon_N| \approx 0.132N^{-1.490}\).</li>
          <li>Showed that the diagonal Padé approximant \(R_{L,L}(1)\) converges to \(\sqrt{2}\) *exponentially* in \(L\),
              reaching the double-precision floor (\(\sim10^{-16}\)) by \(L=10\), vastly outperforming the power series  which would need \(\sim3\times10^9\) terms for comparable accuracy.</li>
          <li>Demonstrated that the approximant remains valid for \(1 < x \le 100\) whereas the power series diverges, and 
              quantified how the exponential convergence rate in \(L\) degrades with \(x\).</li>
          <li>Mapped the poles and zeros of the Padé approximants of six functions, showing that for functions with branch
              points these cluster along the branch cut. Additionally indentified transient "defect" pairs of close proximity poles and zeros for each approximant, which did not correspond to features of the approximated function.</li>
        </ul>

        <div class="catam-figrow">
        <figure class="catam-fig">
            <figcaption>Plots of the analytic Fourier series solution for 𝜃(𝑥) at various times, each found by summing the first 100 terms</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_analytic.jpg' | relative_url }}" alt="Analytic solution evolution">
        </figure>
        <figure class="catam-fig">
            <figcaption>Plots of log(Computational time 𝑇) against log(Numerical step length 𝑁) for each protocol evaluated at 𝑡 = 0.5, 1 & 2</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_error.jpg' | relative_url }}" alt="Numerical error comparison">
        </figure>
        <figure class="catam-fig">
            <figcaption>Plots of the reduced temperature function 𝜙(𝑥, 𝑡) found numerically with protocol 2 and the asymptotic limit of the analytic solution for 𝜙 found in question 1</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_asymptotic.jpg' | relative_url }}" alt="Convergence to asymptotic limit">
        </figure>
        </div>
        <a class="catam-btn" href="{{ '/assets/pdf/catam_7.5_PadeApproximants.pdf' | relative_url }}" target="_blank">
          Download full report (PDF)
        </a>
      </div>
    </div>
  </div>

  <!-- ============================================================ -->
  <!-- PROJECT 3 : placeholder                                      -->
  <!-- ============================================================ -->
  <div class="catam-tile">
    <button class="catam-tile-header" type="button" aria-expanded="false">
      <div class="catam-tile-header-text">
        <span class="catam-badge">Category</span>
        <h4>Project 3 Title</h4>
        <p class="catam-subtitle">One-line description.</p>
      </div>
      <span class="catam-chevron" aria-hidden="true">&#9662;</span>
    </button>
    <div class="catam-tile-body">
      <div class="catam-tile-body-inner">
        <h5>The problem</h5>
        <p>Paraphrased problem statement here.</p>
        <h5>Approach &amp; key results</h5>
        <ul>
          <li>Key result 1.</li>
          <li>Key result 2.</li>
        </ul>
        <a class="catam-btn" href="{{ '/assets/pdf/catam-3.pdf' | relative_url }}" target="_blank">
          Download full report (PDF)
        </a>
      </div>
    </div>
  </div>

  <!-- ============================================================ -->
  <!-- PROJECT 4 : placeholder                                      -->
  <!-- ============================================================ -->
  <div class="catam-tile">
    <button class="catam-tile-header" type="button" aria-expanded="false">
      <div class="catam-tile-header-text">
        <span class="catam-badge">Category</span>
        <h4>Project 4 Title</h4>
        <p class="catam-subtitle">One-line description.</p>
      </div>
      <span class="catam-chevron" aria-hidden="true">&#9662;</span>
    </button>
    <div class="catam-tile-body">
      <div class="catam-tile-body-inner">
        <h5>The problem</h5>
        <p>Paraphrased problem statement here.</p>
        <h5>Approach &amp; key results</h5>
        <ul>
          <li>Key result 1.</li>
          <li>Key result 2.</li>
        </ul>
        <a class="catam-btn" href="{{ '/assets/pdf/catam-4.pdf' | relative_url }}" target="_blank">
          Download full report (PDF)
        </a>
      </div>
    </div>
  </div>

</div>

<style>
  .catam-grid {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    margin-top: 1rem;
  }

  .catam-tile {
    border: 1px solid rgba(128, 128, 128, 0.3);
    border-radius: 0.5rem;
    overflow: hidden;
  }

  .catam-tile-header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    background: none;
    border: none;
    text-align: left;
    padding: 1rem 1.25rem;
    cursor: pointer;
    font: inherit;
    color: inherit;
  }

  .catam-tile-header:hover {
    background: rgba(128, 128, 128, 0.06);
  }

  .catam-tile-header-text h4 {
    margin: 0.25rem 0;
  }

  .catam-subtitle {
    margin: 0;
    opacity: 0.75;
    font-size: 0.95rem;
  }

  .catam-badge {
    display: inline-block;
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.03em;
    padding: 0.15rem 0.5rem;
    border-radius: 999px;
    background: rgba(128, 128, 128, 0.15);
  }

  .catam-chevron {
    flex-shrink: 0;
    font-size: 1.1rem;
    transition: transform 0.2s ease;
  }

  .catam-tile-header[aria-expanded="true"] .catam-chevron {
    transform: rotate(180deg);
  }

  .catam-tile-body {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.25s ease;
  }

  .catam-tile-body-inner {
    padding: 0 1.25rem 1.25rem 1.25rem;
    border-top: 1px solid rgba(128, 128, 128, 0.2);
    padding-top: 1rem;
  }

  .catam-figrow {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    margin: 1rem 0;
  }

  .catam-figrow img {
    flex: 1 1 200px;
    max-width: 100%;
    border-radius: 0.375rem;
  }

  .catam-fig {
    flex: 0 1 220px;
    max-width: 220px;
    margin: 0;
  }

  .catam-fig figcaption {
    font-size: 0.8rem;
    font-weight: 600;
    opacity: 0.75;
    margin-bottom: 0.35rem;
  }

  .catam-fig img {
    display: block;
    width: 100%;
    max-width: 220px;
    border-radius: 0.375rem;
  }
  
  .catam-btn {
    display: inline-block;
    padding: 0.4rem 0.9rem;
    border-radius: 0.375rem;
    border: 1px solid currentColor;
    text-decoration: none;
    font-size: 0.9rem;
  }

  .catam-btn:hover {
    background: rgba(128, 128, 128, 0.1);
  }
</style>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.querySelectorAll('.catam-tile-header').forEach(function (btn) {
      btn.addEventListener('click', function () {
        var expanded = btn.getAttribute('aria-expanded') === 'true';
        var body = btn.nextElementSibling;
        btn.setAttribute('aria-expanded', String(!expanded));
        if (expanded) {
          body.style.maxHeight = null;
        } else {
          body.style.maxHeight = body.scrollHeight + 'px';
        }
      });
    });
  });
</script>