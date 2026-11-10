> **Note (2026-11-09):** the code, data and reproduction scripts of this work are now maintained in [nasir26/u55c-statevector-sim-30q](https://github.com/nasir26/u55c-statevector-sim-30q) (currently private, to be published after review). This repository stays as it is for reference.

Single unified benchmark file. Three backends, four algorithms, complex128 throughout, per-algorithm plots with all three hardwares overlaid.


One gate list per (algorithm, n_qubits, seed) built on the host once and shared by all three hardwares — that's the only way fidelity comparisons can be meaningful (same angles → same target state).

CPU reference in numpy complex128, applies gates via tensordot.

GPU via CUDA-Q kernels (matching the cudaq script you provided).

FPGA via fpga_simulator_version_5 (the v05 simulator we just built).

Reference state = CPU result when n ≤ cpu_cap, else analytic ideal where known (GHZ, QFT|0⟩), else skip fidelity.

Per-algorithm plots: 4 separate figures (one per algorithm), each with two panels (time vs qubits, infidelity vs qubits), three lines per panel (CPU/GPU/FPGA).

---

## Citation

If you use this work in your research, please cite:

```bibtex
@misc{nasirali_updated_fpga_based_s,
  author    = {Nasir Ali},
  title     = {Updated FPGA Based Statevector Simulator},
  year      = {2026},
  publisher = {GitHub},
  url       = {https://github.com/nasir26/Updated_FPGA_Based_Statevector_Simulator},
  note      = {Centre for Development of Advanced Computing (C-DAC), Noida, India}
}
```

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.\
© 2026 Nasir Ali, C-DAC Noida. All rights reserved.
