---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
author_profile: true
---
# The Geometry and Algebra of Complex Numbers

Complex numbers expand our mathematical horizon. Beyond their algebraic utility, they offer an elegant geometric framework bridging algebra, geometry, and trigonometry.

---

## 1. Introduction and Definitions

A **complex number** $z$ is written in the algebraic form:

$$
z = a + bi
$$

where:
* $a = \text{Re}(z)$ is the **real part** of $z$.
* $b = \text{Im}(z)$ is the **imaginary part** of $z$.
* $i$ is the **imaginary unit**, defined by:

$$
i^2 = -1
$$

---

## 2. Geometric Representation: The Complex Plane

Complex numbers are visualized on a two-dimensional Cartesian plane called the **Complex Plane** or **Argand Diagram**. 

* The horizontal axis is the **Real Axis** ($\text{Re}$).
* The vertical axis is the **Imaginary Axis** ($\text{Im}$).



### Modulus and Argument
The vector representing $z = a + bi$ has two key geometric properties:
1. **Modulus (Absolute Value) $|z|$**: The distance from the origin.
   $$r = |z| = \sqrt{a^2 + b^2}$$
2. **Argument $\theta$**: The angle formed with the positive real axis.
   $$\theta = \tan^{-1}\left(\frac{b}{a}\right)$$

---

## 3. Algebraic Operations

### Addition and Subtraction
Addition and subtraction are performed component-wise:

$$
(a + bi) \pm (c + di) = (a \pm c) + (b \pm d)i
$$

**Geometric Interpretation:** Addition corresponds to **vector addition** following the Parallelogram Law:



### Multiplication
Apply the distributive property (FOIL) and substitute $i^2 = -1$:

$$
(a + bi)(c + di) = (ac - bd) + (ad + bc)i
$$

### Complex Conjugate
The conjugate of $z = a + bi$, denoted by $\bar{z}$, is:

$$
\bar{z} = a - bi
$$

Multiplying a number by its conjugate always yields a non-negative real number: $z \cdot \bar{z} = |z|^2$.

---

## 4. Exponential Form (Euler's Formula)

By utilizing Taylor series, Leonhard Euler derived the relation:

$$
e^{i\theta} = \cos\theta + i\sin\theta
$$

Thus, any complex number can be compactly represented in **exponential form**:

$$
z = r e^{i\theta}
$$

Using this form makes **multiplication** and **division** exceptionally easy:
* **Multiplication**: $z_1 z_2 = r_1 r_2 e^{i(\theta_1 + \theta_2)}$
* **Division**: $\frac{z_1}{z_2} = \frac{r_1}{r_2} e^{i(\theta_1 - \theta_2)}$
