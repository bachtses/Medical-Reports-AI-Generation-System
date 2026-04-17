# Medical AI Report Generation Pipeline

## Overview

This project implements an automated medical report generation pipeline that integrates outputs from multiple AI models and produces structured clinical reports in both PDF and XML formats.

The system combines classification results, segmentation outputs, and spatial analysis to generate human-readable medical summaries aligned with clinical reporting standards.


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


## Key Features

- Multi-model AI integration
- Automated clinical report generation
- Spatial tumor analysis (size, location)
- Standardized medical sentence generation
- Dual output format:
  - PDF (for clinicians)
  - XML (for systems / interoperability)


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


## Tech Stack

Python
OpenCV (image processing)
NumPy
Matplotlib
ReportLab (PDF generation)
XML (ElementTree)


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

