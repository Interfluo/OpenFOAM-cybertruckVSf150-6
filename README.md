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


               _________________________
              /.                       /|
             / .                      / |
            /  .                     /  |
           /   .                    /   |
          /    .                   /    |
	     /     .                  /     |
	    /      .                 /      |
       /________________________/       |
       |       .................|.......|
       |       .                |       /
       |      .                 |      /
       |     .         __       |     /
       |    .        /__/|      |    /
       |   .         |__|/      |   /
       |  .                     |  /
       | .                      | /
       |._______________________|/
       

Steps to improve the Project:
- model the rotating wheels
- generate more accurate vehicle models
- greatly refine the mesh and increase the domain size

Commands to run any Case:
- blockMesh (create base mesh for domain)
- snappyHexMesh (carve out the geometry and refine)
- decomposePar (decompose the mesh)
- mpirun -np 6 pisoFoam -parallel (run the solver in parallel on 6 cores)
- ReconstructPar (recombine the decomposed results at every time-step)
- touch results.foam (create a results file)
