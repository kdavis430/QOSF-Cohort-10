Notes for Cohort 10

Part 1:
To keep things simple I used an X gate on the LSB (which will eventually be the target qubit for the CNOT gate) and the Hadamard gate on all other qubits. The CNOT gate works on the LSB with the control qubit being the next highest qubit. After the first two qubits the rest of them are acted upon by the Hadamard gate and then simply the identity gate.


Part 2:
I might not have done this correctly since I was not able to keep the state vector in a (2,2,2,...,2) form after the CNOT gate since this caused entanglement and so it was impossible to pick out individual qubits from then on, at least for the first two qubits which were involved in the CNOT operation. The identity gate leaves the remaining bits separate. So the two LSBs are in the format of a tensor product between two column vectors and not the individual qubits. Also the qubits involved with the CNOT were converted to column vectors since I couldn't figure out how to do the tensor product of a CNOT gate and row vector of two individual bits.


Bonus:
1. I believe sampling from the final states of the state vector involves calculating a partial trace (in Part 1) which I was unable to do in time. I think the technique used in Part 2 would give you the answer more directly by simply accessing the correct index of the state ... again with more time this is the approach I would have taken. Entanglement makes accessing these indices more complicated.

2. Expectation values were calculated and shown in the output using the original Psi (the tensor product of |0>'s) and final resultant Psi. They were all found to be zero in all runs for my circuit. I used the tensordot function to calculate these values.


Conclusion:
This was a good exercise to show how memory management can play a role in a project but also the two parts reveal the different information one can gather from a problem.

In part 1 the final result for the entire state vector is revealed at the end ... you need to perform a few more steps (partial trace?) to get the state of a single qubit. This comes at a huge memory cost as the amount of memory needed to calculate tensor products of operators grows very rapidly as shown in the output plot for part 1.

In part 2 we can see the result of each qubit directly but we do not see the final total state vector, which we could get by the tensor product of each resultant qubit. This saves tremendously on memory but we sacrifice seeing the total final result.

