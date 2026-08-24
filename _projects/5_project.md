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
  The CATAM (Computer-Aided Teaching of All Mathematics) projects are a modular coursework component of the Cambridge Mathematics tripos, each centred around a computer-aided investigation into a mathematics problem, which may itself be analytically intractable. Below are the four projects I completed in my third year, each with a summary of the project, key results, and a link to the full write-up.
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
          <li>Derived the Fourier sine series solution and its long-time asymptotic limit.</li>
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
        <h5>Selected Figures:</h5>
        <div class="catam-figrow">
        <figure class="catam-fig">
            <figcaption>The analytic Fourier series solution for 𝜃(𝑥) at various times, each found by summing the first 100 terms</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_analytic.jpg' | relative_url }}" alt="Analytic solution evolution">
        </figure>
        <figure class="catam-fig">
            <figcaption>Plots of log(Computational time 𝑇) against log(Numerical step length 𝑁) for each protocol evaluated at 𝑡 = 0.5, 1 & 2</figcaption>
            <img src="{{ '/assets/img/catam_PDEs_error.jpg' | relative_url }}" alt="Numerical error comparison">
        </figure>
        <figure class="catam-fig">
            <figcaption>The reduced temperature function 𝜙(𝑥, 𝑡) found numerically with protocol 2 and the asymptotic limit of the analytic solution for 𝜙 found in question 1</figcaption>
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
          A Padé approximant of a function \(f(x)\) is a rational function whose own power series matches \(f(x)\)'s to the highest possible order. Given a power series \(f(x) = \sum c_k x^k\), we construct the \([L,M]\) Padé approximant \(R_{L,M}(x)\) by solving two linear systems, one for its numerator and denominator coefficients respectively. Applying this to \(f_1(x) = (1+x)^{1/2}\) and \(f_2(x) = \int_0^\infty e^{-t}(1+xt)^{-1}dt\), we compare rate of convergence, domain of convergence and accuracy against the truncated power series. Finally, we investigate the pole/zero structure of the Padé approximants for six test functions and relate these poles/zeros to branch cuts and singularities of the approximated function.
        </p>
        <h5>Key Results:</h5>
        <ul>
          <li>Wrote a general-purpose MATLAB routine to solve the Padé linear systems with optional iterative
              improvement for numerical accuracy.</li>
          <li>Derived the power series for \((1+x)^{1/2}\) and showed the partial sum error in estimating \(\sqrt{2}\)
              decays as a power law.</li>
          <li>Showed that the diagonal Padé approximant \(R_{L,L}(1)\) converges to \(\sqrt{2}\) exponentially in \(L\),
              reaching the computer double-precision floor (\(\sim10^{-16}\)) by \(L=10\), vastly outperforming the power series  which would need \(\sim3\times10^9\) terms for comparable accuracy.</li>
          <li>Demonstrated that the approximant remains valid for \(1 < x \le 100\) whereas the power series diverges, and 
              quantified how the exponential convergence rate in \(L\) degrades with \(x\).</li>
          <li>Mapped the poles and zeros of the Padé approximants of six functions, showing that for functions with branch
              points these cluster along the branch cut. Additionally indentified transient "defect" pairs of close proximity poles and zeros for certain approximants, which did not correspond to features of the approximated function.</li>
        </ul>
        <h5>Selected Figures:</h5>
        <div class="catam-figrow">
        <figure class="catam-fig">
            <figcaption>Padé approximant estimates for \(f_1(x)\) for 𝐿 = 1,2,4,6,8 & 10.</figcaption>
            <img src="{{ '/assets/img/catam_Pade_f1estimates.jpg' | relative_url }}" alt="Analytic solution evolution">
        </figure>
        <figure class="catam-fig">
            <figcaption>Poles and zeros (including defects) of the Padé approximant for \(f_6(x)\), clearly lying along a well defined curve between two branch points.</figcaption>
            <img src="{{ '/assets/img/catam_Pade_f6poleszeros.jpg' | relative_url }}" alt="Numerical error comparison">
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
        <span class="catam-badge">Waves</span>
        <h4>Phase and Group Velocity</h4>
        <p class="catam-subtitle">Dispersive wave propagation in the Klein–Gordon equation, from stationary-phase asymptotics to finite-difference simulation.</p>
      </div>
      <span class="catam-chevron" aria-hidden="true">&#9662;</span>
    </button>
    <div class="catam-tile-body">
      <div class="catam-tile-body-inner">
        <h5>The Project:</h5>
        <p>We first consider the Klein–Gordon equation \(u_{tt} - c_0^2 u_{xx} = -q^2 u\). Solving by Fourier transform to obtain the dispersion relation \(\Omega(k) = \sqrt{q^2+k^2}\), we then apply the method of stationary phase to derive a large-\(t\) asymptotic approximation revealing the physical meaning of group velocity. We then build and validate a finite-difference scheme to solve the initial-value problem numerically, and extend it to a "signalling problem" where a boundary is driven at a fixed frequency, examining how the resulting wave packet's shape depends on that frequency relative to \(q\).</p>
        <h5>Key Results:</h5>
        <ul>
          <li>Derived the analytic integral solution via Fourier transform and showed that phase velocity \(\Omega(k)/k\) 
              always exceeds group velocity \(\Omega'(k)\), both tending to 1 as \(|k| \to \infty\).</li>
          <li>Applied method of stationary-phase to obtain a closed-form large-\(t\) asymptotic, explicitly identifying 
              the stationary wavenumber \(k_0(x/t)\) and interpreting the result as an envelope (moving at group velocity) modulating an oscillation (moving at phase velocity).</li>
          <li>Implemented a centred finite-difference scheme in MATLAB and established empirically that accuracy is 
              governed by \(\Delta x\) while stability requires \(\Delta t/\Delta x \le 1\).</li>
          <li>Verified agreement between the numerical solution and the stationary-phase asymptotic away from the 
              wavefront, for both non-dispersive (\(q=0\)) and dispersive (\(q=1\)) regimes.</li>
          <li>Ran the signalling problem for driving frequencies above and below \(q\), showing wave peaks migrate forward
              through the envelope (phase velocity exceeding group velocity) with wavelength shortening near the leading edge, consistent with the dispersion relation derived in question 1.</li>
        </ul>
        <h5>Selected Figures:</h5>
        <div class="catam-figrow">
        <figure class="catam-fig">
            <figcaption>Numerical solution with Δ𝑥 = Δ𝑡 = 0.005 and stationary-phase approximation overlaid for various \|(t\) (𝑞 = 1).</figcaption>
            <img src="{{ '/assets/img/catam_PhaseGroup_asymptotic.jpg' | relative_url }}" alt="Analytic solution evolution">
        </figure>
        <figure class="catam-fig">
            <figcaption>Numerical solution for 𝑞 = 1 & \(𝜔_0 = 1.1\) with Δ𝑥 = Δ𝑡 = 0.005. Arrow indicates movement of individual wavefront forwards through wavepacket.</figcaption>
            <img src="{{ '/assets/img/catam_PhaseGroup_dispersion.jpg' | relative_url }}" alt="Numerical error comparison">
        </figure>
        <a class="catam-btn" href="{{ '/assets/pdf/catam_2.10_PhaseGroupVelocity.pdf' | relative_url }}" target="_blank">
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
        <span class="catam-badge">Waves</span>
        <h4>Soliton Solutions of the KdV Equation</h4>
        <p class="catam-subtitle">Numerical simulation of soliton dynamics via a leap-frog finite-difference scheme, from single-soliton solution validation to nonlinear wave steepening and multiple soliton emergence.</p>
      </div>
      <span class="catam-chevron" aria-hidden="true">&#9662;</span>
    </button>
    <div class="catam-tile-body">
      <div class="catam-tile-body-inner">
        <h5>The Project:</h5>
        <p>Verify analytically that the \(\text{sech}^2\)-profile travelling wave solves the Korteweg–de Vries equation \(u_t + uu_x + \delta^2 u_{xxx} = 0\), and prove mass and energy are conserved under periodic boundary conditions. Implement the Zabusky–Kruskal leap-frog finite-difference scheme (deriving its stability condition and devising a special first-step method), then use it to study two-soliton interactions and the evolution of a smooth sinusoidal initial condition into a soliton train, driven by the competition between nonlinear steepening and dispersion.</p>
        <h5>Key Results:</h5>
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
    flex: 0 1 450px;
    max-width: 450px;
    margin: 0;
  }

  .catam-fig figcaption {
    font-size: 0.8rem;
    font-weight: 400;
    opacity: 0.75;
    margin-bottom: 0.35rem;
  }

  .catam-fig img {
    display: block;
    width: 100%;
    max-width: 450px;
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