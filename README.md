


# Automatic Detection of Keratoconus from Galilei Corneal Images Using Convolutional Neural Networks

---

## Project Overview
This project presents a deep learning-based approach to automatically detect **Keratoconus** (KCN), a progressive non-inflammatory corneal disease, using corneal images obtained from a **Galilei Dual Scheimpflug Analyzer**. The model employs **Convolutional Neural Networks (CNNs)** to analyze corneal topography maps, providing accurate detection of keratoconus from healthy eyes.

## Dataset
- The dataset includes **3538 eyes**: 
  - **1872 keratoconus cases**
  - **1666 healthy eyes**
- Four types of **color-coded corneal maps** were used:
  1. Posterior Elevation Best-Fit Toric Aspheric (BFTA)
  2. Anterior Elevation BFTA
  3. Anterior Instantaneous Curvature
  4. Pachymetry maps
- **14 numerical indices** related to corneal characteristics were also included for certain experiments.

## Model Architecture
- **Multi-branch CNN architecture**: Each branch processes one of the four corneal maps using different pre-trained CNN models.
  - **DenseNet121** for Anterior Elevation BFTA
  - **ResNet50** for Posterior Elevation BFTA
  - **Xception** for Anterior Instantaneous Curvature
  - **MobileNet** for Pachymetry maps
- The output features from the CNNs are concatenated and combined with the **numerical indices** (when available), followed by fully connected layers for classification.

### Three-Stage Training Process:
1. **Stage 1**: Train each CNN model separately using a specific color-coded map and update the weights from ImageNet to the dataset.
2. **Stage 2**: Freeze the CNN weights and train the fully connected layers with all four branches active.
3. **Stage 3**: Fine-tune the model by training one CNN branch at a time, freezing the other three.

## Performance Metrics
- The main model achieved:
  - **Accuracy**: 93.5%


## Prerequisites
- **TensorFlow** 
- **Keras**
- **NumPy**
- **Matplotlib**
- **Pandas**

## Authors

- [Suorena Saeedi](https://github.com/ssuorena)
- [Mohammad Saeed Zafari](https://github.com/ithe0m)