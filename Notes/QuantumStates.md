# Quantum states

### Quantum memory

Quantum memory is the Quantum version of traditional computer memory where
instead of storing data as as 1 or 0, quantum memory will store a quantum state
called a qubit.

A qubit is a unit of information stored as a vector, where the two directions
are written as either a |1> or a |0>.

### Bell state

Bell states are four specific maximally entangled quantum states of two qubits.
They are in a superposition of 1 amd 0. The two qubits in the Bell state are
entangled so if the random outcome of the first qubit is measured the seemingly
random outcome of the second qubit will be the same as the first qubit.

They can be created by applying a Hadamard gate to qubit 0 and then a controlled
NOT gate applied across qubits 0 and 1.

```py
import numpy as np
from qiskit import *

qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0,1)
print(qc.draw())
```

```ascii
        ┌───┐
q_0: |0>┤ H ├──■──
        └───┘┌─┴─┐
q_1: |0>─────┤ X ├
             └───┘
```

### GHZ (Greenberger-Horne-Zeilinger) state

A GHZ state is a type of entangled quantum state involving three qubits.

It can be achieved by taking three qubits each in state |0> and then creating a
bell state between qubit 0 and 1, and then applying a Controlled NOT operation
across qubit 0 and 2.

```py
import numpy as np
from qiskit import *

qc = QuantumCircuit(3)
qc.h(0)
qc.cx(0,1)
qc.cx(0,2)
print(qc.draw())
```

```ascii
        ┌───┐
q_0: |0>┤ H ├──■────■──
        └───┘┌─┴─┐  │  
q_1: |0>─────┤ X ├──┼──
             └───┘┌─┴─┐
q_2: |0>──────────┤ X ├
                  └───┘
```
