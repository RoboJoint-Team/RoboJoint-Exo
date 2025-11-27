## Part.01: Problem Definition, Problem Conversion, Problem Details, and Software Architecture 

### Table of contents:
  * **1.1 A brief list of problems for preview.**
  * **1.2 Detailed problems analysis and Conversion into an Engineering Problem.**
  * **1.3 Problem Sets and Problem-problem relationship through scientific modelling.**
  * **1.4 Software Architectural Design: Subsystems, Components, Modules and Teams.**
  * **References**

### 1.1 A brief list of problems for preview
* **MCA Stroke syndromes** affecting the Middle Cerebral a. (MCA) territories damage the internal capsule fibres, and/or the projecting corona radiata from the motor cortex of the paracentral lobule that is responsible for controlling the lower extremities.
* **ACA Stroke syndromes** affecting the Anterior Cerebral a. (ACA) territories directly damage the paracentral lobules in the frontal cortex; the motor cortex responsible for the innervation of the lower extremities motor system.
* **Spinal traumatic and vascular syndromes** affecting the anterior segment of the cord (Spinal Anterior segmental syndromes) break the circuit between the descending Corticospinal tracts and the Anterior gray horn cells that innervate the motor-end plates providing the Volitional Skilled Muscular Supply for the lower limbs.
* **Spinal traumatic and vascular syndromes** affecting the anterior segment of the cord (Spinal Anterior Segmental Transection syndromes) affect the Anterior Spinocerebellar tracts (from L1 to S2) affecting the coordinated movement and posture of the entire lower extremity.
* **Local joint diseases** including ligamentous rupture or tears lead to joint instability affecting the patient life.
* **Local joint diseases or systemic diseases** affecting the lower extremity could lead to chronic immobility disorders resulting in venous stasis and by virtue vascular endothelial inflammatory reactions and thrombosis (i.e., deep venous thrombosis).
* **Deep venous thrombosis** is one of the major leading risk factors for recurrent cerebrovascular and coronary strokes, and pulmonary embolisms.

### 1.2 Detailed problems analysis and Conversion into an Engineering Problem

The problem is composed of rigid components; there are 2 bones and one axis forming each joint. For a joint to work, there must be one static bone and another dynamic bone moving about the joint axis. The range of motion of the dynamic part is determined by angles in radian.

> [!IMPORTANT]
> The following are the components for a mathematical model of the joint module; they could be replicated in any R vectorspace.
> * Components:
> 1) Static Bone.
> 2) Dynamic Bone.
> 3) Joint Axis.
> 4) External Force (Centeripetal or Linear).
> 5) Axis of applying the force on the dynamic bone (rigid axis).
> 
> **Mathematical Concepts utilized in this document:**
> * Vectorial Analysis of Forces.
> * Vector product.
> * Dot product.
> * Projection Vectors.
> * Representing vectors using projections on Vectorial Axes.
> * Rotation vector.
> * Matrices Operations.
> * Euler angles and Rotation Matrices.
>
> **Concepts of classic Newtonian mechanics utilized in this document:**
> * Newton's First Law of Motion (Inertial Reference Frames).
> * Newton's Second Law of Motion (Force-Acceleration Pairing and Equilibrium).
> * Newton's Third Law of Motion (Action-Reaction Forces Pair).
> * Fundamental Theorem of Calculus (Derivation and Anti-derivation).
> * Centripetal Force.
> * Centripetal Acceleration.
> * Tangential Acceleration.
> * Tangential Force.
> * Resultant Force.
> * Resultant Acceleration.
> * Torque and angular momentum.
> 
> Rigid bodies are protected from moving in a space by the act of the equilibrium of forces acting on them according to Newton's second 
> law of motion; that is if a new external force is applied to the system, it will an inbalance in the system which will cause an acceleration
> recorded as a derivative of a change in displacement in a time interval. If angular motion is desired, that force should be calculated from
> the derivative of the change in displacement in a time interval of that object.
>
> The resultant force that should act on the object to cause angular motion is composed of a centripetal component and a linear component that
> are perpendicular to one another.
>

### 1.3 Problem Sets and Problem-problem relationship through scientific modelling

* Graphical Visualization of the biomechanics of the normal Knee joint (Joint Kinematics):
(DONE)

* Visualization of the biomechanics of the normal Knee joint:
(DONE)

