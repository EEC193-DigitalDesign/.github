# EEC193-DigitalDesign

Senior design repositories for **Team Thomas**, advised by **Professor Anthony Thomas** at UC Davis.

> **2026 ECE Outstanding Senior Design Project Award Winner**

This organization documents our work for **EEC 193**, an independent team design project for seniors in Electrical or Computer Engineering. Our team was interested in digital logic, RTL/HDL development, FPGA implementation, object detection, image processing, and hardware acceleration.

Our workflow was modeled after the structure of UC Davis **EEC 181A/B - Digital Systems Design Project**, a previous digital systems design course taught by **Professor Bevan Baas**:

https://www.ece.ucdavis.edu/~bbaas/181/

The repositories are organized into two major phases: individual lab development and collaborative final-project development.

## Project Materials

### [`final-design`](../final-design)

Main senior design repository.

This repo contains the full FPGA implementation for **Real-Time Object Detection using Matched Filtering on FPGA**. The design targets the DE1-SoC board with the Terasic D8M camera and implements a streaming hardware pipeline for object detection using grayscale conversion, Gaussian blur, Sobel edge detection, sparse template matching, thresholding, and VGA debug output.

This is the primary repository for the completed system.

### [`final-poster`](../final-poster)

Final poster repository.

This repo contains the final senior design poster, figures, diagrams, and presentation materials used to summarize the project architecture, implementation, results, and contributions.

### [Final paper](../final-design/blob/main/docs/TeamThomas_FinalPaper.pdf)

Final paper.

A detailed technical report documenting the motivation, RTL architecture, image-processing pipeline, sparse matched filter detector, simulation strategy, hardware implementation, and results of our FPGA real-time object detection system.

## Repository layout

## Phase 1 — Individual lab development

The early repositories contain individual lab work completed while learning and practicing FPGA-based digital design. These labs helped build experience with Verilog/HDL design, simulation, board bring-up, VGA output, camera input, digital logic, and hardware debugging.

Each team member’s lab work was kept in their own branch when applicable.

Lab repositories:

- `lab1`
- `lab2`
- `lab3`
- `lab4`
- `lab5`

## Phase 2 — Collaborative project development

After the individual lab phase, the team moved into shared project development. These repositories contain prototype designs, experiments, system-level integration work, and final project deliverables.

Project and prototype repositories include:

- `edge-detector` — early image-processing and Sobel edge-detection work
- `matched-filter` — initial matched-filter object-detection exploration
- `matched-filterFFT` — frequency-domain matched-filter exploration
- `design-systolic` — systolic-array matched-filter prototype
- `final-design` — completed FPGA object-detection system
- `final-poster` — final poster and presentation materials

## Final project summary

Our final project implements real-time object detection directly in FPGA hardware. Instead of sending frames to a CPU or GPU for software processing, the design processes the live camera stream through a custom RTL pipeline.

At a high level, the system performs:

```text
D8M Camera
  -> RGB to grayscale downsampling
  -> Gaussian blur
  -> Sobel edge detection
  -> Sparse matched-filter scoring
  -> Frame-level detection
  -> VGA debug display
```

The goal was to explore whether a lightweight, template-based object detector could run in real time using a streaming FPGA datapath and limited on-chip resources.

## Team Thomas

- Yaseen Alkhameri
- Justin Hsu
- Ricardo Gonzales
- Max Madrigal
- Isidro Pulido
