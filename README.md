# RoboJoint-Exo
> Keywords: Exoskeleton - Musculoskeletal System - Cerebrovascular Strokes - Hemiplegia - System Disease - Rehabilitation Therapy

A micro-smart bionic joint interface system emulating the biomechanics of human joints integrating AI models for augmentation of balance and smoothening of tone emulating the fine-grained smooth control of the human cerebellum.

## Preface
RoboJoint-Exo features exoskeleton system implementation through connecting human body joints together via a single CPU/MCU by employing interconnected joint modules and synchronizing them through interrupt I/O and I/O polling.

The project aims at providing a reliable framework to build robust human exoskeletons that supports the joints of the appendicular skeleton; which are severly imparied in morbid disorders; of the most of them are the stroke syndromes affecting the Middle and Anterior Cerebral circulations, and anterior cord syndromes irrespective of the cause. In addition, the project provides compatibility for other localized joint disorders including; ligametnous tears and joint instabilities, but excluding advanced knee osteoarthritis and fractures of long bones.

## Preview
### Medical Condtions
The following brief list of medical conditions are the ones to be addressed by the project; of which some are systemic disorders, while others are localized ones:
1) Patients in state of **hemiplegia** or **hemiparesis**; as a result of cerebrovascular or spinovascular stroke syndromes affecting the MCA/ACA/Anterior Spinal a. vascular territories or as a result of spinal cord transection syndromes (Systemic Disease).
2) Patients with joint instability disorders; as a result of cartilaginous and ligamentous ruptures or tears (Localized Disorders).
3) Patients with MCA/ACA stroke syndromes requiring early rehabilitation therapy to avoid further muscle wasting. (Systemic Disease).
4) In patients with MCA/ACA stroke syndromes, co-morbidities for further Stroke syndromes could occur as a result of immobility and vascular endothelial injury; the device will help avoid the most commonly occuring co-morbidities (Deep Venous Thrombosis -- DVT) as a result of immobility (Systemic Disease)
5) In children with **quadriplegia** or **quadriparesis**; the device may give some hope by adding some artificial tones to the joints of the appendicular skeleton (Systemic Disease).

### Device Mechanics
The general layout proposed for the device is (See Fig.):

1) Multiple joint modules; each module controlling a joint in the lower extremity (e.g., Hip and Knee Modules).
2) A single CPU/MCU module connecting these modules to a single unit.
3) Joint modules are powered by a large torque stepper motors in multiple planes analogous to the joint normal planes.
4) Joint modules are powered by sensor components (e.g., Gyroscopes and Geomagnetic sensors) to detect the joint position and report it back to the CPU module.
5) AI software modules are provided and installed on the CPU/MCU module; providing balancing system by simultaneously controling different stepper motors from different planes; in addition to smoothening the interpolation of motion, therefore providing a substitute for the cerebellar and dorsal column proprioceptive functions that control the muscles tone and keep track of the muscle spatial and temporal position.

<img width="1071" height="404" alt="graphviz" src="https://github.com/user-attachments/assets/0d87c8e2-c447-448c-a6db-f353208bce58" />

### Joint Modules Mechanics Examples:
https://github.com/user-attachments/assets/fdeb4a84-2ae8-438b-98f6-9c01f6907325

https://github.com/user-attachments/assets/419610a7-11cb-4b3e-aa0f-cdb20b26bf9a

## Table of contents:
### Part.01: Problems 
  * 1.1 A brief list of problems for preview.
  * 1.2 Detailed problems analysis.
  * 1.3 Problem Sets.
  * 1.4 Problem-problem relationship.
### Part.02: Solutions
  * 2.1 A brief list of solution mappings to the problems.
  * 2.2 Detailed Solution analysis.
  * 2.3 Solution Sets.
  * 2.4 Derivation of System Components.
  * 2.5 Derivation of component-component relationships.
### Part.03: Requirements
  * 3.1 Software functional requirements.
  * 3.2 Software Simulation Specification document.
  * 3.3 Physics and Vector Maths Specification document.
  * 3.4 Employment of AI Software Modules for fine-grained control.
  * 3.5 Hardware functional requirements.
  * 3.6 Hardware-Software Specification document.
  * 3.7 Hardware-software co-design in simulation environment.
  * 3.8 Employment of AI Modules for fine-grained control.
  * 3.9 Hardware-Software Non-functional requirements.
### Part.04: Circuit Design and Hardware-Software Implementation
WIP

