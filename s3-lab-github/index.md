---
title: About
heading: Safe, Smart, Sustainable
intro: Materials and systems for energy, aerospace, the built environment and extreme conditions.
---

## About S³ Lab

**S³ Lab — Safe, Smart, Sustainable Materials & Systems** is a research group founded and led by Dr Wei Wang at RMIT University, Melbourne.

The three S's express our approach to materials and systems: **Safe** by improving resistance to fire, thermal hazards and demanding environments; **Smart** by integrating sensing, responsive behaviour and complementary functions; and **Sustainable** by designing for resource efficiency, lower energy use and reduced environmental impact.

We combine materials design, experiments and multiscale modelling to connect material behaviour with system performance. Our research spans battery safety and thermal management, energy-efficient building materials, fire-safe composites, multifunctional protection, and smart textiles and sensing. We also explore lightweight thermal protection and multifunctional materials for aerospace, defence and other extreme environments, drawing on our work in aerogels, fire resistance and electromagnetic shielding.

Across these connected directions, we aim to protect people and infrastructure while supporting lower-carbon technologies and the transition towards net zero.

## Research at a glance

<ul class="research-glance">
{% for theme in site.data.research %}
  <li><a class="glance-link" data-theme="{{ theme.id }}" href="{{ '/research/' | relative_url }}#{{ theme.id }}">{{ theme.title | escape }}</a> — {{ theme.summary | escape }}</li>
{% endfor %}
</ul>

## About Wei

**Dr Wei Wang** is a Lecturer and ARC DECRA Fellow at RMIT University.

For Wei's full biography, academic appointments and research profile, [visit his RMIT webpage](https://www.rmit.edu.au/profiles/w/wei-wang).
