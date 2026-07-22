---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
author_profile: true
---

## Project Idea

Create a visualization of famous quantum algorithms for a better understand of how they work.

To generalize the visualization of quantum algorithms to a higher number of entangled qubits, one must create subspaces per direction of the arrow (since human beings cannot visualize more than \\(3\\) dimensions). Even though this is very restrictive, we sometimes do not care about every result when doing quantum algorithms. Whenever that is the case, we can find a way to visualize the algorithm. 

## Background

Motivation: The Bloch sphere was an excellent tool to visualize \\(1\\) qubit quantum systems and unitary operators, but fails to make any meaningful visualization when we have multiple entangled qubits. 

Luckily, when using subspaces as cardinal directions for quantum algorithms, a unitary operator is still a rotation on that sphere, like how it is a rotation on the Bloch sphere.

Video: Visualizing Qubits on the Bloch Sphere-Qiskit: https://www.youtube.com/watch?v=WjjUfEpej-0


## An Example Of Visualizing Quantum Algorithms: The Deutsch-Hoza Algorithm


Deutsch-Hoza Algorithm is a quantum algorithm that solves the following problem.

Suppose you have a function \\(f(x): \\{0,1\\}^n \to \\{0,1\\}\\). You are promised it is either constant, meaning that \\(f(x)=0\\) or \\(f(x)=1\\) for all \\(x\\), or it is balanced, meaning that the function returns \\(1\\) and \\(0\\) and equal number of times in the domain of \\(f(x)\\). To solve this deterministically, a classical function requires an exponential number of calls to the oracle in terms of the number of bits, \\(n\\). However, a quantum algorithm can solve this with one oracle inquiry. 

Assuming we already have the ancillary necessary for phase kickback, the quantum algorithm performs a Hadamard on \\(n\\) qubits at the initial \\(0\\) state, then a phase flip for the states such that \\(f(x)=1\\), then the Hadamard again, and then finally a measurement in the computaitonal basis.

We can then visualize this quantum algorithm, considering two possibilities. The first possibility is that this function is constant. In this diagram, \\(e\\) denotes all the possible qubit states besides \\(0\\). It is a SUBSPACE, so it is not a specific quantum state.

The qubit state initializes like this:

<img width="494" height="375" alt="image" src="https://github.com/user-attachments/assets/c84b2d48-f8e9-4d00-8ac6-ca0105f7af5c" />

Then, the Hadamard gate is applied, which rotates the green qubit state \\(180\\) degrees about the yellow arrow (the directions of this yellow arrow depend on the dimensionality of \\(n\\). What is important to note is that as \\(n\\) grows large, the angle decreases. When \\(n=1\\), the angle is \\(22.5\\) degrees for the yellow arrow.

<img width="512" height="342" alt="image" src="https://github.com/user-attachments/assets/27d406e4-1590-4315-93dd-56db1d6b6675" />

Next, the oracle is called. Since we assumed \\(f(x)\\) is balanced, the oracle either negates the entire wavefunction of the qubit or does nothing. However, adding a global phase doesn't change measurement outcomes, so we can pretend nothing happens after the oracle call.

After that, we apply the Hadamrd.

Two rotations of \\(180\\) degrees does nothing to the qubit, and it is back to where it started.

<img width="432" height="340" alt="image" src="https://github.com/user-attachments/assets/ee3fd69c-8f49-45cd-9caf-f791a7a813ff" />


After a measurement, we are guaranteed to get the \\(0\\) state.

Next, we see what happens if \\(f(x)\\) is balanced instead. We now use two different subspaces, the subspace where \\(f(x)=0\\) and the subspace where \\(f(x)=1\\). Denote these subspaces \\(a\\) and \\(b\\), respectively. Let us assume \\(f(0)=0\\), so the qubit initializes in the \\(a\\) subspace.

<img width="379" height="357" alt="image" src="https://github.com/user-attachments/assets/1ff1c5ab-04d8-4185-b212-181345b862a3" />

After we apply the Hadamard gate, since there are an equal number of states in the \\(a\\) and \\(b\\) subspaces, the qubit state will be pointing perfectly in the middel between them.

<img width="503" height="346" alt="image" src="https://github.com/user-attachments/assets/6c06140a-29b9-4fd4-b3e4-6bcfe1878ec0" />


Then, we call the phase kickback oracle. This flips the sign of all states in the \\(b\\) subspace, but keep all the states in the \\(a\\) subspace as they are.

<img width="458" height="363" alt="image" src="https://github.com/user-attachments/assets/677bb3a8-e207-4a32-a07b-86779991902a" />


Finally, we call the Hadamard again. Since the Hadamard is a rotation of \\(180\\) degrees about the yellow vector, we have the state becomes

<img width="509" height="336" alt="image" src="https://github.com/user-attachments/assets/414c2e99-3bb1-475a-828c-4d76f035ad6e" />

Hence, a measurement will yield the qubit state in one of the states that satisfy the property that \\(f(x)=1\\). This state cannot be \\(0\\) since we assumed \\(f(0)=0\\). 

Therefore, the Deutsch-Hoza returns \\(0\\) if \\(f(x)\\) is constant, and something other than \\(0\\) if \\(f(x)\\) is balanced in one oracle inquiry, proving that the Deutsch-Hoza algorithm works as intended using only visualizations and no algebra.





### Tools

To create these diagrams for visualization of quantum algorithms, I used Python and Qutip. To understand quantum algorithms, one must be familiar with complex numbers and some quantum gates.

### Goals Of This Project

By visualization quantum algorithms, we can get more of an intutive feeling of how they work. Moreover, we can better understand the motivation behind these algorithms, as we can actually see what is going on, since we are no longer staring at mathematical calculations and praying something cancels out in the end.
