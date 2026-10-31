# Quantum Entanglement, Noise Resilience & Error Correction

A Qiskit-based study investigating Bell state fidelity decay under environmental noise, followed by the implementation and performance evaluation of a 3-qubit quantum error-correction (QEC) architecture.

## 📌 Project Overview

This project explores the fragile nature of quantum information and how we can protect it. Using Qiskit and Python, the project is divided into two primary phases:
1. **Noise Decay Analysis:** Constructing all four maximally entangled Bell states ($|\Phi^+\rangle, |\Phi^-\rangle, |\Psi^+\rangle, |\Psi^-\rangle$) and simulating their degradation when subjected to open quantum system error channels—specifically **Amplitude Damping** (thermal energy relaxation/$T_1$ decay) and **Phase Damping** (dephasing/$T_2$ processes).
2. **Quantum Error Correction (QEC):** Engineering a 3-qubit repetition code paired with 2 ancilla qubits for non-destructive syndrome measurement, demonstrating how fault-tolerant design principles can recover quantum state fidelity under thermal noise.

## 🔬 Key Scientific Conclusions

* **Decay Trajectories:** Both amplitude and phase damping degrade the purity of entangled states, but their mathematical impact on the density matrix varies depending on the superposition structure of the specific Bell state.
* **Sensitivity to Noise:** Even at relatively low error probabilities ($p=0.05$), state fidelity drops noticeably, illustrating why quantum error correction is critical for fault-tolerant quantum computing.
* **Error Mitigation & Recovery:** The 3-qubit repetition code architecture successfully detects and mitigates bit-flip/thermal disturbances, maintaining higher state fidelity compared to uncorrected noisy states across varying error probability sweeps ($p \in [0.0, 0.20]$).

## ⚙️ Technical Highlights

* **Frameworks Used:** Qiskit, Qiskit Aer, NumPy, Matplotlib.
* **Core Concepts:** Quantum Circuits, Statevectors, Density Matrices, Quantum Channels, Fidelity Metrics, Repetition Codes, Syndrome Measurement, Ancilla Parity Checks.
* **Data Visualization:** Generated automated, high-resolution comparative decay curves and circuit diagrams:
  * `bell_state_1_noise_decay.png` through `bell_state_4_noise_decay.png`
  * `5-qubits with syndrome measurement.png`
  * `error_correction_fidelity_comparison.png`

## ⚠️ Limitations of Classical Simulation

While running these circuits locally on a personal machine is effective for learning and prototyping, classical simulation of quantum mechanics comes with distinct constraints:
1. **Exponential Scaling:** Simulating quantum states requires tracking $2^n$ complex amplitudes (where $n$ is the number of qubits). While trivial for 2 to 5 qubits, classical memory requirements scale exponentially, making large-scale simulations impossible on standard consumer hardware.
2. **Idealized Noise Models:** The amplitude and phase damping models used here assume uniform, isolated error channels on specific qubits. Real-world quantum processors (like IBM's superconducting QPUs) experience complex, correlated noise, spatial crosstalk, and State Preparation and Measurement (SPAM) errors that simplified local simulations cannot fully capture.

## 🚀 Future Extensions

* Scaling the analysis to GHZ states ($n>2$) to study multipartite entanglement decay.
* Expanding error-correction simulations from basic repetition codes to full surface code patches or stabilizer error-correction circuits.
* Executing the same circuits on real IBM Quantum hardware via Qiskit Runtime to compare simulated fidelity decay against empirical hardware results.
