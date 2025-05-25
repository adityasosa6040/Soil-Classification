
Team Name :- Project Mayhem

Team Members 
  1. Prajwal Warade
  2. Aditya Sosa
  3. Akash Venkatesh
  4. Shubham Malviya
  5. Sandip Dalvi

**Simple Transcript of the Code:**

1. **Clean Working Directory**  
   - Deletes all existing files/folders in `/kaggle/working/` to start fresh.  
   - *Output*: "Contents cleared."

2. **Setup & Data Preparation**  
   - Imports libraries (Pandas, PyTorch, etc.) and defines a custom `SoilDataset` class to load soil images and labels.  
   - Applies image preprocessing: resizes images to 224x224, normalizes, and adds GPU-based augmentations (flips, rotations, blur).  
   - Splits data into 80% training and 20% validation sets.  
   - Loads a pretrained ResNet18 model and configures it for GPU training.  
   - *Output*: "Images saved" and warnings about dataloader workers.

3. **Model Training**  
   - Trains the model for 50 epochs using the Adam optimizer and CrossEntropy Loss.  
   - Implements early stopping (patience=10) if validation loss doesn’t improve.  
   - Saves the best model (`best_model.pth`) based on validation loss.  
   - *Output*: Training/validation losses per epoch. Early stopping triggers at epoch 47.

4. **Model Evaluation**  
   - Loads the best model and evaluates it on the validation set.  
   - Computes F1 scores for each soil class and the macro average.  
   - *Output*: F1 scores (Alluvial: ~0.98, Black: ~0.99, Clay: ~0.96, Red: ~1.0; Macro Avg: ~0.98).

5. **Generate Predictions for Test Set**  
   - Uses the trained model to predict labels for unseen test images.  
   - Saves predictions to `submission.csv` with filenames and predicted soil types.  
   - *Output*: "submission.csv generated."

**Key Takeaways**  
- Achieves high accuracy (F1 ~0.98) on validation data.  
- Uses GPU acceleration for faster training and augmentations.  
- ResNet18 with pretrained weights and fine-tuning works well for small datasets.  
- Final predictions are exported for competition submission.

# Leaderboard
- F1 Score :- 0.9285
