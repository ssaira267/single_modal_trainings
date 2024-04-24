# **Gradient-Boosted Trees for Predicting Dunham Texture**

## Overview
This repository contains the Python code and datasets used in Chapter 5 of Saira Baharuddin's PhD thesis. The chapter is titled "Gradient-Boosted Trees to Predict Dunham Texture from Diverse Downhole Logging Tools." The goal of this project is to apply machine learning techniques, specifically gradient-boosted trees and convolutional neural networks (CNNs), to predict the Dunham classification of carbonate rocks using data derived from various downhole logging tools (Formation MicroScanner image log and wireline logs).

## Chapter Abstract
Geological cores provide valuable information about carbonate rocks, but coring is often limited by time, resources, and low recovery. Borehole logs offer a continuous proxy for subsurface lithologies. Machine learning models have been used successfully to predict lithology from wireline log data, such as gradient-boosted trees and convolutional neural networks (CNNs). In this study, I use two different datasets: one with standard wireline logs data and another with high-resolution wireline logs data. Both datasets include a combination of wireline logs and FMS images cropped to the depth intervals of wireline logs. The objectives of this study include: 
- investigate the use of the VGG19 CNN model and gradient-boosted trees (XGBoost algorithm) separately for carbonate rock classification using wireline log data and Formation MicroScanner image log exclusively, and
- compare the performance of 3 single-modal learning methods: transfer learning on a VGG19 architecture using FMS image data, XGBoost using wireline log data, and XGBoost using the embedding of FMS data from the VGG19 model. The models performances' are evaluated based on learning curves (loss and accuracy) as well as various quantitative metrics such as accuracy, precision, recall, and F1-score.

The VGG19 architecture successfully captured features from FMS images but encountered issues such as overfitting and poor model convergence. Nonetheless, transfer learning demonstrated moderate to good performance. Integrating FMS features extracted by VGG19 with XGBoost also led to overfitting, possibly due to the limited size of the dataset. Overall, the XGBoost tabular model trained using standard-resolution wireline logs has the highest test accuracy at 91%. This confirms that XGBoost performs exceptionally well with structured tabular data, and the greater number of features in the standard-resolution dataset, derived from more wireline logs, allows for better learning by the model. In conclusion, the best approach, therefore, appears to be using gradient-boosted trees on tabular data alone. The FMS data does not provide any additional benefit in this context.

## Repository Contents
1. Data: Sample datasets used for training and testing the models are publicly available on the following website: https://mlp.ldeo.columbia.edu/logdb/scientific_ocean_drilling. The dataset used are from Leg 194, holes 1194B, 1196A and 1199A. The .csv files inside the data directory serve as examples demonstrating how the data is arranged and used for this study. These files contain structured data in tabular format, where each row represents a sample or observation, and each column represents a feature or attribute of that sample. Due to the large file size of the FMS images, I am unable to upload the FMS images folder. However, the images are available on the website mentioned earlier. It's important to note that the FMS images have been cropped based on the depth intervals specified for the study.
2. Notebooks: Python codes developed include data preprocessing, model training, model evaluation, and visualization of the results.
3. Documentation: Additional resources and documentation that outline the methods used in this study.

## How to Use
To run the scripts in this repository:
1. Ensure that Python 3.8 (and above) and the necessary libraries (listed in requirements.txt) are installed.
2. Clone the repository to your local machine.
3. Navigate to the notebooks directory and run the desired notebook as follows:
  
  ```bash
  python notebook_name.py
  ```

## Dependencies 
- Dlisio
- Imbalanced-learn
- Livelossplot
- Matplotlib
- NumPy
- OpenCV-python
- pandas
- Scikit-learn
- Seaborn
- Tensorflow
- Tensorflow-Keras
- XGBoost

Please refer to 'requirements.txt' for a complete list of dependencies.

## Contact
For any queries related to this repository or the research, please contact:
- Saira Baharuddin                  - Email: s.baharuddin19@imperial.ac.uk
- Prof Cédric John (PhD Supervisor) - Email: cedric.john@qmul.ac.uk









