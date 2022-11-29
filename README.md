# MidcircuitMeasureReset
markdown: kramdown
theme: Architect
[Full_adder using Mid_circuit measure and reset] (https://github.com/Ashw1nKarth1k/MidcircuitMeasureReset/blob/main/final_full_adder%20(1).ipynb)
[BV+Simon by reusing Qubits] (https://github.com/Ashw1nKarth1k/MidcircuitMeasureReset/blob/main/final_mid_mes_rst%20(1).ipynb)
[Report] (https://github.com/Ashw1nKarth1k/MidcircuitMeasureReset/blob/main/Mid_circuit%20measure%20and%20reset_%20report.pdf)
Final Presentation: (https://github.com/Ashw1nKarth1k/MidcircuitMeasureReset/blob/main/592_PP%20(1).pptx)

<!DOCTYPE html>
<html>
	<body>
		<p>1.	Problem Statement:
 
Typically, measurements in Quantum Circuits are performed at the end of the simulation to gather final information about the state of qubits(result in Classical terminology). The circuit is simulated multiple times(shots) and the measurement records the states of qubits. The states with the highest shots give the possible solutions.
 
Mid-circuit measurement along with reset enables the programmer to reuse the same qubits or ancilla qubits for the next connected circuit or in the same circuit itself. In this way, we can save the number of qubits we reserve for executing the job.
 
In general, the Quantum circuits get affected by various noise factors coming from idleness and quantum gates themselves. So, a stabilizer-based mid-circuit measurement and reset/set of the qubit corrects the deviation maintaining fidelity.
 

 

 
1.1	QC optimization using Mid measurement/reset:
 
We are planning to implement an n-bit Full adder circuit to show how mid-measurement and reset help to optimize the qubits usage. The textbook implementation of the n-bit full adder asigns each qubit to each bit of the inputs. Our approach induces a mid-circuit measurement and reset. Once the full addition operation is finished, the qubits are measured and reused for the next bit fulladder.
 
Mid-circuit measurement and reset can be significant in reducing the total number of qubits used in a quantum circuit. Implementing a n-bit Full-adder circuit can be a plausible way to demonstrate the decrease in the need of additional qubits. Typically, for Implementing a 1-bit full-adder, 5 qubits are needed. With increase in the width of the input, the number of qubits required increases at the rate of ‘4’ qubits where ’n’ is the width of the input bits.
 
With the use of Mid-circuit measurement and reset, the sum bit can be measured and reset for storing consequent values of sum. The carry bit and input bits can also be reset and reused with the consequent carry and the input bits. Single resetting of the qubits can affect the fidelity. In order to prevent errors in the circuit, the reset is usually performed multiple times. But this significantly increases the depth of the circuit and hence the execution time. Below is description of typical n-bit full adder circuit. With the new approach, we reset the input A0,B0 and carry C0 and reuse them for all An, Bn and Cn.
 

 

 
 
 

 
1.2	Circuits fusing using Mid measurement/reset:
 
In this we are planning to fuse two Quantum circuits into a single module and analyse whether this gives any improvement on wait-times on actual hardware job queues. We plan to implement Bernstein-Vazirani and Simon’s algorithms as the circuits. After first circuit completes its execution, we do a measure and reset the qubits for the next circuit implementation. Firstly, we want to run the circuits individually and note the results. Later, we want to merge the operations and run as a single job to monitor the improvements in the wait time. We are assuming monitoring the wait times on a set of IBMQ-s give more generalized and sophisticated results.
 
Also, we need to monitor if there is any fidelity issues caused by doing a mid-measurement and reset operation in between the circuits.
 

 

 

 

 
1.3	QEC for Mid measurement/reset noise:
 
As explained in the problem statement, Quantum circuits are susceptible to qubit and gate noise. We are planning to implement a repetition code based error correction technique. And after doing a mid circuit measurement on a noisy circuit, if we detect any error, we fix it by doing a conditional reset. This mid circuit measurement and reset might effect the fidelity of circuit and lead to errors which needs to be analysed. Effects of fidelity on QEC is as below:
 
F : Fidelity without QEC	F_ec: Fidelity with QEC. P : Probability of error in qubit.
 
Note: Taken from Wikipedia: https://en.wikipedia.org/wiki/Quantum_error_correction
 
 
 

 

 
</p>
	</body>
</html>
