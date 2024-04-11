# Pneumonia-Detection-using-Knowledge-Distillation-from-Self-Supervised-Models

# Problem Statement

Build a binary classifier to detect pneumonia using chest x-rays.

# Pneumonia
Pneumonia is an infection that inflames the air sacs in one or both lungs. The air sacs may fill with fluid or pus (purulent material), causing cough with phlegm or pus, fever, chills, and difficulty breathing. A variety of organisms, including bacteria, viruses and fungi, can cause pneumonia. Chest X-ray, blood tests, and culture of the sputum may help confirm the diagnosis. The disease may be classified by where it was acquired, such as community- or hospital-acquired or healthcare-associated pneumonia.

# Dataset description
The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). There are 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal). Chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of patients’ routine clinical care. For the analysis of chest x-ray images, all chest radiographs were initially screened for quality control by removing all low quality or unreadable scans. The diagnoses for the images were then graded by two expert physicians before being cleared for training the AI system. In order to account for any grading errors, the evaluation set was also checked by a third expert.
![WhatsApp Image 2024-03-31 at 15 31 53_5aa50f20](https://github.com/Akshita132/Pneumonia-Detection-using-Knowledge-Distillation-from-Self-Supervised-Models/assets/89724193/0bd3f93a-ea40-4db9-9831-fc76a2680503)

# Model used :
![resnet50](https://github.com/Akshita132/Pneumonia-Detection-using-Knowledge-Distillation-from-Self-Supervised-Models/assets/89724193/e65e3685-d304-4a2b-a1e9-566c3c9983ff)
                                        Architecture of Teacher Model(ResNet50)- Student Model (ResNet18)
                                        
![image](https://github.com/Akshita132/Pneumonia-Detection-using-Knowledge-Distillation-from-Self-Supervised-Models/assets/89724193/fc5041e8-446c-4a2c-913c-1744b90ea47f)      
                                                                 Data flow diagram

### Pre-training the Teacher Model: 
Start by pre-training a large, complex model (the teacher model) on a large dataset for a specific task. This model serves as the source of knowledge that will be distilled into the student model.
### Transfer Learning for Student Model Initialization: 
Initialize the smaller student model using the pre-trained weights of the teacher model. By doing this, the student model starts with some knowledge already transferred from the teacher model, which can help accelerate the learning process.
### Knowledge Distillation Training: 
Train the student model using knowledge distillation techniques. In addition to learning from the ground truth labels of the training data, the student model is also trained to mimic the outputs (e.g., class probabilities) of the teacher model on the same data.
### Objective Function: 
The objective function used during training typically combines two components: the standard cross-entropy loss between the student model predictions and the ground truth labels, and an additional loss term that measures the discrepancy between the predictions of the student and teacher models. 
    


