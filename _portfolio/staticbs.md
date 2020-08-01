---
title: "Static Electromagnetic Simulator"
excerpt: "Ginger Gulp design system including logo mark, website design, and branding applications."
header:
  # image: /assets/images/16-bit-dac/irled_micro_display_overview.png
  teaser: assets/images/staticbs/regular_octagon_helmholtz_71.53mm_radius.png
sidebar:
  - title: "Role"
    image: http://placehold.it/350x250
    image_alt: "logo"
    text: "Electrical Engineer"
  - title: "Responsibilities"
    text: "Determine why current design doesn't work."
---

static-bs
Is a simple 3D electro-magnetostatic biot-savart solving simulator written in python. I wrote this simulator for some research involving detecting the direction of flow of sea water with a static magnetic field. Charged particles in the water traveled through the magnetic field and caused a corresponding voltage gradient. Plates on a PCB board probed the voltage gradient and determined the direction of flow for the sea water. To my knowledge this has never been done before. Currently, I am writing a journal paper about this technique.

Static-bs works by creating line segments of current and then adding up the cumulative effects of the different current segments at the defined observation points. The code is open source and available on my [github](http://www.github.com/grungy/static-bs).

---

## What questions can static-bs answer? ##
Static-bs can answer questions like these:

- What is the B field at a specific point for a coil of wire without having to use a large volume of points like a finite element solver?
- What does that 3D field look like?
- How does the B field change if I have a bunch of coils oriented in a bunch of different ways?
- What is the electric field if I have charged particles moving through the B field?
- What is the voltage field I see from this electric field?

## What is static-bs not good at doing? ## 
- Evaluating a large number of points or a lot of line segments quickly

## Output examples ## 
B field plot of two regular octagons with a radius of 71.53mm in Helmholtz coil configuration

{% capture fig_img %}
![Alt]({{ '/assets/images/staticbs/regular_octagon_helmholtz_71.53mm_radius.png' | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption></figcaption>
</figure>

E field plot of two regular octagons with a radius of 71.53mm in a Helmholtz coil configuration and a fluid moving uniformly in the x direction at 1cm / s

{% capture fig_img %}
![Alt]({{ '/assets/images/staticbs/regular_octagon_helmholtz_71.53mm_radius_e_field.png' | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption></figcaption>
</figure>