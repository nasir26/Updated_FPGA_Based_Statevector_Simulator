Single unified benchmark file. Three backends, four algorithms, complex128 throughout, per-algorithm plots with all three hardwares overlaid.


One gate list per (algorithm, n_qubits, seed) built on the host once and shared by all three hardwares — that's the only way fidelity comparisons can be meaningful (same angles → same target state).

CPU reference in numpy complex128, applies gates via tensordot.

GPU via CUDA-Q kernels (matching the cudaq script you provided).

FPGA via fpga_simulator_version_5 (the v05 simulator we just built).

Reference state = CPU result when n ≤ cpu_cap, else analytic ideal where known (GHZ, QFT|0⟩), else skip fidelity.

Per-algorithm plots: 4 separate figures (one per algorithm), each with two panels (time vs qubits, infidelity vs qubits), three lines per panel (CPU/GPU/FPGA).
