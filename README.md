# Wound Imaging Foundation-Model Survey: Gap Map and Failure Mode Catalog

Companion data release for:

> Kh Shafin Farhan, Xiaoyu Zhang, Wei Bo, Alexander Gherardi, Jun Xia, and
> Wenyao Xu, "Foundation Models in Wound Imaging: A Pipeline-Wide Maturity
> Assessment," *IEEE Reviews in Biomedical Engineering* (under review).

Version 1.1. Final search date: 28 July 2026.

## Changes from version 1.0

Version 1.1 matches the submitted manuscript. Applying the FM-track
criterion uniformly (any released, broadly pretrained foundation-model
checkpoint applied to the analysis of a real wound image and central to
the paper's contribution) moved four papers to the FM track (Kiprono 2025,
Busch 2025, Ban 2025, Lucho 2024). Three records first excluded at title
and abstract screening were admitted (Almufadi 2025, Sathya Preiya 2023,
Karim 2025), one included study of rat wounds was excluded as non-human,
and the fairness, external-validation and mitigation-status counts were
re-verified against the source papers. The corpus is 133 studies: 42
FM-track wound papers, 2 FM-based adjacent precedents evaluated on
non-wound imaging, 79 non-FM adjacent papers and 10 text-only entries.

The version 1.0 files (`gap_map_v1.csv`, `failure_mode_catalog_v1.csv`) are
retained unchanged for reference.

## What this release contains

| File | Rows | Description |
|---|---|---|
| `gap_map_v1.1.csv` | 7 | The Gap Map: foundation-model evidence by pipeline step, with maturity level, corpus composition, and verification practice. Corresponds to Table I of the manuscript. |
| `failure_mode_catalog_v1.1.csv` | 31 | The Failure Mode Catalog: wound-specific foundation-model failure modes with mechanism, supporting evidence, and mitigation status. Corresponds to Supplementary Table S10. |

## What this release does not contain

The source publications are not redistributed here. Every study in the
corpus is identified by citation in the manuscript's reference list.
Per-study extraction detail for all 133 included studies is published as
Supplementary Tables S1 through S7 of the manuscript. Records excluded at
full-text assessment appear in Supplementary Table S8, records excluded at
title and abstract in Supplementary Table S9, and the search strings in
Supplementary Table S11.

## `gap_map_v1.1.csv`

One row per pipeline step.

| Column | Description |
|---|---|
| `step` | Pipeline step, in clinical deployment order. |
| `fm_track_papers` | FM-track papers whose primary contribution is at this step (Adaptation Strategy includes the 2 non-wound adjacent precedents). |
| `non_fm_papers` | Adjacent-track papers included as context. |
| `maturity_level` | L0 through L4, the maximum any FM-track paper at that step achieves. |
| `external_validations` | Papers running any external or cross-dataset evaluation (at Deployment, a live real-world test). |
| `step_total_studies` | Denominator for the preceding column. Includes the 10 text-only entries that the FM and non-FM columns exclude. |
| `fairness_audits` | Papers, FM-track or not, reporting race- or skin-tone-stratified performance. |
| `flagship_paper` | The paper setting the step's reported level. |
| `flagship_citekey` | BibTeX key for that paper in the manuscript's reference list. |
| `evidence_vector_tags` | Independent evidence-vector findings for the flagship paper. |

Column totals reconcile to the manuscript: `fm_track_papers` sums to 44,
`non_fm_papers` to 79, and `step_total_studies` to 133.

## `failure_mode_catalog_v1.1.csv`

One row per catalog entry.

| Column | Description |
|---|---|
| `entry` | Permanent entry number. Numbers are never reused or reassigned, so entries are not in step order. |
| `step` | Pipeline step where the mechanism applies, which is not always the step its source paper is tagged to. |
| `failure_mode` | The failure mode in one line. |
| `evidence` | The papers documenting it and what they report. |
| `mitigation_status` | `None` where the source names the problem without testing a fix; `Partial` where it reports an attempted but incomplete mitigation. No entry currently qualifies as Resolved. |
| `mitigation_note` | Qualifying detail on the status assignment, where the source gives one. |

Status distribution: 22 `None`, 9 `Partial`.

Entry numbering is designed to accumulate in the spirit of CWE/CVE
numbering. New entries take the next free integer.

## Citing this release

Cite the manuscript above. If you need to cite the data specifically,
cite this deposit by its DOI.

## License

Creative Commons Attribution 4.0 International (CC BY 4.0). You may
share and adapt this data for any purpose, including commercially,
provided you give appropriate credit to the manuscript cited above.

Full text: https://creativecommons.org/licenses/by/4.0/
