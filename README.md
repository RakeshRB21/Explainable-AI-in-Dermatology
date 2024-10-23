# Skin Lesion Classification with Explainable AI (Grad-CAM, SmoothGrad)

This project applies deep learning models—InceptionV3, Xception, and EfficientNet—to classify skin lesions as benign or malignant. To enhance the transparency and trustworthiness of the models, we incorporated Explainable AI (XAI) techniques like Grad-CAM and SmoothGrad, which help visualize the important regions in images that influence the AI's decision. This approach makes the model's predictions more interpretable and helps healthcare professionals understand and trust the results.

## Table of Contents
- [Project Overview](#project-overview)
- [Models](#models)
- [XAI Techniques](#xai-techniques)
- [Installation](#installation)
- [Dataset](#dataset)
- [Usage](#usage)
- [Results](#results)
- [Future Work](#future-work)


## Project Overview

Skin cancer is a growing concern globally, and early detection is critical for successful treatment. AI can assist in diagnosing skin lesions by classifying them as benign or malignant with high accuracy. However, the lack of transparency in most AI models can limit their adoption in clinical settings. This project tackles that challenge by applying explainable AI techniques that allow healthcare professionals to visualize the areas in the images that influenced the model's predictions.

## Models

We implemented and compared the following deep learning models:

- InceptionV3
- Xception
- EfficientNet (128x128 and 224x224 input sizes)

These models were trained on a large dataset of skin lesion images and evaluated for their performance on classifying lesions as benign or malignant.

## XAI Techniques

To make the models more interpretable, we used:

- **Grad-CAM** (Gradient-weighted Class Activation Mapping): Visualizes the important regions in the image that contributed to the model's prediction.
- **SmoothGrad**: Enhances the visualization generated by Grad-CAM by reducing noise in the gradient maps, leading to clearer explanations.

## Installation

1. Clone the repository:
```bash
git clone https://github.com/your-repo/skin-lesion-classification-xai.git
cd skin-lesion-classification-xai
```


Ensure you have TensorFlow, Keras, and OpenCV installed for training models and image processing.

## Dataset

We used the isic malignant vs benign skin lesion classification dataset.

## Usage

1. **Preprocessing**: Organize and preprocess the dataset using the provided Jupyter notebooks. This step includes data augmentation, resizing images, and splitting the dataset into training and testing sets.

2. **Training the models**: Run the training scripts to train the InceptionV3, Xception, and EfficientNet models. The training scripts will save the best model weights based on validation accuracy.
```bash
python train_model.py --model xception
```

3. **Explainability**: After training, apply the Grad-CAM and SmoothGrad techniques to visualize the areas of the images that influenced the model's decision.
```bash
python apply_xai.py --model xception --technique grad-cam
```

4. **Evaluation**: Evaluate the models using performance metrics like precision, recall, F1-score, and overall accuracy.

## Results

The Xception model performed the best overall, achieving the following metrics:

- Benign Precision: 0.87
- Benign Recall: 0.92
- Malignant Precision: 0.90
- Malignant Recall: 0.84
- Overall Accuracy: 88%

Grad-CAM and SmoothGrad successfully highlighted important regions, such as irregular borders and color variations in lesions, that influenced the models' decisions.

## Future Work

We plan to:

- Further optimize the models to improve accuracy and recall for both benign and malignant lesions
- Explore advanced XAI methods like SHAP and Layer-wise Relevance Propagation (LRP)
- Develop a real-time clinical application with an integrated explainability dashboard
- Expand the dataset to include more diverse and complex skin lesion images

