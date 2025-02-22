Mathematica Code for Creating 3D Diffusion Network
==
This Mathematica code was developed to assist in the DFT calculations of 3D networks for ion diffusion within complex structures, such as alkali ion diffusion in zeolites. For detailed methodology and background, please refer to the following paper:
L. Wang and G. Luo, Exploration of Zeolites as High-Performance Electrode Protective Layers for Alkali-Metal Batteries, ACS Applied Materials & Interfaces, DOI: 10.1021/acsami.4c21152.

Requirements
==
The Mathematica code was written and tested using Mathematica 14 on macOS.
When running on Windows, ensure to replace the path separator "/" with "\\" in the code to avoid path issues.

Execution Instructions
==
Follow the steps below to run the code:

A. DFT Optimization for Pure System without Adsorbed Species
=
Navigate to the directory zeolites/XXX_XX/1_zeolite_GeoOpt.
Perform a VASP geometry optimization for a pure structure.

B. Set Up Initial Parameters and Create Required Folders
==
Use the Mathematica code to set up the initial parameters and create the required folders:

2_quick_GeoOpt: for quick geometrical optimizations by relaxing only the positions of diffusion species.

3_normal_GeoOpt: for fully geometrical optimizations.

4_IF_GeoOpt: for fully geometrical optimizations of the initial and final-state structures for cNEB calculations.

5_cNEB_Opt: for cNEB calculations.

6_3D_network: for generation of 3D diffusion network.

C. Screening of Sampling Sites
==
Use the Mathematica code to create POSCAR files with diffusion species placed at inequivalent sampling sites. These files will be saved under the 2_quick_GeoOpt folder.

D. Quick DFT Optimization
==
Run DFT calculations in the 2_quick_GeoOpt folder. This step is designed for a quick screening of sampling sites, with only the diffusion species positions being relaxed.
Use the Mathematica code to identify inequivalent sampling sites from the optimized results.
Prepare POSCAR files for fully DFT optimizations, which will be saved under the 3_normal_GeoOpt folder.

E. Run Fully DFT Optimization and Prepare Structural Files for Initial and Final states 
==
Run DFT calculations in the 3_normal_GeoOpt folder.
Use the Mathematica code to identify inequivalent sampling sites from the optimized results and determine adsorption sites for the cNEB calculations.
Currently, these initial and final-state sites for cNEB calculations need to be re-optimized to ensure reliability.
The files will be saved under the 4_IF_GeoOpt folder.

F. Run DFT Optimization for the Initial and Final States, and Prepare Files for cNEB Calculations
==
Run DFT calculations in the 4_IF_GeoOpt folder.
Use the Mathematica code to prepare the structures of the initial and final states for the cNEB calculations.
The files will be saved in the 5_cNEB_Opt folder.

G. Run cNEB Calculations and Collect Energy Data
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
An example is provided in the zeolites/EDI_Li folder for testing purposes.
