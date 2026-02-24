---
title: "Duren Lab - Research"
layout: archive
permalink: /research/
author_profile: true
---

{% include base_path %}

## Vision
**We aim to make the regulome a computable system that explains how genomes shape phenotypes.** Biomedicine is entering an inflection point where multimodal and spatial genomics make system-level regulatory modeling both feasible and necessary. We go beyond molecular readouts—markers, pathways, and differential signals—to build mechanistic, system-level models of regulation. Our lab develops element-resolved gene regulatory networks (GRNs) that link cis-regulatory elements, transcription factors, and target genes within cells, and place these networks in tissue context by modeling how cross-cell-type signaling modulates regulatory programs. By combining single-cell, multiomic, and spatial data, we identify driver regulatory mechanisms that underpin disease and generate testable hypotheses about where intervention could restore healthy programs.

---

## Research Pillars

### I. Mechanistic & Element-Resolved GRN Inference
![]({{ site.url }}{{ site.baseurl }}/images/respic/summary.png){: style="width: 75%; float: none; border: 10px"}
We develop algorithms that model the physical and functional coupling between chromatin accessibility and gene expression, moving beyond simple correlations to resolve regulatory logic at the level of individual *cis*-elements and transcription factors. Our approach treats the genome not as a static map, but as a dynamic, coupled system.

**Key Frameworks:** **LINGER** (Atlas-informed regulatory learning) and **scREG** (Cis-regulatory potential modeling).

![]({{ site.url }}{{ site.baseurl }}/respic/summary.png){: style="width: 50%; float: right; margin-left: 20px; border: 1px solid #eee; border-radius: 8px;"}

<div style="clear: both;"></div>

---

### II. Regulatory Intelligence Across Technology Eras
We create "reusable" regulatory knowledge by developing frameworks that adapt pre-trained regulatory priors to new datasets. This bridges the gap between bulk, single-cell multiome, and RNA-only assays, enabling high-fidelity inference even when paired data is missing or noisy across changing experimental designs.

**Key Frameworks:** **REGA** (RNA-only regulatory inference) and **CoupledNMF** (Unpaired modality integration).

![]({{ site.url }}{{ site.baseurl }}/images/integration.PNG){: style="width: 50%; float: left; margin-right: 20px; border: 1px solid #eee; border-radius: 8px;"}

<div style="clear: both;"></div>

---

### III. Spatial Regulatory Landscapes & Cell-Cell Communication
We place GRNs in their native tissue context to study how spatial organization and extracellular signaling (ligand-receptor interactions) rewire intracellular regulatory programs. By modeling cross-cell-type signaling, we understand how the tissue environment modulates gene expression.

**Key Frameworks:** **ISON** (Spatial GRN inference) and **Spatial-Rewiring** models.

![]({{ site.url }}{{ site.baseurl }}/images/spatial.PNG){: style="width: 50%; float: right; margin-left: 20px; border: 1px solid #eee; border-radius: 8px;"}

<div style="clear: both;"></div>

---

### IV. Regulatory Rewiring in Disease & Perturbations
We treat genetic variants, pharmacological treatments, and environmental stressors as "system-level rewiring events." Our goal is to quantitatively predict how these factors shift regulatory programs and identify where intervention could restore healthy states.

**Key Frameworks:** **sc-compReg** (Comparative GRN analysis) and **Reg-Variants** (Non-coding variant prioritization).

![]({{ site.url }}{{ site.baseurl }}/images/disease.PNG){: style="width: 50%; float: left; margin-right: 20px; border: 1px solid #eee; border-radius: 8px;"}

<div style="clear: both;"></div>

# Research questions
<iframe width="560" height="315" src="https://www.youtube.com/embed/RT10AizQz4Y?si=EVkbdcQ44EN-5euZ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
