# CV_SADIA
# Satellite Vegetation Health Classification with YOLO26

## Project Overview
This beginner-friendly computer vision project classifies Sentinel-2 satellite image patches into **healthy** or **stressed** vegetation using Ultralytics **YOLO26n Classification**.

## Problem Description
Vegetation stress monitoring can support agriculture and environmental monitoring. The project demonstrates a complete pipeline from satellite data to prediction.

**Important:** EuroSAT does not provide real healthy/stressed ground-truth labels. This educational project creates proxy labels using mean NDVI. Therefore, the result is a course demonstration and should not be treated as a validated crop-stress diagnostic system.

## Dataset & Model Used
- Dataset: EuroSAT multispectral Sentinel-2 imagery.
- Original project: phelber/EuroSAT on GitHub.
- Colab-friendly mirror used by the notebook: giswqs/EuroSAT_MS.
- Selected vegetation classes: AnnualCrop, Forest, HerbaceousVegetation, Pasture, PermanentCrop.
- Proxy label: image mean NDVI split at the dataset median.
- Model: Ultralytics YOLO26n-cls pretrained classification model.

## Workflow / Architecture
Sentinel-2 multispectral images
→ select vegetation classes
→ calculate NDVI
→ create healthy/stressed proxy labels
→ convert B04/B03/B02 to RGB
→ train/validation/test split
→ YOLO26n-cls fine-tuning
→ evaluation
→ prediction
→ ONNX export

## Results & Evaluation
Run the notebook to generate:
- Top-1 classification accuracy
- Training curves
- Confusion matrix
- Successful prediction example
- Failure case example


## Technologies Used
- Python
- Google Colab
- Ultralytics YOLO26
- PyTorch
- Hugging Face Datasets
- NumPy
- Pillow
- Matplotlib

## How to Run the Project
1. Upload/open `Satellite_Vegetation_Stress_YOLO26.ipynb` in Google Colab.
2. Select a GPU runtime.
3. Run all cells from top to bottom.
4. Start with 10 epochs for a classroom demonstration.
5. Increase epochs or `MAX_IMAGES` if you have more time.

## Deployment / Optimization
The notebook exports the trained model to ONNX.

## Future Improvements
- Replace NDVI proxy labels with field-validated healthy/stressed labels.
- Use time-series Sentinel-2 imagery.
- Use multispectral bands directly instead of only RGB during YOLO training.
- Add NDMI, red-edge, and SWIR information.
- Compare against a CNN or transformer baseline.

## Repository Structure
```text
.
├── Satellite_Vegetation_Stress_YOLO26.ipynb
├── README.md
└── requirements.txt
```

## SDAIA Academy GitHub Repository Link
https://github.com/SDAIAAcademy
