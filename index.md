---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
author_profile: true
---

## Project Idea

Create a visualization of famous quantum algorithms for a better understand of how they work.

To generalize the visualization of quantum algorithms to a higher number of entangled qubits, one must create subspaces per direction of the arrow (since human beings cannot visualize more than \\(3\\) dimensions). Even though this is very restrictive, we generally do not care about every result when doing quantum algorithms (apparently). 

## Background

Motivation: Bloch sphere

Video: https://www.youtube.com/watch?v=WjjUfEpej-0

## 1. Visualizing Quantum Algorithms


### Deutsch-Hoza Algorithm

Deutsch-Hoza Algorithm is a quantum algorithm that solves the following problem.

Suppose you have a function \\(f(x): \\{0,1\\}^n \to \\{0,1\\}\\). You are promised it is either constant, meaning that \\(f(x)=0\\) or \\(f(x)=1\\) for all \\(x\\), or it is balanced, meaning that the function returns \\(1\\) and \\(0\\) and equal number of times in the domain of \\(f(x)\\). To solve this deterministically, a classical function requires an exponential number of calls to the oracle in terms of the number of bits, \\(n\\). However, a quantum algorithm can solve this with one oracle inquiry. 

Assuming we already have the ancillary necessary for phase kickback, the quantum algorithm performs a Hadamard on \\(n\\) qubits at the initial \\(0\\) state, then a phase flip for the states such that \\(f(x)=1\\), and then the Hadamard again.

We can then visualize this quantum algorithm, considering two possibilities. The first possibility is that this function is constant. In this diagram, \\(e\\) denotes all the possible qubit states besides \\(0\\).

The qubit state initializes like this:

<img width="494" height="375" alt="image" src="https://github.com/user-attachments/assets/c84b2d48-f8e9-4d00-8ac6-ca0105f7af5c" />

Then, the Hadamard gate is applied, which rotates the green qubit state \\(180\\) degrees about the yellow arrow (the directions of this yellow arrow depend on the dimensionality of \\(n\\). What is important to note is that as \\(n\\) grows large, the angle decreases. When \\(n=1\\), the angle is \\(22.5\\) degrees for the yellow arrow.

<img width="512" height="342" alt="image" src="https://github.com/user-attachments/assets/27d406e4-1590-4315-93dd-56db1d6b6675" />



### Grover's Algorithm

### No Overshooting Grover

### Quantum Bomb Experiment



Tools:

Python, Qtip, Complex Numbers, Solid Geometry

Goals: Gain a more intuitive understanding of quantum algorithms

Goals: Beter understand the motivation on how these quantum algorithms were invented
