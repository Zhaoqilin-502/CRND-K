# CRND-K and CRND-D

This repository presents two datasets for controllable railway number character degradation synthesis and recognition: **CRND-Knowledge (CRND-K)** and **CRND-Degraded (CRND-D)**.

## CRND-Knowledge (CRND-K)

CRND-K is a railway number character dataset with morphological knowledge annotations for training and evaluating controllable degradation generation models.

Each sample provides a degraded character, a matched complete glyph, an estimated missing-region mask, and corresponding morphological descriptors. Missing-region masks are constructed through same-class reference retrieval, registration, and multi-reference consistency analysis.

The knowledge annotations contain **14 numerical attributes** organized into five groups:

| Knowledge Group | Dimensions | Description |
|:--|:--:|:--|
| Strength | 1 | Missing-area ratio relative to the complete character foreground |
| Position | 8 | Centroid coordinates and horizontal and vertical regional proportions |
| Connected components | 2 | Component count and largest-component area fraction |
| Continuity | 1 | Local continuity measured through neighborhood occupancy |
| Fragmentation | 2 | Fragmentation score and boundary density |

The formal experimental subset contains **2,774 high-confidence samples**, divided into 2,224 training, 278 validation, and 272 reference samples. Character images and masks are normalized to **64 × 64** pixels.

## CRND-Degraded (CRND-D)

CRND-D is a synthetic railway number degradation dataset generated using **MBdiffusion (MBdiff)**.

Conditioned on complete glyphs and morphological knowledge, MBdiff generates missing-region masks that specify the pixels to be removed from character foregrounds. This process produces degraded characters with varying strengths, locations, and structural patterns.

CRND-D supports data augmentation and downstream recognition experiments, providing synthetic stroke-loss samples for studying recognition performance under challenging degradation conditions.
