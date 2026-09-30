---
title: ''
summary: ''
date: 2026-09-09
type: landing

sections:
  - block: resume-biography-3
    content:
      username: me
      text: ''
      headings:
        about: Research Profile
        education: Education
        interests: Research Interests
    design:
      background:
        gradient_mesh:
          enable: true
      banner:
        filename: tactile-research-banner.jpg
      name:
        size: md
      avatar:
        size: medium
        shape: circle
  - block: markdown
    content:
      title: 'Research'
      text: |-
        My research sits at the intersection of accessible visual computing, tactile perception, and human-computer interaction. I investigate how tactile graphics can communicate visual and spatial information clearly, and how perceptually grounded computational methods can support the semi-automatic creation of educational tactile maps for blind and low-vision learners.
    design:
      columns: '1'
  - block: collection
    id: papers
    content:
      title: Selected Publications
      filters:
        folders:
          - publications
        featured_only: true
    design:
      view: publication-details
---
