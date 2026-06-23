# Ligand RBFE

Example repo for setting up ligand RBFE simulations. 

For theory, have a look at [this paper](https://livecomsjournal.org/index.php/livecoms/article/view/v2i1e18378)

This tutorial is based on the [BioSimSpace Tutorials](https://github.com/OpenBioSim/biosimspace_tutorials/tree/main/04_fep/02_RBFE)

# Prerequisites 

## 1. Install required software

**1. Install `mamba` [here](https://mamba.readthedocs.io/en/latest/installation/mamba-installation.html) (preferred) or `conda`[here](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)**

**2. Create a clean environment:**

```
conda create -n obss
```

**3. Install BioSimSpace:**

```
conda activate obss
mamba install -c openbiosim biosimspace
```

4. **Make sure Amber is installed.**

You can install Amber [here](https://ambermd.org/Installation.php)

## 2. System setup

1. **Starting structures**

- Start with a prepared protein (or other target) system: 
    - Choose a good-quality starting structure (ideally with at least one ligand bound pose), 
    - Determine the protonation states of amino acid side chains, 
    - Fix missing residues/chains
    - And determine the protonation states of your ligands.
- For a ligand series, it's best to start from the coordinates of a single bound pose of a ligand to which all the other ligands are aligned 
- Decide if you want to include protein terminal residues, and how you deal with co-factors such as metals. You can use [meze](https://github.com/meyresearch/meze/tree/main) to parameterise zinc-metalloenzymes. 

2. **Directory structure**

The data in this tutorial is structured as: 

```
data/
|---- inputs/
|    |---- ligands/
|    |    |---- ligand_1.sdf           Input ligand SDF file for ligand 1
|    |    |---- ligand_2.sdf           Input ligand SDF file for ligand 2
|    |---- protein/
|    |    |---- kpc2.prepared.pdb      Prepared protein PDB file
```

It's recommended you follow the same structure. 

3. **Parameterisation**

If you have any non-standard residues or ligands, it's recommended that you use e.g. `leap` in `ambertools` for parameterisation. You can then load in the topology (`prmtop`/`prm7`) and coordinate (`inpcrd`/`rst7`) files to BioSimSpace. 

BioSimSpace uses GROMACS for solvation by default, so if you want to solvate your systems with Amber you can do so at the parameterisation step. 

## 3. Prepare network

You can create the perturbation network with the Jupyter notebook [`01_setup_network.ipynb`](https://github.com/jasmin-guven/ligand_rbfe/blob/95e8f274b2a02c7b642376abb86d2a76b8ca9e93/01_setup_network.ipynb).

This will create three more folders in the inputs directory: 

```
data/
|---- inputs/
|    |---- ligands/
|    |    |---- ligand_1.sdf           Input ligand SDF file for ligand 1
|    |    |---- ligand_2.sdf           Input ligand SDF file for ligand 2
|    |    |---- images/                Directory created by lomap
|    |    |    |---- network.png       Image of the network    
|    |    |---- inputs/                Directory created by lomap
|    |    |    |---- 000_ligand_1.sdf  Input files processed by lomap
|    |    |---- outputs/               Directory created by lomap
|    |    |    |---- network.csv       Network saved a csv file
|    |    |    |---- lomap_score_with_connection.txt   Lomap output
|    |    |    |---- lomap.pickle      Lomap output
|    |    |    |---- lomap.txt         Lomap output
|    |---- protein/
|    |    |---- kpc2.prepared.pdb      Prepared protein PDB file
```

## 4. Prepare unbound stage

## 5. Prepare bound stage

## 6. Create single topology

## 7. Prepare RBFE 

## 8. Run RBFE

## 9. Analyse

