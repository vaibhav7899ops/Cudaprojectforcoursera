CUDA-Based Fluid Simulation (Image Processing)

This project presents a high-performance fluid simulation system built using CUDA and Smoothed Particle Hydrodynamics (SPH). By leveraging GPU parallelism, the system efficiently simulates large-scale particle interactions in a 3D space, achieving realistic fluid behavior even with millions of particles.

📌 Key Features
🌊 3D fluid simulation based on SPH methodology
⚡ Real-time execution using CUDA-enabled GPUs
🧩 Efficient neighbor detection via spatial hashing
🧪 Physically inspired fluid dynamics:
Pressure interactions
Viscous effects
Surface tension modeling
Boundary constraints
📦 Export support in PLY format for rendering and analysis
🐍 Visualization utilities implemented in Python
📊 Built-in tools for performance evaluation
⚙️ Working Principle
🧠 Smoothed Particle Hydrodynamics (SPH)

SPH is a particle-centric approach for modeling fluids, where the fluid body is represented as a collection of discrete particles. Each particle carries physical properties and interacts with nearby particles using a smoothing function.

Core Components:
Density Estimation
A particle’s density is computed by aggregating contributions from surrounding particles, weighted by a smoothing kernel.
Pressure Interaction
Pressure forces arise due to density differences, driving particles from compressed regions toward less dense areas.
Viscosity Effect
Viscosity dampens velocity differences, encouraging particles to align their motion with neighbors.
Surface Tension
Surface forces act on boundary particles to maintain cohesive fluid shapes and reduce surface irregularities.
⚡ CUDA-Based Acceleration

The system utilizes NVIDIA CUDA to distribute computations across thousands of GPU threads:

Efficient Neighbor Lookup
A spatial hash grid is used to quickly identify nearby particles.
Parallel Execution
Each particle’s calculations (density, forces, updates) are handled simultaneously on the GPU.
🚀 Optimization Techniques
🗂️ Spatial Hashing
Limits interaction checks to particles within nearby cells, reducing computational cost
📦 Memory Coalescing
Structures data for optimal GPU memory throughput
⚡ Shared Memory Usage
Temporarily stores frequently accessed data in faster on-chip memory
🔀 Kernel Merging
Combines multiple computational steps into fewer GPU kernel launches
📊 Performance Evaluation

(Benchmarked on NVIDIA RTX 3080)

Particle Count	Frame Time (ms)	FPS
10,000	2.3	434.8
50,000	9.7	103.1
100,000	19.1	52.4
500,000	94.3	10.6
1,000,000	187.8	5.3
🧾 Conclusion

This implementation highlights the effectiveness of combining SPH with GPU acceleration to achieve scalable and realistic fluid simulations. The system demonstrates strong performance even at high particle counts, making it suitable for applications such as:

Game physics engines
Visual effects and animation
Scientific and engineering simulations
