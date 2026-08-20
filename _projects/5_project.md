---
layout: page
title: CATAM Projects
description: Four Cambridge CATAM projects, each pairing an analytic derivation with a numerical implementation.
img: assets/img/catam.png
importance: 1
category: Academic
permalink: /catam/
---

<div class="catam-projects">

<p>
  CATAM (Computer-Aided Teaching of All Mathematics) is a Cambridge Mathematics course unit in which
  each project poses an open-ended mathematical problem — typically requiring an analytic derivation
  followed by a numerical implementation, error analysis, and discussion of results. Below are four
  projects I completed, each summarised with the problem, my approach and key results, and a link to
  the full write-up.
</p>

<div class="row row-cols-1 row-cols-md-2 g-4 catam-grid">

  <!-- ============================================================ -->
  <!-- PROJECT 1 : Parabolic Partial Differential Equations         -->
  <!-- ============================================================ -->
  <div class="col">
    <div class="card h-100 catam-card">
      <div class="card-body">
        <span class="badge bg-secondary mb-2">Numerical Analysis</span>
        <h4 class="card-title">Parabolic Partial Differential Equations</h4>
        <p class="card-text text-muted">
          Analytic vs. finite-difference solutions of the 1D heat equation with a time-varying boundary condition.
        </p>
        <button class="btn btn-outline-primary btn-sm" type="button"
                data-bs-toggle="collapse" data-bs-target="#catam1" aria-expanded="false" aria-controls="catam1">
          View details
        </button>
      </div>

      <div class="collapse" id="catam1">
        <div class="card-body border-top">

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

          <div class="row g-2 my-3">
            <div class="col-6 col-md-4">
              <img src="{{ '/assets/img/catam/pde-fig-analytic.png' | relative_url }}"
                   class="img-fluid rounded" alt="Analytic solution evolution">
            </div>
            <div class="col-6 col-md-4">
              <img src="{{ '/assets/img/catam/pde-fig-error.png' | relative_url }}"
                   class="img-fluid rounded" alt="Numerical error comparison">
            </div>
            <div class="col-6 col-md-4">
              <img src="{{ '/assets/img/catam/pde-fig-asymptotic.png' | relative_url }}"
                   class="img-fluid rounded" alt="Convergence to asymptotic limit">
            </div>
          </div>

          <a class="btn btn-primary btn-sm"
             href="{{ '/assets/pdf/catam-1.3-parabolic-pdes.pdf' | relative_url }}" target="_blank">
            Download full report (PDF)
          </a>

        </div>
      </div>
    </div>
  </div>

  <!-- ============================================================ -->
  <!-- PROJECT 2 : placeholder — replace title/text/links           -->
  <!-- ============================================================ -->
  <div class="col">
    <div class="card h-100 catam-card">
      <div class="card-body">
        <span class="badge bg-secondary mb-2">Category</span>
        <h4 class="card-title">Project 2 Title</h4>
        <p class="card-text text-muted">One-line description.</p>
        <button class="btn btn-outline-primary btn-sm" type="button"
                data-bs-toggle="collapse" data-bs-target="#catam2" aria-expanded="false" aria-controls="catam2">
          View details
        </button>
      </div>
      <div class="collapse" id="catam2">
        <div class="card-body border-top">
          <h5>The problem</h5>
          <p>Paraphrased problem statement here.</p>
          <h5>Approach &amp; key results</h5>
          <ul>
            <li>Key result 1.</li>
            <li>Key result 2.</li>
          </ul>
          <a class="btn btn-primary btn-sm" href="{{ '/assets/pdf/catam-2.pdf' | relative_url }}" target="_blank">
            Download full report (PDF)
          </a>
        </div>
      </div>
    </div>
  </div>

  <!-- ============================================================ -->
  <!-- PROJECT 3 : placeholder                                      -->
  <!-- ============================================================ -->
  <div class="col">
    <div class="card h-100 catam-card">
      <div class="card-body">
        <span class="badge bg-secondary mb-2">Category</span>
        <h4 class="card-title">Project 3 Title</h4>
        <p class="card-text text-muted">One-line description.</p>
        <button class="btn btn-outline-primary btn-sm" type="button"
                data-bs-toggle="collapse" data-bs-target="#catam3" aria-expanded="false" aria-controls="catam3">
          View details
        </button>
      </div>
      <div class="collapse" id="catam3">
        <div class="card-body border-top">
          <h5>The problem</h5>
          <p>Paraphrased problem statement here.</p>
          <h5>Approach &amp; key results</h5>
          <ul>
            <li>Key result 1.</li>
            <li>Key result 2.</li>
          </ul>
          <a class="btn btn-primary btn-sm" href="{{ '/assets/pdf/catam-3.pdf' | relative_url }}" target="_blank">
            Download full report (PDF)
          </a>
        </div>
      </div>
    </div>
  </div>

  <!-- ============================================================ -->
  <!-- PROJECT 4 : placeholder                                      -->
  <!-- ============================================================ -->
  <div class="col">
    <div class="card h-100 catam-card">
      <div class="card-body">
        <span class="badge bg-secondary mb-2">Category</span>
        <h4 class="card-title">Project 4 Title</h4>
        <p class="card-text text-muted">One-line description.</p>
        <button class="btn btn-outline-primary btn-sm" type="button"
                data-bs-toggle="collapse" data-bs-target="#catam4" aria-expanded="false" aria-controls="catam4">
          View details
        </button>
      </div>
      <div class="collapse" id="catam4">
        <div class="card-body border-top">
          <h5>The problem</h5>
          <p>Paraphrased problem statement here.</p>
          <h5>Approach &amp; key results</h5>
          <ul>
            <li>Key result 1.</li>
            <li>Key result 2.</li>
          </ul>
          <a class="btn btn-primary btn-sm" href="{{ '/assets/pdf/catam-4.pdf' | relative_url }}" target="_blank">
            Download full report (PDF)
          </a>
        </div>
      </div>
    </div>
  </div>

</div>
</div>

<style>
.catam-card .card-title { font-weight: 600; }
.catam-card .btn[aria-expanded="true"]::after { content: " ▲"; }
.catam-card .btn[aria-expanded="false"]::after { content: " ▼"; }
</style>