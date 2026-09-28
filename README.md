# scCNVmap

scCNVmap analyzes copy-number variation (CNV) in single-cell RNA sequencing, single-cell ATAC sequencing, and spatial transcriptomics data. This repository distributes prebuilt release packages together with small test fixtures and tutorials; it does not contain the application source code.

## Download and run

Download the release package for your operating system from [GitHub Releases](https://github.com/diogobaird/scCNVmap/releases). Extract the archive, make the `scCNVmap` executable available on your `PATH`, and check the available options with:

```sh
scCNVmap --help
```

Release assets are published separately from the files on the `main` branch. If the Releases page has no assets yet, a downloadable binary has not been published.

## Test data

`test_data/` contains small synthetic fixtures for smoke testing and format checks:

- `scrna/`: gene-by-cell counts, genomic gene order, and cell annotations.
- `scatac/`: compressed fragment records and cell annotations.
- `spatial/`: gene-by-spot counts, genomic gene order, annotations, and spot coordinates.

These examples contain invented values and identifiers. They are not real biological or patient data and are not an accuracy benchmark. Do not use the fixtures to support biological conclusions.

All tables are tab-separated. Count matrices have genes or genomic features in rows and cells or spots in columns. Gene-order files provide `gene`, `chr`, `start`, and `end`; annotation identifiers must match the corresponding matrix columns or fragment barcodes.

## Tutorials

The notebooks cover scRNA-seq, scATAC-seq, and spatial transcriptomics. They demonstrate the input contracts, CLI invocation, expected output tables, and figure inspection. The bundled result fixtures are explicitly marked as tutorial examples and are not presented as results inferred by the executable.

- [scRNA-seq tutorial](tutorials/scCNVmap_scRNA_tutorial.ipynb)
- [scATAC-seq tutorial](tutorials/scCNVmap_scATAC_tutorial.ipynb)
- [Spatial transcriptomics tutorial](tutorials/scCNVmap_ST_tutorial.ipynb)
- [Tutorial overview](tutorials/README.md)

Install the notebook dependencies with:

```sh
python -m pip install -r tutorials/requirements.txt
```

Public datasets mentioned in the tutorials are not redistributed here. Obtain them from their original repositories and follow the providers' access terms and citation requirements.

## License

The README, tutorials, and bundled repository fixtures are distributed under the [MIT License](LICENSE). The scCNVmap binary release retains its BSD 3-Clause license; see the `LICENSE` file included in each release archive.
