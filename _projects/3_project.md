---
layout: page
title: Bell's Theorem: Hidden Variables vs. Inherent Indeterminism
description: An investigation into an instance of Bell's Theorem including an experimental verification using results from real hardware through IBM's Quantum Platform.
img: assets/img/Qiskit stock image.jpg
importance: 3
category: Personal
---

In the case of an entangled electron-positron pair with anti-aligned spins, are the spins described by some hidden variables unknown to us or are the spins actually undetermined by nature itself prior to measurement? This can, in fact, be determined experimentally by considering the statistics of multiple measurements. 

In this project, I investigate this particular instance of Bell's Theorem and verify it using the results from a suitable experiment on real IBM hardware, access to which was made possible by their Quantum Platform. 

---

{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/BellsTheorem.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/BellsTheorem.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}