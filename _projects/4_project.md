---
layout: page
title: Quantum Algorithms In Qiskit
description: Implementation of Grover's algorithm and the Period-Finding algorithm using Qiskit, with results from real hardware through IBM's Quantum Platform 
img: assets/img/Qiskit stock image.jpg
importance: 4
category: Peronal
---

In these two short projects I outline the theory behind two classic quantum algorithms - Grover's search algorithm and the Period-Finding algorithm - before implementing these using Qiskit and running them on real hardware through IBM's Quantum Platform.

The theoretical background for these algorithms was supported by my lecture notes from “Quantum Information & Computation” at Cambridge.

---

{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/GroversAlgorithm.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/GroversAlgorithm.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/ShorsAlgorithm.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/ShorsAlgorithm.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}
