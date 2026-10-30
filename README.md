# quantum-bell-states-analysis
A Qiskit-based study on Bell state fidelity decay under environmental noise.
# Quantum Entanglement & Noise Resilience: A Fidelity Analysis of Bell States

## 📌 Project Overview
This project explores the behavior of quantum entanglement under environmental noise. Using **Qiskit** and **Python**, I constructed all four maximally entangled **Bell states** ($|\Phi^+\rangle$, $|\Phi^-\rangle$, $|\Psi^+\rangle$, $|\Psi^-\rangle$) and simulated their degradation when subjected to open quantum system error channels: **Amplitude Damping** (representing thermal energy relaxation/$$T_1 \text{ decay}$$ decay) and **Phase Damping** (representing quantum information loss via dephasing/$$T_2 \text{ decay}$$ processes).

---

## 🔬 Key Scientific Conclusions
By running parameter sweeps across varying error probabilities ($p = 0.0$ to $0.20$) and calculating the **Quantum State Fidelity ($F$)** via density matrix evolution, I observed:
* **Decay Trajectories:** Both amplitude and phase damping degrade the purity of entangled states, but their mathematical impact on the density matrix varies depending on the superposition structure of the specific Bell state.
* **Sensitivity to Noise:** Even at relatively low error probabilities ($p = 0.05$), state fidelity drops noticeably, illustrating why quantum error correction is critical for fault-tolerant quantum computing.
* **Comparative Resilience:** Mapping these fidelity decay curves side-by-side demonstrates how environmental interactions erode quantum correlation differently across distinct computational bases.

---

## ⚙️ Technical Highlights
* **Frameworks Used:** Qiskit, Qiskit Aer, NumPy, Matplotlib.
* **Core Concepts:** Quantum Circuits, Statevectors, Density Matrices, Quantum Channels, Fidelity Metrics.
* **Data Visualization:** Generated automated, high-resolution comparative decay curves (`.png` outputs) to visually contrast thermal relaxation versus pure dephasing.

---

## ⚠️ Limitations of Laptop-Based Classical Simulation
While running these circuits locally on a personal machine is effective for learning and prototyping, classical simulation of quantum mechanics comes with distinct constraints:
1. **Exponential Scaling:** Simulating quantum states requires tracking $2^n$ complex amplitudes (where $n$ is the number of qubits). While trivial for 2 qubits, classical memory requirements scale exponentially, making large-scale simulations impossible on standard consumer hardware.
2. **Idealized Noise Models:** The amplitude and phase damping models used here assume uniform, isolated error channels on specific qubits. Real-world quantum processors (like IBM's superconducting QPUs) experience complex, correlated noise, spatial crosstalk, and State Preparation and Measurement (SPAM) errors that simplified local simulations cannot fully capture.

---

## 🚀 Future Extensions
* Scaling the analysis to GHZ states ($n > 2$) to study multipartite entanglement decay.
* Executing the same circuits on real IBM Quantum hardware via Qiskit Runtime to compare simulated fidelity decay against empirical hardware results.

---
*View the `.ipynb` notebook above to inspect the complete code and generated fidelity plots.*