* Mathematical Model of rotation in R(2) and R(3) vectorspaces:
The mathematical model is based on the vector rotational transformation model that attains rotation of the vector by rotating its components; by constructing a rotation matrix from the angle of rotation; the following components are invovled:
1) **The vector (v)**: denoting the rectangular coordinates of the local translation of the object in the vector-space.
2) **The angle** ($\phi_{R}$): denoting the the angle of rotation to be applied on that object in the vector-space.
3) **The polar vector** ($v_{polar}$): denoting the polar coordinates of that vector (v) in the vector-space.
4) **The rotation matrix** ($R$): is a `2x2` matrix for R(2) vectorspace, and `3x3` matrix for R(3) vectorspace; it establishes rotation by rotating the components of the vector components (i.e., For R(2): the $\vec{Vx\\_{Vx}}$, and $\vec{Vx\\_{Vy}}$).
5) **The vector prime (v'):** denoting the new local translation of the object in the vector-space as a result of the applied rotational motion.

#### The mathematical model of rotating vectors around a prime axis:

* Let vector $\vec{V}$ be a vector in an $R^3$ vectorspace; such that:

$$
\vec{V} = \begin{pmatrix}
\|\vec{V}\| \cdot \cos(\phi_{(\vec{V}, \vec{V}_x)}) \\
\|\vec{V}_{yz}\| \cdot \cos\left(\frac{\pi}{2} - \phi_{(\vec{V}_{yz}, \vec{V}_z)}\right) \\
\|\vec{V}_{yz}\| \cdot \cos(\phi_{(\vec{V}_{yz}, \vec{V}_z)})
\end{pmatrix}
$$

* Therefore, the rotated vector around the X-axis using angle $\phi_R$ with the positive direction of Z-axis (Z-convention) using the direction cosines methodology; could be rewritten as a function of the rotational angle by evaluating the addition trigonometric identity using the Euclidean Geometry:

$$ 
\vec{V}^{'} = \begin{pmatrix}
\|\vec{V}\|\cos(\phi_{(\vec{V}, \vec{V}_x)}) \\
\|\vec{V}_{yz}\|(\sin(\phi_{(\vec{V}_{yz}, \vec{V}_z)})\cos(\phi_{R}) \pm \cos(\phi_{(\vec{V}_{yz}, \vec{V}_z)})
                \sin(\phi_{R})) \\
\|\vec{V}_{yz}\|(\cos(\phi_{(\vec{V}_{yz}, \vec{V}_z)})\cos(\phi_{R}) \mp \sin(\phi_{(\vec{V}_{yz}, \vec{V}_z)})
            \sin(\phi_{R})) \\
\end{pmatrix}
$$


* The rotated vector around the X-axis with Z-convention expressed in direction cosines; could be further rewritten using matrix algebra into a **matrix product of a rotation matrix and the vector column matrix**; where $R_x$ is the rotation matrix around X-Axis with Z-convetion:

$$
\vec{V}^{'} = R_x(\pm \hat{\Phi_R}) \times \vec{V} \\
            = \begin{pmatrix}
                1 & 0 & 0 \\
                0 & \cos(\phi_{R}) & \pm \sin(\phi_{R}) \\
                0 & \mp \sin(\Phi_R) & \cos(\phi_{R})
              \end{pmatrix} 
              \times
              \begin{pmatrix}
               \|\vec{V}\|\cos(\phi_{(\vec{V}, \vec{V}_x)}) \\
               \|\vec{V}_{yz}\|\sin(\phi_{(\vec{V}_{yz}, \vec{V}_z)}) \\
               \|\vec{V}_{yz}\|\cos(\phi_{(\vec{V}_{yz}, \vec{V}_z)})
              \end{pmatrix}
$$

$$
= \begin{pmatrix}
    1 & 0 & 0 \\
    0 & \cos(\phi_{R}) & \pm \sin(\phi_{R}) \\
    0 & \mp \sin(\Phi_R) & \cos(\phi_{R})
\end{pmatrix} 
    \times
\begin{pmatrix}
   \cos(\phi_{(\vec{V}, \vec{V}_x)}) \\
   \sin(\phi_{(\vec{V}_{yz}, \vec{V}_z)}) \\
   \cos(\phi_{(\vec{V}_{yz}, \vec{V}_z)})
\end{pmatrix}
    \times 
\begin{pmatrix}
  \|\vec{V}\| \\
  \|\vec{V}_{yz}\| \\
  \|\vec{V}_{yz}\|
\end{pmatrix}^\top
$$

* Therefore, the rest of rotation operations could be expressed using rotation matrices as follows:
  * Rotation around Y-axis (**X-convention**):
  
$$
\vec{V}^{'} = R_y(\pm \hat{\Phi_R}) \times \vec{V} \\
            = \begin{pmatrix}
                \|\vec{V}_{xz}\|(\cos(\phi_{R})\cos(\phi_{(\vec{V}_{xz}, \vec{V}_x)}) \mp 
                \sin(\phi_{R})\sin(\phi_{(\vec{V}_{xz}, \vec{V}_x)})) \\
                \|\vec{V}\|\cos(\phi_{(\vec{V}, \vec{V}_y)}) \\
                \|\vec{V}_{xz}\|(\pm \sin(\phi_{R})\cos(\phi_{(\vec{V}_{xz}, \vec{V}_x)}) + \cos(\phi_{R})\sin(\phi_{(\vec{V}_{xz}, \vec{V}_x)})) 
              \end{pmatrix}
$$

$$
= \begin{pmatrix}
    \cos(\phi_R) & 0 & \mp \sin(\phi_R) \\
    0 & 1 & 0 \\
    \pm \sin(\phi_R) & 0 & \cos(\phi_R)
\end{pmatrix} 
    \times
\begin{pmatrix}
    \cos(\phi_{(\vec{V}_{xz}, \vec{V}_x)}) \\
    \cos(\phi_{(\vec{V}, \vec{V}_y)}) \\
    \sin(\phi_{(\vec{V}_{xz}, \vec{V}_x)})
\end{pmatrix}
    \times 
\begin{pmatrix}
    \|\vec{V}_{xz}\| \\
    \|\vec{V}\| \\
    \|\vec{V}_{xz}\|
\end{pmatrix}^\top
$$

  * Rotation around Z-axis (**X-Convention**) using direction cosines:

$$
\vec{V}^{'} = R_z(\pm \hat{\Phi_R}) \times \vec{V} \\
            = \begin{pmatrix}
                \|\vec{V}_{xy}\|(\cos(\phi_{R})\cos(\phi_{(\vec{V}_{xy}, \vec{V}_x)}) \mp 
                \sin(\phi_{R})\sin(\phi_{(\vec{V}_{xy}, \vec{V}_x)})) \\
                \|\vec{V}_{xy}\|(\pm \sin(\phi_{R})\cos(\phi_{(\vec{V}_{xy}, \vec{V}_x)}) + \cos(\phi_{R})\sin(\phi_{(\vec{V}_{xy}, \vec{V}_x)})) \\
                \|\vec{V}\|\cos(\phi_{(\vec{V}, \vec{V}_z)})
            \end{pmatrix}
$$

$$
= \begin{pmatrix}
    \cos(\phi_R) & \mp \sin(\phi_R) & 0 \\
    \pm \sin(\phi_R) & \cos(\phi_R) & 0 \\
    0 & 0 & 1
  \end{pmatrix} 
      \times
  \begin{pmatrix}
    \cos(\phi_{(\vec{V}_{xy}, \vec{V}_x)}) \\
    \sin(\phi_{(\vec{V}_{xy}, \vec{V}_x)}) \\
    \cos(\phi_{(\vec{V}, \vec{V}_z)}) \\
  \end{pmatrix}
      \times 
  \begin{pmatrix}
    \|\vec{V}_{xy}\| \\
    \|\vec{V}_{xy}\| \\
    \|\vec{V}\|
  \end{pmatrix}^\top
 $$

  * A set of rotations could be achieved by multiplying the rotation matrices to get the final rotation matrix, and then multiply it with the vector coordinates.

> [!TIP]
> **Proof:**
> * The rotation matrix could be derived from the result of the addition trigonometric identities retrieved after adding the angle $\phi_{R}$ to the initial angle $\phi_{0}$.
> * The resulting vector (v') could be obtained by other means: 
>    1) Adding the angle of rotation to the initial angle and constructing the rectangular coordinates from the polar vector.
>    2) Deriving the final vector (v') by evaluating the addition trigonometeric identities (i.e., $\cos(\phi_0 \pm \phi_R)$ and $\sin(\phi_0 \pm \phi_R)$ ).

* Mathematical Modelling: Errors of Rotation and Error Handling Techniques.


* Mathematical-Physical Model of angular (or rotational) motion in R(2) and R(3) vectorspaces:
(WIP)

* Mathematical model of the biomechanics of the normal Knee joint:
(WIP)

* Visualization of the biomechanics of the Knee joint in a patient of Knee Instability:
(WIP)

* Software Architectural Design of the involved subsystems and components:

<img src="solution-design.svg">

### References
1) [Harrison's Principles of Medicine $20^{th}$ edition](https://accessmedicine.mhmedical.com/content.aspx?bookId=2129&sectionId=159213747)
2) [Thomas' Calculus](https://www.pearson.com/en-us/subject-catalog/p/thomas-calculus/P200000007103/9780137616077)
3) [Principles of Physics: A Calculus-Based Text, Serway and Jewett](https://faculty.cengage.com/works/9781133104261)
4) [Applied Linear Algebra, Springer](https://link.springer.com/book/10.1007/978-3-319-91041-3)
5) [Handbook of Mathematics, Springer](https://link.springer.com/book/10.1007/978-3-662-46221-8)
6) [Spinal Cord Injuries](https://www.ncbi.nlm.nih.gov/books/NBK560721/)
7) [Medical and Biological Engineering and Computing: Use of cardan angles to locate rigid bodies in three-dimensional space](https://link.springer.com/article/10.1007/BF02441745)