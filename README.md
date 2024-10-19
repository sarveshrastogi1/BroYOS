# BroYO
# Diabetic Retinopathy Project

## Overview

Diabetic Retinopathy (DR) is one of the leading causes of blindness worldwide, affecting nearly 1 in 3 people with diabetes. Early detection is critical, but the manual examination of retinal images is time-consuming and requires specialized expertise, especially given the subtle variations between different stages of DR. DR occurs when high blood sugar levels damage the blood vessels in the retina, leading to vision changes and potentially severe complications. In its advanced stages, DR can cause bleeding in the eye and the formation of scar tissue, which may result in permanent vision loss if not treated promptly. Additionally, other retinal conditions such as Central Retinal Vein Occlusion (CRVO), Branch Retinal Vein Occlusion (BRVO), Pre-Retinal Hemorrhage (PRH), and Retinal Hemorrhages Localized (RHL) can lead to significant vision loss if not identified early.

![Severe Diabetic Retinopathy](https://www.aao.org/Assets/35c52c16-8c9f-479e-afe2-85e90e356274/637255216604230000/diabetic-retinopathy-severe-bc0ffcc8-5c40-4c3d-90ea-54dc3bdb2986.jpg)

This project addresses these challenges by leveraging deep learning to automatically detect and classify Diabetic Retinopathy and other retinal diseases from high-resolution images. The model classifies DR into five categories: No DR, Mild, Moderate, Severe, and Proliferative DR. It also identifies the presence of CRVO, BRVO, PRH, and RHL, providing a comprehensive assessment of a patient's retinal health.

- CRVO (Central Retinal Vein Occlusion)- occurs when the central retinal vein becomes blocked, leading to retinal hemorrhages and fluid leakage
- BRVO (Branch Retinal Vein Occlusion)-characterized by the obstruction of one of the branches of the central retinal vein, resulting in localized swelling and bleeding in the retina
- PRH (Pre-Retinal Hemorrhage)-bleeding that occurs between the retina and the inner limiting membrane
- RHL (Retinal Hemorrhages Localized)-involves the presence of localized areas of bleeding within the retina

Detecting these additional conditions is crucial, as they can exacerbate vision loss and complicate treatment plans if left undiagnosed. By improving diagnostic accuracy and efficiency, the model supports healthcare professionals in early intervention, potentially saving patients' vision and showcasing AI's transformative role in healthcare.

## Dataset

The dataset is sourced from [Kaggle](https://www.kaggle.com/datasets/sovitrath/diabetic-retinopathy-224x224-2019-data), containing approximately 3,700 high-resolution retinal images categorized into five classes: No DR, Mild, Moderate, Severe, and Proliferative DR.

In this project, we employed a robust deep learning framework to detect and classify Diabetic Retinopathy and other retinal conditions using a custom ensemble model that combines EfficientNet and Vision Transformer (ViT) architectures. The training process began with the creation of a comprehensive dataset loader utilizing Albumentations for advanced data augmentation techniques, such as random rotations, brightness adjustments, and dropout, to enhance model robustness and improve generalization. We configured the model to classify images into five categories of Diabetic Retinopathy while also detecting other conditions like CRVO, BRVO, PRH, and RHL.

The training utilized Focal Loss, which is particularly effective in addressing class imbalance and emphasizing harder-to-classify samples. A Cosine Annealing Warm Restarts scheduler was employed to dynamically adjust the learning rate, optimizing convergence throughout the 100 epochs of training. The model was evaluated using accuracy metrics on both training and validation datasets, with the best model weights saved for future inference. Overall, this approach not only demonstrates the effectiveness of ensemble learning in medical imaging but also highlights the potential of AI to assist in critical healthcare diagnostics.

## Model Architecture

This project utilizes an ensemble model architecture that combines two powerful neural network architectures: *EfficientNet-B0* and the *Vision Transformer (ViT)*. EfficientNet-B0 is recognized for its efficiency regarding parameters and computational resources while achieving high accuracy in image classification tasks, thanks to its balanced scaling of depth, width, and resolution. In contrast, ViT leverages self-attention mechanisms to effectively capture global dependencies in images, making it particularly effective for various computer vision applications. By averaging the predictions from both EfficientNet and ViT, this ensemble model employs a soft voting approach that enhances robustness and accuracy, ultimately improving the classification of Diabetic Retinopathy from retinal images.
