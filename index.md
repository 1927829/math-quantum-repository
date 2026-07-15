---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
author_profile: true
---
# The Geometry and Algebra of Complex Numbers

Complex numbers expand our mathematical horizon, providing a complete algebraic system where every non-zero polynomial has roots. Beyond their algebraic utility, complex numbers offer a elegant, unified geometric framework that bridges algebra, geometry, trigonometry, and calculus.

---

## 1. Introduction and Definitions

A **complex number** \\(z\\) is defined as an ordered pair of real numbers $(a, b)$, written in the algebraic form:

$$z = a + bi$$

where:
* $a = \text{Re}(z)$ is the **real part** of $z$.
* $b = \text{Im}(z)$ is the **imaginary part** of $z$.
* $i$ is the **imaginary unit**, defined by the fundamental property:

$$i^2 = -1$$

The set of all complex numbers is denoted by $\mathbb{C}$:

$$\mathbb{C} = \{ a + bi \mid a, b \in \mathbb{R} \}$$

---

## 2. Geometric Representation: The Complex Plane

Complex numbers can be visualized geometrically on a two-dimensional Cartesian plane called the **Complex Plane** or **Argand Diagram**. 
* The horizontal axis represents the **Real Axis** ($\text{Re}$).
* The vertical axis represents the **Imaginary Axis** ($\text{Im}$).

Each complex number $z = a + bi$ corresponds to a unique point $(a, b)$ or a position vector starting from the origin $(0,0)$ to the point $(a, b)$.

### Vector Representation and Polar Coordinates

The vector representing $z = a + bi$ has two key geometric properties:
1. **Modulus (or Absolute Value) $|z|$**: The length of the vector, representing the distance from the origin.
   $$r = |z| = \sqrt{a^2 + b^2}$$
2. **Argument $\theta$ (or $\arg(z)$)**: The angle formed with the positive real axis.
   $$\theta = \tan^{-1}\left(\frac{b}{a}\right)$$

Below is an interactive-style vector diagram of a complex number in the complex plane:

<div align="center">
  <svg width="400" height="400" viewBox="-50 -50 450 450" xmlns="http://www.w3.org/2000/svg" style="background-color: #fdfbf7; border-radius: 8px; border: 1px solid #e0dcd5; font-family: 'Times New Roman', serif;">
    <!-- Grid Lines -->
    <line x1="0" y1="300" x2="350" y2="300" stroke="#e6e2da" stroke-width="1" />
    <line x1="100" y1="300" x2="100" y2="0" stroke="#e6e2da" stroke-width="1" />
    <line x1="200" y1="300" x2="200" y2="0" stroke="#e6e2da" stroke-width="1" />
    <line x1="300" y1="300" x2="300" y2="0" stroke="#e6e2da" stroke-width="1" />
    <line x1="50" y1="0" x2="50" y2="350" stroke="#e6e2da" stroke-dasharray="2,2" />
    <line x1="250" y1="0" x2="250" y2="350" stroke="#e6e2da" stroke-dasharray="2,2" />
    <line x1="0" y1="100" x2="350" y2="100" stroke="#e6e2da" stroke-dasharray="2,2" />
    <line x1="0" y1="200" x2="350" y2="200" stroke="#e6e2da" stroke-dasharray="2,2" />
    
    <!-- Real and Imaginary Axes -->
    <line x1="0" y1="300" x2="350" y2="300" stroke="#4a4a4a" stroke-width="2" marker-end="url(#arrow)" />
    <line x1="50" y1="350" x2="50" y2="10" stroke="#4a4a4a" stroke-width="2" marker-end="url(#arrow)" />
    
    <!-- Axis Labels -->
    <text x="330" y="320" fill="#4a4a4a" font-size="14" font-weight="bold">Re (Real)</text>
    <text x="15" y="30" fill="#4a4a4a" font-size="14" font-weight="bold">Im (Imag)</text>
    <text x="40" y="315" fill="#4a4a4a" font-size="12">0</text>
    
    <!-- Vector z = a + bi -->
    <!-- Point at (250, 100) -> Real component 200, Imaginary component 200 -->
    <line x1="50" y1="300" x2="250" y2="100" stroke="#0066cc" stroke-width="3" marker-end="url(#blue-arrow)" />
    
    <!-- Projections -->
    <line x1="250" y1="100" x2="250" y2="300" stroke="#888" stroke-dasharray="4,4" stroke-width="1.5" />
    <line x1="50" y1="100" x2="250" y2="100" stroke="#888" stroke-dasharray="4,4" stroke-width="1.5" />
    
    <!-- Coordinates Text -->
    <text x="255" y="315" fill="#333" font-size="13">a</text>
    <text x="30" y="105" fill="#333" font-size="13">b</text>
    
    <!-- Point and Point label -->
    <circle cx="250" cy="100" r="5" fill="#d9534f" />
    <text x="260" y="95" fill="#d9534f" font-size="15" font-weight="bold">z = a + bi</text>
    
    <!-- Angle Theta / Modulus r -->
    <path d="M 90 300 A 40 40 0 0 0 82 268" fill="none" stroke="#d9534f" stroke-width="2" />
    <text x="100" y="285" fill="#d9534f" font-size="14" font-style="italic">&theta;</text>
    <text x="130" y="185" fill="#0066cc" font-size="14" font-style="italic">r = |z|</text>
    
    <!-- Markers definitions -->
    <defs>
      <marker id="arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#4a4a4a" />
      </marker>
      <marker id="blue-arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#0066cc" />
      </marker>
    </defs>
  </svg>
  <p><em>Figure 1: The Complex Plane representation of $z = a + bi$ showing modulus $r$ and argument $	heta$.</em></p>
