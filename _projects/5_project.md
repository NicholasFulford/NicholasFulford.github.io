---
layout: page
title: CATAM Projects
description: Four Cambridge CATAM projects, each pairing an analytic derivation with a numerical implementation.
img: assets/img/catam.png
importance: 1
category: Academic
permalink: /catam/
---

<p>
  CATAM (Computer-Aided Teaching of All Mathematics) is a Cambridge Mathematics course unit in which
  each project poses an open-ended mathematical problem — typically requiring an analytic derivation
  followed by a numerical implementation, error analysis, and discussion of results. Below are four
  projects I completed, each summarised with the problem, my approach and key results, and a link to
  the full write-up.
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

        <h5>The problem</h5>
        <p>
          Solve the 1D diffusion equation on the unit interval, where the temperature at one end
          varies smoothly in time as a pulse, <d-math>f(t) = t(1-t)</d-math>, while the other end
          is held at zero. First derive an analytic solution by substitution and a Fourier sine
          series expansion, then implement and compare three finite-difference time-marching
          schemes &mdash; explicit forward-differencing, a centred (leapfrog) scheme, and a
          semi-implicit &theta;-scheme &mdash; evaluating each for stability, order of accuracy,
          and computational cost against the analytic benchmark.
        </p>

        <h5>Approach &amp; key results</h5>
        <ul>
          <li>Derived the closed-form Fourier sine series solution and its long-time asymptotic limit.</li>
          <li>Implemented all three finite-difference schemes in MATLAB, exploiting sparsity for the
              implicit scheme via tridiagonal solves.</li>
          <li>Found the centred (leapfrog) scheme to be unconditionally unstable, confirming the
              theoretical prediction, and excluded it from further analysis.</li>
          <li>Identified special parameter choices (e.g. &nu; = 1/6 for the explicit scheme; specific
              &nu;&ndash;&rho; pairings for the implicit scheme) at which local truncation error
              jumps from second to fourth order due to cancellation of leading error terms.</li>
          <li>Compared total operation count vs. accuracy across three candidate protocols and
              recommended the implicit scheme with &nu; = 1/5, &rho; = 1/12 as the most
              efficient choice for a given accuracy target.</li>
          <li>Verified numerically that the solution converges to the derived long-time asymptotic
              limit as t &rarr; &infin;.</li>
        </ul>

        <div class="catam-figrow">
          <img src="{{ '/assets/img/catam/pde-fig-analytic.png' | relative_url }}" alt="Analytic solution evolution">
          <img src="{{ '/assets/img/catam/pde-fig-error.png' | relative_url }}" alt="Numerical error comparison">
          <img src="{{ '/assets/img/catam/pde-fig-asymptotic.png' | relative_url }}" alt="Convergence to asymptotic limit">
        </div>

        <a class="catam-btn" href="{{ '/assets/pdf/catam-1.3-parabolic-pdes.pdf' | relative_url }}" target="_blank">
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
        <span class="catam-badge">Category</span>
        <h4>Project 2 Title</h4>
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
        <a class="catam-btn" href="{{ '/assets/pdf/catam-2.pdf' | relative_url }}" target="_blank">
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