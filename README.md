Mathematica Code for Creating 3D Diffusion Network
==
This Mathematica code was developed to assist in the calculation of 3D ion diffusion networks within complex structures. For detailed methodology and background, please refer to the following paper:
L. Wang and G. Luo, Exploration of Zeolites as High-Performance Electrode Protective Layers for Alkali-Metal Batteries, ACS Applied Materials & Interfaces, DOI: 10.1021/acsami.4c21152.

Usage
==
Requirements
==
The Mathematica code (3D_Diffusion_Network.nb) was written and tested using Mathematica 14 on macOS.
When running on Windows, ensure to replace the path separator / with \\ in the code to avoid path issues.

Execution Instructions
==
Follow the steps below to run the code:

A. VASP Geometry Optimization
==
Navigate to the directory zeolites/XXX_XX/1_zeolite_GeoOpt.
Perform a VASP geometry optimization for the pure zeolite structure.

B. Set Up Directories and Initial Parameters
==
Using the Mathematica code, initialize the following directory structure and create the required folders:

2_quick_GeoOpt: Perform a quick optimization by relaxing only the alkali ion positions.
3_normal_GeoOpt: Fully optimize the structure.
4_IF_GeoOpt: Fully optimize both the initial and final-state structures for the cNEB calculation.
5_cNEB_Opt: Perform the cNEB calculation.
6_3D_network: Generate the 3D diffusion network.

C. Quick Screening of Sampling Sites
==
Use the Mathematica code to create POSCAR files with alkali ions placed at inequivalent sampling sites. These files will be saved under the 2_quick_GeoOpt folder. This step is designed for a quick screening of sampling sites, with only the alkali ion positions being relaxed.

D. DFT Calculation for Quick Optimization
==
Run DFT calculations in the 2_quick_GeoOpt folder.
Use the Mathematica code to identify inequivalent sampling sites from the optimized results.
Prepare POSCAR files for fully relaxed DFT calculations, which will be saved under the 3_normal_GeoOpt folder.

E. DFT Calculation for Full Optimization
==
Run DFT calculations in the 3_normal_GeoOpt folder.
Use the Mathematica code to identify inequivalent sampling sites from the optimized results and determine adsorption sites for the cNEB calculations.
Note: These adsorption sites should be re-optimized for reliability.
The files will be saved under the 4_IF_GeoOpt folder.

F. Initial and Final State Collection for cNEB
==
Run DFT calculations in the 4_IF_GeoOpt folder.
Use the Mathematica code to collect the structures of the initial and final states for the cNEB calculations.
The files will be saved in the 5_cNEB_Opt folder.

G. cNEB Calculation
==
Complete the cNEB calculations in the 5_cNEB_Opt folder.
Use the Mathematica code to collect and compile the energy data from these calculations.
An Excel file (energy_XXX_XX.xlsx) will be saved in the zeolites/XXX_XX/ directory.

H. Generate 3D Diffusion Network
==
Using the compiled energy data and other structural information, run the Mathematica code to generate a 3D diffusion network.
The output file (dump_XXX-traj.xyz) will be saved in the 6_3D_network folder.
This file can be visualized using OVITO.

Example Data
==
An example dataset is provided in the zeolites/EDI_Li folder for testing purposes.
