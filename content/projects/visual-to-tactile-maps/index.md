---
title: 'From Visual Maps to Tactile Maps: A Perceptually Grounded Approach to Semi-Automatic Transcription of Educational Thematic Maps for Blind and Low-Vision Individuals'
date: 2026-09-30
summary: 'A human-in-the-loop visual computing system for transforming raster educational thematic maps into perceptually grounded tactile and hybrid maps.'
tags:
  - Tactile Maps
  - Accessibility
  - Blind and Low-Vision
  - Educational Maps
  - Visual Computing
share: false
image:
  caption: 'Overview of the semi-automatic transcription workflow and its perceptually grounded pattern-assignment component.'
  focal_point: Center
  preview_only: false
---

Educational thematic maps communicate spatial patterns, relationships, and structure, but they are often inaccessible to blind and low-vision learners. Converting them into tactile graphics is still a largely manual process that requires specialist knowledge and substantial time—especially when the source is a raster image from a textbook rather than structured geospatial data.

This project investigates a human-in-the-loop visual computing pipeline that supports the semi-automatic transcription of visual thematic maps into tactile maps. The system combines multimodal artificial intelligence, computer vision, geometric processing, and findings from tactile-perception studies. It is designed to assist expert transcribers, not replace their judgment.

## At a glance

- **Input:** a raster image of an educational thematic map
- **Output:** an editable tactile-only or hybrid-color map with a Braille-ready legend and labels
- **Current production method:** swell paper
- **Core principle:** automate repetitive processing while keeping a human reviewer in control

## How the system works

1. **Understand the visual map.** A multimodal model identifies the map's topic, semantic structure, and likely relationships between visual elements.
2. **Detect and reconstruct its content.** Computer-vision and text-recognition methods locate the map, legend, labels, colors, and thematic regions.
3. **Simplify the geometry for touch.** Regions are segmented and converted into simplified geometry while preserving the topology and spatial relationships needed to interpret the map.
4. **Assign perceptually distinct tactile patterns.** Pattern selection considers which regions touch, so neighboring areas receive patterns with strongly distinguishable transitions.
5. **Review and export.** A transcriber can correct intermediate results, edit labels and legends, and produce either a tactile-only version or a hybrid visual-tactile version for low-vision readers.

## Perceptually grounded pattern assignment

The pattern-assignment stage is informed by empirical work on tactile similarity and transition saliency. We assembled an eight-pattern set using tactile-graphics guidelines, practitioner input, and an analysis of 240 existing tactile maps. In an initial study, 17 blindfolded sighted participants completed free-sorting and pairwise transition-comparison tasks. A follow-up study involved six blind participants and one participant with low vision.

Multidimensional scaling and stochastic triplet embedding revealed a consistent global organization of the patterns into four perceptual clusters. The transcription system uses these results together with a class-adjacency graph: it selects no more than one pattern from each perceptual cluster and seeks an assignment that maximizes the minimum perceptual distance between adjacent map regions. This makes the method sensitive to local boundaries—the transitions a reader actually encounters while exploring a tactile map.

## Human control and accessible output

The workflow includes review points after interpretation, detection, segmentation, simplification, and pattern assignment. This supports correction when a source map is ambiguous and preserves the expertise of tactile-graphics professionals. The prototype currently targets low-cost swell-paper production and can retain carefully selected color information for readers with residual vision.

## Current status

The research prototype implements the main stages of the pipeline. Its design has been informed by a 30-hour tactile-graphics transcription workshop at INSEI, observation of professional production practice, tactile-reading workshops, and collaboration with specialists in visual impairment and relief-image adaptation. The tactile-pattern study has been published at EuroHaptics 2026.

The next evaluation phase will examine the complete workflow with tactile-map creators and educators, followed by studies of the resulting maps with blind and low-vision readers.

## Resources

- [Source code and development repository](https://github.com/n-bagheri/mapgen-thematic)
- [Prototype demonstration](https://nuage.lix.polytechnique.fr/index.php/s/fPDrse7dNFeEYej)
- [EuroHaptics 2026 paper on tactile dissimilarity and transition saliency](https://link.springer.com/chapter/10.1007/978-3-032-32350-7_32)

## Project team

{{< team-grid >}}
{{< team-card initials="NB" name="Nasim Bagheri" url="/" role="Project lead · PhD researcher" description="Research design, perceptual studies, prototype development, and project coordination." >}}
{{< team-card initials="PM" name="Pooran Memari" url="https://www.lix.polytechnique.fr/~memari/" role="PhD supervisor" description="Visual computing, computational geometry, and geometry processing." >}}
{{< team-card initials="PM" name="Panos Mavros" url="https://perso.telecom-paristech.fr/pmavros/" role="PhD supervisor" description="Design, spatial cognition, and user-experience research." >}}
{{< team-card initials="GB" name="Gilles Bailly" url="https://hci.isir.upmc.fr/gilles-bailly/" role="Research collaborator" description="Human-computer interaction and accessibility." >}}
{{< team-card initials="DG" name="David Gueorguiev" url="https://www.isir.upmc.fr/personnel/gueorguiev/" role="Research collaborator" description="Haptics, touch, and tactile perception." >}}
{{< team-card initials="MG" name="Mathieu Gaborit" url="https://www.insei.fr/recherche/mathieu-gaborit" role="Domain expert · INSEI collaborator" description="Tactile graphics, relief-image adaptation, and visual-impairment education." >}}
{{< /team-grid >}}

## Collaboration and stakeholder engagement

INSEI is the central application partner for the project. The work is also informed by exchanges with organizations and specialists involved in accessible education and tactile-graphics production, including Association Valentin Haüy, INJA, ATAF, and Dedicon.
