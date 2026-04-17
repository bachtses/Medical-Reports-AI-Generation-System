# Medical Reports AI Generation System

## Overview

This project implements an automated medical report generation pipeline that integrates outputs from multiple AI models and produces structured clinical reports in both PDF and XML formats.

The system combines classification results, segmentation outputs, and spatial analysis to generate human-readable medical summaries aligned with clinical reporting standards.

<img width="914" height="391" alt="image" src="https://github.com/user-attachments/assets/c471ce7d-816f-494b-b5f3-0f6796eb7759" />



## Concept

The pipeline simulates a real-world clinical workflow:

1. AI models analyze medical images (mammography / MRI)
2. Predictions are exported as JSON outputs
3. The system aggregates results
4. A structured clinical report is generated automatically


## Pipeline Architecture

- **Input Models**
  - Healthy / Non-Healthy classification
  - BIRADS classification
  - Breast density estimation
  - Cancer staging prediction
  - Lesion segmentation

- **Processing Layer**
  - JSON parsing
  - Spatial analysis (OpenCV)
  - Rule-based medical interpretation

- **Output**
  - PDF clinical report (human-readable)
  - XML report (HL7-like structure)


<img width="738" height="270" alt="image" src="https://github.com/user-attachments/assets/69fabe7e-f00e-4fe8-bb35-973ae25d589d" />



## Key Features

- Multi-model AI integration
- Automated clinical report generation
- Spatial tumor analysis (size, location)
- Standardized medical sentence generation
- Dual output format:
  - PDF (for clinicians)
  - XML (for systems / interoperability)

<img width="954" height="456" alt="image" src="https://github.com/user-attachments/assets/edf80614-ae30-465f-af77-69d9f973870b" />


## Spatial Analysis

The system processes segmentation masks to extract:

- Tumor presence detection
- Region of interest (ROI)
- Tumor size (cm)
- Tumor location (quadrant-based)

Uses:
- Contour detection (OpenCV)
- Geometric estimation (circle approximation)
- Pixel-to-mm conversion


## Input Format

Each AI model exports predictions as JSON:

{
  "value": "birads prediction",
  "probability": [0, 0, 1, 0, 0]
}

Segmentation is provided as:

Binary mask image (.png)


## Output
PDF Report
- Structured clinical report
- Includes:
- Patient info
- Model results
- Medical interpretation
- Visual references

XML Report
- HL7-like structured format
- Suitable for:
- Integration with medical systems
- Data exchange
- Report Generation Logic

<img width="714" height="377" alt="image" src="https://github.com/user-attachments/assets/87891248-165e-4288-963f-bdf63fbf3d74" />


## The system combines:

Model predictions
Segmentation results
Predefined medical knowledge templates

To generate clinically meaningful sentences such as:

Diagnosis indication
Risk category (BIRADS)
Density classification
Tumor staging
Tumor location

<img width="722" height="341" alt="image" src="https://github.com/user-attachments/assets/b5e0e1a7-cea4-4ee1-aeed-97e5f7e4e539" />


## Tech Stack

Python, OpenCV (image processing), NumPy, Matplotlib, ReportLab (PDF generation), XML (ElementTree)


## How to Run

Place model outputs in respective folders:
JSON files
Segmentation image

Run:
python medical_report_component.py

Outputs generated in:
Results/


## Use Cases

AI-assisted radiology workflows
Clinical decision support systems
Medical AI pipelines integration
Research on automated report generation


## Disclaimer

This project is for research and development purposes only and does not replace professional medical diagnosis.


<img width="695" height="368" alt="image" src="https://github.com/user-attachments/assets/f51f8dc4-cee2-4569-a1e8-82eb3418def8" />
