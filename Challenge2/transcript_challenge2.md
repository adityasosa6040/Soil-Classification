
Team Name :- Project Mayhem

Team Members 
  1. Prajwal Warade
  2. Aditya Sosa
  3. Akash Venkatesh
  4. Shubham Malviya
  5. Sandip Dalvi

# Code Transcript: Soil vs Non-Soil Classification

# Data Preparation

- Preprocess soil images via resizing/centercropping to 224x224

- Create SoilDataset for loading normalized RGB images and labels

# Feature Extraction

- Use ResNet-18 (pretrained on ImageNet) with final classification layer removed

- Extract flattened features (512-dim) from penultimate layer

# Anomaly Detection Training

- Train a One-Class SVM on soil features to learn "normal" soil patterns

# Inference Pipeline

- Preprocess test images identically to training

- Extract features using modified ResNet

- Predict "soil" (1) or "non-soil" (0) via SVM decision boundary

# Output

- Save predictions to submission.csv with image_id and binary label

# Key Techniques:

- Transfer learning from ResNet for feature representation

- One-class classification for outlier (non-soil) detection

# Execution Flow:
# Preprocess → Extract Features → Train SVM → Predict → Save Results

# Leaderboard
- F1 Score :- 0.8288
