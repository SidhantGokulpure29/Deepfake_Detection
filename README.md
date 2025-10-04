# Deepfake Detection System 
### 🎯 *Project Goal*

> To build a deep learning pipeline that detects deepfake videos by classifying facial images extracted from video frames as *real* or *fake* using a CNN model.

### 🔄 *Workflow Summary*

#### *1. Dataset & Metadata Handling*

* Started with labeled video data (REAL/FAKE) and a metadata file.
* Used pandas to read metadata and ensure clean labels for *supervised classification*.

🧠 ML Term: Label Encoding

---

#### *2. Frame Extraction*

* Used OpenCV to extract frames from videos (e.g., 1 per second) for efficiency.
* Ensures *feature sampling* across the video timeline.

---

#### *3. Face Detection with MTCNN*

* Detected and cropped face regions using *MTCNN*, a pretrained CNN-based face detector.
* Focused only on the *Region of Interest (ROI)* — the face.

---

#### *4. Data Preparation*

* Saved cropped faces into labeled folders (real/fake).
* Applied image transformations: resizing and normalization using PyTorch.

🧠 ML Terms: Preprocessing, Normalization

---

#### *5. Model Training (ResNet-18)*

* Used *transfer learning*: loaded a pretrained ResNet-18 model (trained on ImageNet).
* Replaced the final layer and *fine-tuned* it for binary classification.

🧠 DL Terms: CNN, Transfer Learning, Fine-tuning

---

#### *6. Training Loop & Optimization*

* Trained using *Cross-Entropy Loss* and the *Adam optimizer*.
* Tracked training and validation accuracy and loss over multiple *epochs*.

🧠 ML Terms: Loss Function, Optimizer, Backpropagation

---

#### *7. Evaluation*

* Assessed performance on a validation set using:

  * Accuracy
  * Confusion matrix
  * (Optional) ROC-AUC

---

#### *8. Model Saving & Inference*

* Saved the trained model using torch.save().
* Built an *inference pipeline* to classify faces from new videos.

---

### ✅ *Key Highlights*

* Used *MTCNN* for high-quality face extraction.
* Leveraged *ResNet + transfer learning* for efficient training.
* Designed the pipeline to be *modular, scalable, and production-ready*.