</div>

---

## 3. Algebraic Operations

Operations on complex numbers mirror polynomial operations, with the added simplification that $i^2$ is always replaced by $-1$.

### Addition and Subtraction
Addition and subtraction are performed component-wise (combining real parts with real parts, and imaginary parts with imaginary parts):

$$(a + bi) \pm (c + di) = (a \pm c) + (b \pm d)i$$

**Geometric Interpretation:** Addition corresponds to **vector addition** following the Parallelogram Law:

<div align="center">
  <svg width="400" height="280" viewBox="-20 -20 420 300" xmlns="http://www.w3.org/2000/svg" style="background-color: #fdfbf7; border-radius: 8px; border: 1px solid #e0dcd5; font-family: 'Times New Roman', serif;">
    <!-- Origin (50, 230) -->
    <!-- Axes -->
    <line x1="20" y1="230" x2="380" y2="230" stroke="#888" stroke-width="1.5" marker-end="url(#axis-arrow)" />
    <line x1="50" y1="260" x2="50" y2="20" stroke="#888" stroke-width="1.5" marker-end="url(#axis-arrow)" />
    
    <!-- Vector z1 (50, 230) to (200, 180) -> diff (150, -50) -->
    <line x1="50" y1="230" x2="200" y2="180" stroke="#00b300" stroke-width="2" marker-end="url(#green-arrow)" />
    <text x="110" y="195" fill="#00b300" font-size="14" font-weight="bold">z₁</text>
    
    <!-- Vector z2 (50, 230) to (120, 90) -> diff (70, -140) -->
    <line x1="50" y1="230" x2="120" y2="90" stroke="#ff8c00" stroke-width="2" marker-end="url(#orange-arrow)" />
    <text x="65" y="145" fill="#ff8c00" font-size="14" font-weight="bold">z₂</text>
    
    <!-- Vector z1 + z2: Origin to (200+70, 180-140) = (270, 40) -->
    <line x1="50" y1="230" x2="270" y2="40" stroke="#b22222" stroke-width="3" marker-end="url(#red-arrow)" />
    <text x="210" y="110" fill="#b22222" font-size="15" font-weight="bold">z₁ + z₂</text>
    
    <!-- Parallelogram Dashed Lines -->
    <line x1="200" y1="180" x2="270" y2="40" stroke="#555" stroke-dasharray="4,4" stroke-width="1" />
    <line x1="120" y1="90" x2="270" y2="40" stroke="#555" stroke-dasharray="4,4" stroke-width="1" />
    
    <!-- Markers -->
    <defs>
      <marker id="axis-arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#888" />
      </marker>
      <marker id="green-arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#00b300" />
      </marker>
      <marker id="orange-arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#ff8c00" />
      </marker>
      <marker id="red-arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#b22222" />
      </marker>
    </defs>
  </svg>
  <p><em>Figure 2: Parallelogram Rule of Complex Addition ($z_1 + z_2$).</em></p>
