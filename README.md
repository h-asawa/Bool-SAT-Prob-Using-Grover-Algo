# Bool-SAT-Prob-Using-Grover-Algorithm

## Motivation 
Grover's algorithm is a quantum algorithm to search for an element in unsorted array quadratically faster than the classical linear search for large datasets. <br />

In this project, we will solve a boolean satisfiability problem using Grover's algorithm by searching through all the possible combinations to determine the correct ones. 

## Problem Statement
Frank wants to throw a dinner party to celebrate Alice and Bob’s engagement. He is also considering inviting their mutual friends Charles, Dave and Eve. However, he is aware that Charles will come to the party only if Dave comes without Eve. Frank wants to know what possible combinations of invitations he can write for his friends Alice, Bob, Charles, Dave and Eve. <br />

Help Frank calculate all the possible combinations using Grover’s algorithm.

## Steps Involved
1. Creating a phase oracle - <br />
   First we create the quantum circuit (5 qubits) to solve the problem using a phase oracle. We know that Grover's algorithm solves oracles that add a negative phase to the solution states. Hence, the oracle will be a diagonal matrix, where entry corresponding to the marked item will have a negative phase. Using statevector's from_label attribute and diagonal operators, we mark the states 11000,11001,11010,11011,11110. <br />
   
2. Creating 5 qubit diffuser circuit - <br />
   This is created using some quantum gates like pauli X gate, Hadamard gate, multi-controlled Z gate etc.
   
3. Initialising the state - <br />
   This is achieved by applying H-gate to 'qubits' in quantum circuit.

4. Creating the final circuit - <br />
   Final circuit is made by initialising the states, appending the quantum circuits formed by step 1 and 2. As we have 5 solution states and 32 possibilities, we need to run 2 iterations.
   
5. Getting the results - <br />
   Achieved by using a quantum simulator to run the algorithm on final circuit for a sufficient number of counts and plotting the histogram of frequency of measured states. 
   <br />
## Result - 

The correct possible combinations in dinner party are (11110) , (11000) , (11001) , (11010) , (11011). Each bit corresponds respectively to Alice,Bob,Charles,Dave and Eve.

![image](https://user-images.githubusercontent.com/83265838/173781245-d34f54c1-ba52-4bfa-8c52-48b2e288b7c6.png)
