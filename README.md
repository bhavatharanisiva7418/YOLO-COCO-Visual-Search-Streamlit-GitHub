# YOLO-COCO-Visual-Search-Streamlit-GitHub
## 1. Project Title
YOLO-COCO Visual Search and Filtering Application Using Streamlit

## 2. Abstract / Introduction
This project implements a complete visual search system built on top of a YOLOv11 object detection model pretrained on the COCO dataset. The application runs entirely through a Streamlit web interface, allowing users to:

 - Perform object detection on a directory of images
 - Automatically generate metadata including detected object classes, bounding boxes, and object counts
- Load existing metadata to avoid reprocessing
- Search images based on selected COCO classes
- Apply count-based filters and logical search modes (OR / AND)
- Display results in an optimized image grid
- Export results as JSON
The goal is to create a lightweight yet powerful visual search engine that works fully on CPU and is easy to deploy using Streamlit.

## 3. Dataset and YOLO Model Details (COCO)
## COCO Dataset
The COCO dataset (Common Objects in Context) contains:

- 80 object classes
- Over 118,000 training images
- 5,000 validation images
The validation subset coco-val-2017-500 is included in the repository for demo purposes.

# YOLO Model
This project uses:

- YOLOv11m.pt
- Pretrained on COCO 2017
- Supports 80 object categories
- Works on CPU without CUDA
- The inference wrapper is implemented in src/inference.py.

# 4. Environment Setup
# Install Dependencies
Create a Python environment (recommended) and install dependencies:

```
pip install -r requirements.txt
```
Make sure the following libraries are installed:

- streamlit
- ultralytics (for YOLOv11)
- pillow
- pyyaml

If any library is missing, install manually:
```
pip install ultralytics streamlit pillow pyyaml
```
# 5. CPU Installation Steps (No GPU Required)
This project is designed to run fully on CPU.

# Confirm CPU Mode for YOLOv11
Open src/inference.py and ensure the following line is present:
```
device='cpu'
```
Ultralytics automatically falls back to CPU if no CUDA is available.

No GPU installation or CUDA toolkit is required.

# 6. How to Run in VS Code Using Conda
# Step 1 — Create a Conda Environment
```
conda create -n yolosearch python=3.10 -y
conda activate yolosearch
```

# Step 2 — Install Dependencies
```
pip install -r requirements.txt
```

# Step 3 — Open the Folder in VS Code
```
File → Open Folder → Select project directory
```

# Step 4 — Run the Application
From VS Code Terminal:
```
streamlit run app.py
```

# 7. How to Deploy Using Streamlit
# Local deployment
Simply run:
```
streamlit run app.py
Streamlit will automatically launch the UI in your browser (default: http://localhost:8501).
```

# For remote deployment (Streamlit Community Cloud)
1.Push the repository to GitHub
2.Visit: https://share.streamlit.io
3.Connect your GitHub repo
4.Set entry point = app.py
5.Deploy
The app will run fully on CPU.

# 8. Output:
# Result:
The project demonstrates that a complete visual search engine can be built using:

- YOLOv11 pretrained models
- Lightweight Streamlit UI
- CPU-only execution
- Metadata-driven filtering
- The search system is fast, intuitive, and scalable to larger datasets. By decoupling detection from search using JSON metadata, users can easily re-run searches without repeating expensive inference.


