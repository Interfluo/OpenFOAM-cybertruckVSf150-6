# OpenFOAM-pisoFoam-LES-cybertruckVSf150-6

This Repository contains the files for a video I made comparing the aerodynamics of the upcoming Tesla Cybertruck to a more traditional design modeled after a Ford F150. For fun, the aerodynamics of a brick will also be evaluated.
The purpose was not to realistically capture the aerodynamics of either vehicle but to get a rough, first order, approximation to be able to compare them.

The general procedure for this project where:
- Generate the Geometry (SolidWorks)
- Meshing (BlockMesh & SnappyHexMesh)
- Specifying Boundary conditions (OpenFOAM)
- Running the Simulation (OpenFOAM)
- Postprocessing (ParaView & Blender)

Boundary Conditions:
- velocity inlet = 132 m/s (equivalent Re to the full-size truck @ 50mph)
- pressure outlet
- walls with slip around the domain
- no slip at the truck surface

Steps to improve the Project:
- model the rotating wheels
- generate more accurate vehicle models
- greatly refine the mesh and increase the domain size
