---
title: "Post: Grover's Algorithm"
last_modified_at: 2026-07-22T16:20:02-05:00
categories:
  - Blog
tags:
  - Post Formats
  - readability
  - standard
---

Grover's Algorithm can also be neatly visualized.


Grover's algorithm is a quantum algorithm that solves the unsorted searching problem in \\(O(\sqrt{N})\\) time. The problem setup is as follows.

We have a function \\(f(x): \\{0,1\\}^n \to \\{0,1\\}\\), where \\(f(x)=1\\) at exactly one value of \\(x\\). We wish to find that value of \\(x\\). For a classical algorithm, each query can only rule out one possibility of \\(x\\), so we must have \\(O(N)\\) time. However, Grover's algorithm can solve this problem in \\(O(\sqrt{N})\\) time.

The quantum oracle for Grover's algorithm flips the sign of the coeficient regarding state \\(x\\) if and only if \\(f(x)=1\\). We can now visualize what the quantum algorithm does.

We use two subspaces. The first subspace consists of only one state, the state \\(x\\) where \\(f(x)=1\\). The second subspace consists of all the other states. We will call the subspaces \\(x\\) and \\(w\\) respectively.

We first intialize the state as \\(0\\), which will probably satisfy \\(f(x)=0\\) and thus be in the \\(w\\) subspace. If it doesn't, then we can manually call the oracle and check this. If it does indeed return \\(1\\), we have already succeded. 

<img width="434" height="323" alt="image" src="https://github.com/user-attachments/assets/c13b8878-ba5a-4093-b54b-eee2b262ea6e" />

Our next step is to perform a Hadamard. Since there are so many states in \\(w\\), the resulting state will be very close to \\(w\\). In this example, we assume there are \\(10\\) qubits, or \\(1024\\) possible inputs to the oracle.

<img width="506" height="329" alt="image" src="https://github.com/user-attachments/assets/b35ab839-8d6d-4754-b54b-5eaca572b7f0" />

We can barely see a change in the state because the majority of quantum states are in the \\(w\\) subspace.

Afterward, we call the oracle. This flips the sign of the \\(x\\) subspace (only \\(1\\) state), which is therefore a reflection about the \\(x\\)-axis.

<img width="485" height="334" alt="image" src="https://github.com/user-attachments/assets/d885e647-0c77-483b-8b9a-0d117795fa9e" />

The yellow vector was the previous state. 

Next, we can reflect about the yellow vector, since the state of the yellow vector doesn't depend on \\(f(x)\\), so it requires no inquries to the oracle.

<img width="469" height="321" alt="image" src="https://github.com/user-attachments/assets/21e1e932-aa75-4e1b-ab49-d3ba63a817e5" />

We're making some progress toward getting our quantum state close to the desired \\(x\\) state.

Afterward, we repeat. Every time, we call the oracle and then reflect about the yellow vector. Let us watch what happens when we do this again and again.

Call the oracle:

<img width="412" height="336" alt="image" src="https://github.com/user-attachments/assets/3945e79f-1dba-4edf-a27d-c1d00ba4627d" />

Reflect:

<img width="520" height="347" alt="image" src="https://github.com/user-attachments/assets/3d85247d-7683-4caa-ad74-fdec9071dddf" />

Call the oracle:

<img width="437" height="335" alt="image" src="https://github.com/user-attachments/assets/9ff1f888-de4c-4c2e-8184-24f1f60be5ea" />

Reflect:

<img width="423" height="333" alt="image" src="https://github.com/user-attachments/assets/a45eac6e-4c63-4580-80b6-106421433d84" />

Call the oracle:

<img width="415" height="318" alt="image" src="https://github.com/user-attachments/assets/1fb291fb-678e-47a2-b795-db44d4d62802" />

Reflect:

<img width="474" height="321" alt="image" src="https://github.com/user-attachments/assets/83c27302-18af-4af7-8e0e-8f50a9756995" />

Call the oracle and reflect \\(10\\) more times:

<img width="452" height="333" alt="image" src="https://github.com/user-attachments/assets/4f48afe6-93f7-4114-97d8-ccae4975c2fe" />

Call the oracle and reflect \\(11\\) more times:

<img width="545" height="333" alt="image" src="https://github.com/user-attachments/assets/936707a0-dbc8-4db7-a44e-3d539c64021e" />

The state of our qubit is almost exactly aligned with the \\(x\\) state! Therefore, a measurement will almost always yield the \\(x\\) state. 

In total, we called the oracle \\(25\\) times to get our desired result. Using some basic trigonometry, we actually need around \\(\frac{\pi}{4} \sqrt{N}\\) calls to the oracle to get a high probability of getting the state \\(x\\) upon measurement. This is better than the \\(N\\) oracle calls required by classical computing!
