---
layout: page
title: BB84 QKD
description: A modular implementation in Python with Qiskit, including intercept-resend eavesdropper analysis.
img: assets/img/Qiskit stock image.jpg
importance: 2
category: Personal
related_publications: false
---

This project uses the `bb84`, `channel` and `eavesdropping` modules from `/qkdcode` in the QKD-Protocols repository on my GitHub. The theoretical elements of this project were supported by my lecture notes from "Quantum Information & Computation" at Cambridge and Nielsen & Chuang's classic textbook.

{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/bb84.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/bb84.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}