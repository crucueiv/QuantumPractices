# QuantumPractices

Collection of **Quantum Computing** practices completed during the third year
of the Software Engineering degree at the University of Málaga. The repository
contains five Jupyter notebooks that progressively introduce the mathematical
and practical foundations required to work with quantum states, operators,
circuits, and measurements of one- and multi-qubit systems.

## Repository contents

```text
QuantumPractices/
├── Practice1/
│   └── CC-nb1-complejos.ipynb
├── Practice2/
│   └── CC-nb2-vectores.ipynb
├── Practice3/
│   └── CC_nb3_estado_y_esfera_bloch.ipynb
├── Practice4/
│   └── CC-nb4-circuitos-1qubit.ipynb
├── Practice5/
│   └── CC-nb5-medidas-1qubit.ipynb
└── README.md
```

The notebooks include explanations, exercises, numerical checks, mathematical
representations, and visualizations. They are primarily prepared to run in
Google Colab, but they can also be opened in a local Jupyter environment.

## Practices

### Practice 1 — Complex numbers

**File:** `Practice1/CC-nb1-complejos.ipynb`

Studies the complex arithmetic used to represent quantum amplitudes:

- Cartesian and polar representations;
- modulus, phase, and complex conjugation;
- conversion between Cartesian and polar coordinates;
- addition, multiplication, and division of complex numbers;
- calculation and numerical verification of the absolute value;
- sums of equally spaced phases and amplitude cancellation;
- graphical representation of a simple wave function
  \(y(t)=\operatorname{Re}(e^{i\omega t})\).

This practice covers part of the mathematical foundation of quantum computing:
state amplitudes and relative phases are complex numbers.

### Practice 2 — Vectors and operators

**File:** `Practice2/CC-nb2-vectores.ipynb`

Introduces the formalism of complex vector spaces and matrices:

- bra-ket notation using column and row vectors;
- adjoints, conjugate transposes, and matrix indexing;
- norms and manipulation of complex vectors;
- vector-space dimension;
- construction of bases and orthonormalization through QR decomposition,
  related to the Gram-Schmidt process;
- outer products \(\lvert u\rangle\langle v\rvert\);
- linear operators and projections onto subspaces;
- eigenvalues and eigenvectors;
- matrix powers and matrix exponentials;
- Pauli matrices \(I\), \(X\), \(Y\), and \(Z\).

This practice focuses on the linear-algebra formulation of quantum mechanics:
states are vectors, while observables and transformations are operators.

### Practice 3 — States and the Bloch sphere

**File:** `Practice3/CC_nb3_estado_y_esfera_bloch.ipynb`

Works with quantum states using Qiskit's `Statevector` class:

- creation, visualization, and validation of state vectors;
- state normalization;
- generation of one-qubit states from the angles \(\theta\) and \(\phi\);
- representation of states on the Bloch sphere;
- computational-basis states and other one-qubit states;
- tensor products of states;
- qubit-numbering order in composite states, including the distinction
  between the least and most significant qubits;
- state factorization and separability;
- introduction to the Schmidt decomposition;
- representation of non-factorizable states using the Q-sphere;
- examples of Bell states and GHZ states.

This practice studies the geometric representation of one-qubit states and the
composition, separability, and entanglement of multi-qubit states.

### Practice 4 — One-qubit circuits

**File:** `Practice4/CC-nb4-circuitos-1qubit.ipynb`

Introduces the construction and simulation of one-qubit quantum circuits:

- circuit initialization from a state vector;
- circuit representations in text, LaTeX, and Matplotlib;
- use of `save_statevector` probes to inspect intermediate states;
- simulation with `AerSimulator` using the state-vector method;
- retrieval of the final state and ideal probabilities;
- construction and analysis of circuits using the \(X\), \(H\), and \(Y\)
  gates;
- composition of multiple gates in a single circuit;
- comparison between the state defined by a circuit and the simulated state.

The practice focuses on the unitary evolution of a qubit and on how quantum
gates transform its amplitudes.

### Practice 5 — One-qubit measurements

**File:** `Practice5/CC-nb5-medidas-1qubit.ipynb`

Studies measurement and the experimental estimation of quantum properties:

- creation of quantum and classical registers;
- measurement of a qubit and storage of the classical result;
- circuit simulation with different numbers of `shots`;
- result counting and bar-chart visualization;
- measurement after applying quantum gates;
- the quantum coin and comparison between one and multiple Hadamard
  operations;
- conversion of counts into probability distributions;
- calculation of expectation values of observables;
- estimation of \(\langle Z\rangle\), \(\langle X\rangle\), and
  \(\langle Y\rangle\) through equivalent circuits;
- visualization of the vector associated with expectation values on the Bloch
  sphere.

This practice covers the measurement postulate, the randomness of measurement
results, and the relationship between repeated measurements, probabilities,
and observables.

## Dependencies

The notebooks install or use the following libraries:

- Python 3;
- Qiskit `2.1.2`;
- `qiskit-aer`;
- `qiskit-ibm-runtime`;
- `qiskit-optimization`;
- NumPy;
- SciPy;
- SymPy;
- pandas;
- Matplotlib;
- IPython/Jupyter.

Each notebook contains the setup cell used in Google Colab:

```bash
pip install qiskit==2.1.2 qiskit[visualization] qiskit-aer \
  qiskit-ibm-runtime qiskit-optimization matplotlib numpy scipy sympy pandas
```

## Running the notebooks

### Google Colab

1. Open the desired notebook in Google Colab.
2. Run the package setup cell.
3. Run the cells in order.

The notebooks detect Colab to install their dependencies, and some cells save
figures temporarily under `/tmp`.

### Local environment

In a Python virtual environment, install the dependencies and start Jupyter:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install qiskit==2.1.2 "qiskit[visualization]" qiskit-aer \
  qiskit-ibm-runtime qiskit-optimization matplotlib numpy scipy sympy pandas
jupyter lab
```

Then open any `.ipynb` file and run its cells in order. The recommended
sequence is `Practice1` through `Practice5`, since each practice builds on
concepts introduced in the previous ones.

## Conceptual progression

The repository follows this progression:

1. **Complex numbers:** amplitudes and phases.
2. **Linear algebra:** vectors, matrices, and operators.
3. **Quantum states:** normalization, the Bloch sphere, tensor products, and
   entanglement.
4. **Circuits:** gates and one-qubit evolution.
5. **Measurement:** probabilities, experimental results, and expectation values.

Together, these practices provide a practical introduction to the mathematical
description and simulation of basic quantum circuits with Qiskit.
