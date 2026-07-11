#  MurJ-Drug-Discovery

> Computational analysis and molecular dynamics study of the bacterial lipid II flippase MurJ (*E. coli*).

**Status:**  Ongoing Research

---

## Overview

This repository presents a computational study of **EcMurJ** (UniProt [P0AF16](https://www.uniprot.org/uniprot/P0AF16)), an essential bacterial lipid II flippase involved in peptidoglycan biosynthesis. MurJ transports lipid-linked peptidoglycan precursors across the cytoplasmic membrane, making it a promising target for antibacterial drug discovery and phage therapy research.

The project focuses on:

- **Structural analysis** of MurJ co-crystal structures (PDB: 9UKV, 9NU4, 9NU5, 9NU8, 6CC4)
- **Molecular dynamics simulations** to characterize conformational dynamics
- **Binding pocket identification** and druggability assessment
- **Computational drug discovery** including molecular docking and virtual screening



## Objectives

- Investigate the structural characteristics of EcMurJ, focusing on transmembrane regions TM2 (39–60), TM4 (100–121), TM7 (188–209), and TM8 (213–234).
- Analyze conformational changes during 100 ns molecular dynamics simulations.
- Identify key conserved residues and potential druggable binding pockets.
- Characterize Chain B interactions with phage proteins and allosteric regulation sites.
- Provide computational evidence to support future antibacterial drug discovery targeting MurJ.

---

## Workflow

```
Protein Structure Preparation
        │
        ▼
  Structural Analysis (5 co-crystal structures)
        │
        ▼
  Binding Pocket Analysis (sub-pocket mapping)
        │
        ▼
  100 ns Molecular Dynamics Simulation (GROMACS)
        │
        ▼
  Trajectory Analysis (RMSD / RMSF / H-bonds / Rg)
        │
        ▼
  Interaction Analysis (PyMOL / PLIP)
        │
        ▼
  Molecular Docking & Virtual Screening (AutoDock Vina)
```

---

## Current Progress

### Structure

- [x] Protein structure preparation (CHARMM-GUI)
- [x] Structural visualization (PyMOL / ChimeraX)
- [x] Co-crystal structure analysis (9UKV, 9NU4, 9NU5, 9NU8, 6CC4)
- [x] Transmembrane region mapping (TM2 / TM4 / TM7 / TM8)
- [x] Conserved residue identification
- [x] Binding pocket analysis — near-end (Z = 78–85 Å) & far-end (Z = 90–100 Å) sub-pockets
- [x] Druggable pocket residue annotation (K46 / R53 / S241 / Q244 / D269 / R270 / E273 / K368)
- [x] Allosteric residue annotation (A59 / F64 / V229 / M233 / Q244 / I248 / I252)

### Molecular Dynamics

- [x] 100 ns molecular dynamics simulation (GROMACS 2021.3, CHARMM36m)
- [x] RMSD analysis (`rmsd_100ns.xvg`)
- [x] RMSF analysis (`rmsf_100ns.xvg`)
- [x] Hydrogen bond analysis — intra-protein & protein-membrane
- [x] Radius of gyration (Rg) analysis (`rg_100ns.xvg`)
- [ ] PCA / free energy landscape (FEL) analysis
- [ ] Solvent accessible surface area (SASA) analysis
- [ ] MM/PBSA free energy calculation

### Drug Discovery

- [x] Docking box determination (AutoDock Vina, large-box screening setup)
- [x] Compound library acquisition (MCE Bioactive, Natural Product libraries)
- [ ] Molecular docking (AutoDock Vina, ~236K compound library)
- [ ] Virtual screening

---

## Research Highlights

- Investigated the structural characteristics of MurJ across 5 co-crystal structures (PDB: 9UKV, 9NU4, 9NU5, 9NU8, 6CC4).
- Identified potential ligand-binding pockets, including near-end (Z = 78–85 Å) and far-end (Z = 90–100 Å) sub-pockets.
- Annotated druggable pocket residues (K46, R53, S241, Q244, D269, R270, E273, K368) and allosteric inhibition residues (A59, F64, V229, M233, Q244, I248, I252).
- Performed 100 ns molecular dynamics simulation of EcMurJ in a POPC bilayer (CHARMM36m force field).
- Established a reproducible computational workflow for MurJ structural analysis and drug discovery.

---

## Repository Structure

```
MurJ-Drug-Discovery/
│
├── docs/            # Project documentation
├── data/            # Metadata and sample files (large datasets not included)
├── figures/         # Figures and illustrations
├── notebooks/       # Jupyter notebooks
├── scripts/         # Analysis scripts
├── results/         # Simulation and analysis results
│   ├── md/          # MD trajectories and analysis
│   └── docking/     # Docking results
├── references/      # Literature and references
├── commands/        # PyMOL / ChimeraX / GROMACS command notes
└── README.md
```

---

## Key Residues

### Druggable Pocket Residues

| Residue | TM Region | Role |
|---------|-----------|------|
| K46     | TM2       | Pocket lining |
| R53     | TM2       | Pocket lining |
| S241    | TM7       | Polar interaction |
| Q244    | TM7       | Allosteric / pocket |
| D269    | TM8       | Salt bridge |
| R270    | TM8       | Salt bridge |
| E273    | TM8       | Charged interaction |
| K368    | —         | Pocket lining |

### Allosteric Inhibition Residues

| Residue | TM Region |
|---------|-----------|
| A59     | TM2       |
| F64     | TM2       |
| V229    | TM8       |
| M233    | TM8       |
| Q244    | TM7       |
| I248    | TM8       |
| I252    | TM8       |

---



## Tools

- **GROMACS 2021.3** — Molecular dynamics simulation
- **CHARMM-GUI** — Membrane protein system building
- **PyMOL** — Structural visualization & analysis
- **ChimeraX** — Structural visualization
- **PLIP** — Protein-ligand interaction profiling
- **AutoDock Vina** — Molecular docking & virtual screening
- **AutoDockTools (ADT)** — Receptor/ligand preparation & grid box setup
- **Open Babel** — Chemical format conversion (SDF → PDBQT)
- **APBS** — Electrostatic surface potential calculation
- **Python** — Data analysis & scripting
  - MDAnalysis, NumPy, Matplotlib, BioPython
- **Jupyter Notebook** — Interactive analysis

---


---

## References

Key references used in this project are listed in the `references/` directory. Primary structural data were obtained from the Protein Data Bank (PDB).

- Kohga H, et al. (2025) *Sci Adv* 11, eady8083.
- PDB entries: [9UKV](https://www.rcsb.org/structure/9UKV), [9NU4](https://www.rcsb.org/structure/9NU4), [9NU5](https://www.rcsb.org/structure/9NU5), [9NU8](https://www.rcsb.org/structure/9NU8), [6CC4](https://www.rcsb.org/structure/6CC4), [5T77](https://www.rcsb.org/structure/5T77)
- UniProt: [P0AF16](https://www.uniprot.org/uniprot/P0AF16)

---

## Author

NJMU Bioinformatics  Student

Interested in Computational Biology, Structural Bioinformatics, and Drug Discovery.

---

## Future Work

- Complete MD trajectory analysis (PCA / FEL, SASA)
- Characterize residue interactions in detail (MM/PBSA)
- Perform molecular docking with AutoDock Vina (large-box screening)
- Conduct virtual screening of ~236K compound library
- Develop reproducible computational workflows for membrane protein drug discovery

---

## License

Licensed under the MIT License.
