---
layout: page
title: 9-Qubit Shor Code
description: A simple implementation in Python with Qiskit for correcting single qubit errors.
img: assets/img/Qiskit stock image.jpg
importance: 2
category: Personal
giscus_comments: true
---

A simple implementation of the 9-qubit Shor Code in Python with Qiskit. This implementation is useful for illustrating the Shor Code's functionality as well as some basic princicples of quantum error correction. 

The following notebook runs through and verifies the functionality of the python code which can be found in the `ShorCode`  module from the QEC-Codes repository on my GitHub. 

---

{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/9QubitShorCode.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/9QubitShorCode.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}