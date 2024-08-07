| Type | Parameters | Function | Range |
|------|------------|----------|-------|
| Garment | Particle Contact Offset | Distance at which particles start interacting | 0.03 - 0.12 |
| | Contact Offset | Distance at which collisions are detected | 0 - 16384 |
| | Rest Offset | Distance at which particles are in resting contact | 0 - 0.05 |
| | Solid Rest Offset | Distance for particle-solid interactions | Default |
| | Fluid Rest Offset | Distance for particle-fluid interactions | Default |
| | Solver Position Iteration Count | Number of iterations for solver to satisfy constraints | 6 - 255 |
| | Max Depenetration Velocity | Maximum speed at which particles are separated when overlapping | inf |
| | Max Neighborhood | Maximum number of neighboring particles for interactions | 36 - 512 |
| | Density | Mass per unit volume of the material | default |
| | Friction | Resistance to sliding motion | default |
| | Damping | Reduction of motion or oscillations | default |
| | Viscosity | Internal friction within the fluid material | default |
| | Cohesion | Attractive force between particles | default |
| | Surface Tension | Elastic tendency of the material's surface | default |
| | Drag | Resistance experienced when moving through fluid or air | default |
| | Lift | Force acting perpendicular to fluid flow around the material | default |
|Fluid | Particle Contact Offset | Distance at which particles start interacting | 0.17 - 0.3 |
| | Contact Offset | Distance at which collisions are detected | default |
| | Rest Offset | Distance at which particles are in resting contact | 0.03 - 0.3 |
| | Solid Rest Offset | Distance for particle-solid interactions | 0.1-0.2 |
| | Fluid Rest Offset | Distance for particle-fluid interactions | 0.1-0.15 |
| | Solver Position Iteration Count | Number of iterations for solver to satisfy constraints | 6 - 255 |
| | Max Depenetration Velocity | Maximum speed at which particles are separated when overlapping | inf |
| | Max Neighborhood | Maximum number of neighboring particles for interactions | 36 - 512 |
| | Density | Mass per unit volume of the material | 0 - 1e10 |
| | Friction | Resistance to sliding motion | 0 - 0.2 |
| | Damping | Reduction of motion or oscillations | 0 - 10 |
| | Viscosity | Internal friction within the fluid material | 1e3 - 1e6 |
| | Cohesion | Attractive force between particles | 0 - 100 |
| | Surface Tension | Elastic tendency of the material's surface | 0 - 100 |
| | Drag | Resistance experienced when moving through fluid or air | 0 - 78 |
| | Lift | Force acting perpendicular to fluid flow around the material | 0 - 1e10 |
| Deformable Body | Vertex Velocity Damping | Rate of reduction of vertex velocities | 0 - 10 |
| | Simulation Mesh Resolution | Granularity of the simulation mesh | 10 |
| | Solver Position Iterations | Number of iterations for solver to satisfy positional constraints | 8 - 255 |
| | Sleep Threshold | Velocity below which the body is considered to be at rest | 0 - 1e7 |
| | Settling Threshold | Velocity below which the body is considered to have settled | 0 - 1e7 |
| | Sleep Damping | Additional damping as the body approaches the sleep threshold | 0 - 1e7 |
| | Contact Offset | Distance at which collisions are detected | -inf |
| | Rest Offset | Distance at which particles are in resting contact | -inf |
| | Self Collision Filter Distance | Minimum distance to avoid self-collision | -inf |
| | Remeshing Resolution | Resolution for remeshing the input mesh | Default |
| | Target Triangle Count | Target resolution for quadric simplification | Default |
| | Max Depenetration Velocity | Maximum speed at which vertices can be separated when overlapping | inf |
| | Density | Mass per unit volume | Default |
| | Dynamic Friction | Resistance to sliding motion | 0 - 2048 |
| | Young's Modulus | Stiffness of the material | 1e3 - 1e10 |
| | Poisson's Ratio | Ratio of transverse to axial strain | 0 - 0.499 |
| | Elasticity Damping | Reduction of oscillations and vibrations | 0 - 0.05 |
| | Damping Scale | Adjusts the overall damping effect | 0 - 1.0 |
|Rigid Body | Max Linear Velocity | The rate of change of position of the rigid body. | 0-50 |
| | Max Angular Velocity | The rate of change of rotation of the rigid body. | 0-1e10 |
| | Collision Shape | Defines the shape used for collision detection. | default |
| | Contact Offset | Distance from the surface where collisions are detected. | -inf-inf |
| | Rest Offset | Effective contact distance from the surface. | -inf-inf |
|  | Convex Hull | Approximation method for collision shape. | 0-64 |
| | SDF (Signed Distance Field) | Approximation method using signed distance field. | default |
| | Mass | Defines the mass of the rigid body. | 0 to Inf |
| | Density | Defines the density of the rigid body material. | 0 to 1000 |
| | Friction | Resistance to sliding motion. | 0 to 1 |
| | Restitution (Bounciness) | Degree of elasticity of collisions. | 0 to 1 |
| | Material Density | Density of the material applied to the rigid body. | 0 to 1000 |
| Flow | X-Component | Flow rate in the x-direction | -inf-inf |
| | Y-Component | Flow rate in the y-direction | -inf-inf |
| | Z-Component | Flow rate in the z-direction | -inf-inf |
| | Magnitude | Overall magnitude of the flow | 0-inf |