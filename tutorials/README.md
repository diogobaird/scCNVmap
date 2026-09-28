# scCNVmap tutorials

These notebooks open with a visible, deterministic result-format fixture: the command, validation log, result tables, article-level PNG and provenance are already shown. The fixture is explicitly labelled and is not a scCNVmap inference result.

To run your own data:

1. Keep `USE_DEMO = False` and replace the input paths.
2. Validate cell/spot IDs, gene-order columns, genomic coordinates and annotation columns before inference.
3. Install `scCNVmap` on `PATH`, run the CLI cell, and keep the complete stdout/stderr log.
4. Run the article-grade renderer cell on the exported result tables.
5. Use the generated SVG/PDF/PNG/TIFF and source-data manifest in the manuscript package.

If `USE_DEMO=True` and no executable is installed, the notebook uses `demo_results/` only to demonstrate the output contract and figure rendering. If `USE_DEMO=False`, a missing executable is an error.

The renderer writes editable SVG/PDF, 300 dpi PNG, 600 dpi LZW TIFF, source-data tables, metadata and a SHA-256 manifest. The article figures therefore show reported HMM states, intervals and predictions rather than a count-matrix surrogate.

Input contracts:

- scRNA: tab-separated counts with genes as rows and cells as columns; `gene_order.tsv` with `gene`, `chr`, `start`, `end`; annotations with `cell`, `group`, `role`.
- scATAC: five-column `fragments.tsv.gz` with chromosome, start, end, cell barcode and count; annotations with `cell`, `role`.
- ST: counts plus `spatial_coords.tsv` (`spot`, `x`, `y`), annotations (`spot`, `group`, `role`) and gene order (`gene`, `chr`, `start`, `end`).

Figures are descriptive outputs. Keep the complete source tables, run manifest, parameter settings and independent truth definition with any manuscript figure. A heatmap is not an accuracy estimate, and cells/spots are not biological replicates.