</div>

### Multiplication
Multiplication involves applying the distributive property (FOIL) and substituting $i^2 = -1$:

$$(a + bi)(c + di) = ac + adi + bci + bdi^2$$
$$(a + bi)(c + di) = (ac - bd) + (ad + bc)i$$

### Complex Conjugation
The **complex conjugate** of $z = a + bi$, denoted by $\bar{z}$ or $z^*$, is formed by reversing the sign of the imaginary part:

$$\bar{z} = a - bi$$

**Properties:**
* $z \cdot \bar{z} = a^2 + b^2 = |z|^2$ (always a non-negative real number).
* Geometrically, $\bar{z}$ is a **reflection** of $z$ across the real horizontal axis.

### Division
To divide complex numbers, multiply the numerator and denominator by the complex conjugate of the denominator to make the divisor real:

$$\frac{a + bi}{c + di} = \frac{(a + bi)(c - di)}{(c + di)(c - di)} = \frac{(ac + bd) + (bc - ad)i}{c^2 + d^2}$$

---

## 4. Polar and Exponential Forms

Using trigonometry on the complex plane, we can rewrite the real components in terms of modulus $r$ and argument $\theta$:
* $a = r \cos\theta$
* $b = r \sin\theta$

### Polar Form
$$z = r(\cos\theta + i\sin\theta)$$

### Exponential Form (Euler's Formula)
By utilizing Taylor series expansions for $e^x$, $\sin x$, and $\cos x$, Leonhard Euler derived one of the most profound relations in mathematics:

$$e^{i\theta} = \cos\theta + i\sin\theta$$

Thus, any complex number can be compactly represented in **exponential form**:

$$z = r e^{i\theta}$$

### Multiplication and Division in Exponential Form
While addition and subtraction are easier in Cartesian coordinates, **multiplication** and **division** become exceptionally elegant in exponential form:

* **Multiplication**: Multiply the moduli, add the arguments.
  $$z_1 z_2 = (r_1 e^{i\theta_1})(r_2 e^{i\theta_2}) = r_1 r_2 e^{i(\theta_1 + \theta_2)}$$
* **Division**: Divide the moduli, subtract the arguments.
  $$\frac{z_1}{z_2} = \frac{r_1 e^{i\theta_1}}{r_2 e^{i\theta_2}} = \frac{r_1}{r_2} e^{i(\theta_1 - \theta_2)}$$

---

## 5. De Moivre's Theorem and Roots of Unity

### De Moivre's Theorem
For any real number $n$:

$$(r(\cos\theta + i\sin\theta))^n = r^n (\cos(n\theta) + i\sin(n\theta))$$

Using exponential notation, this theorem is a natural consequence of power properties:

$$(r e^{i\theta})^n = r^n e^{i n\theta}$$

### $n$-th Roots of Unity
The equation $z^n = 1$ has $n$ distinct solutions in the complex plane, called the **$n$-th roots of unity**. They are evenly spaced points on the unit circle ($r = 1$), given by:

$$z_k = e^{i\frac{2\pi k}{n}} = \cos\left(\frac{2\pi k}{n}\right) + i\sin\left(\frac{2\pi k}{n}\right) \quad \text{for } k = 0, 1, 2, \dots, n-1$$

---

## 6. Real-World Applications

Complex numbers are not "imaginary" in the sense of being unreal; they are vital tools used to model real-world physical systems:

1. **Electrical Engineering (AC Circuits)**:
   Alternating current (AC) voltage and current oscillate sinusoidally. Engineers model these signals as rotating vectors (phasors) represented by complex numbers, where resistance and reactance combine into a single complex quantity called **Impedance** ($Z = R + jX$, using $j$ instead of $i$ to avoid confusion with current $i$).
2. **Quantum Mechanics**:
   The state of a quantum physical system is described by a wave function $\Psi$, which is inherently complex-valued. Schrödinger's equation explicitly relies on the imaginary unit $i$.
3. **Signal Processing & Control Systems**:
   Fourier transforms decompose raw signals into sine and cosine components using complex exponentials, facilitating modern digital audio, video, and wireless communication.
