# Visual Complexity Perception: Comparing AI and Human Judgments
Overview

Humans and AI do not always perceive visual complexity in the same way. While computers can quantify low-level image characteristics such as edges, brightness, and color variation, it is unclear whether these features capture how people actually judge the complexity of a scene.

This project investigates how closely AI predictions align with human perceptions of visual complexity. Using computational image features extracted from 80 images, I trained machine learning models to predict visual complexity and compared their predictions with participant ratings. I also analyzed where AI and humans agreed most, where they differed, and how researcher judgments compared with participant perceptions.

Research Questions

This project explores the following questions:
- Can AI predict how humans perceive visual complexity?
- Which image features best explain human judgments?
- Where do AI predictions align most closely with participant ratings?
-  Which images produce the largest disagreements between AI and humans?
- How similar are researcher-assigned ratings to participant perceptions?

Dataset

The dataset contains 80 images divided into four scene categories:
- Messy Desks
- Streets
- Landscapes
- Simple Rooms

For each image, I extracted three computational features:
- Edge Density – amount of visual structure and detail
- Average Brightness – mean grayscale intensity
- Color Variance – variability of RGB values

Each image also includes:
- Researcher-assigned visual complexity rating
- Average participant complexity rating (five participants)

Project Workflow

Week 1 – Building the Dataset
- Collected and organized 80 images across four scene categories.
- Extracted computational image features using OpenCV.
- Combined image features with researcher and participant complexity ratings.
- Explored feature distributions across image categories.

Week 2 – Predicting Researcher Ratings
Two machine learning models were trained to predict researcher-assigned complexity ratings:
- Linear Regression
- Random Forest Regression

Model performance was evaluated using Mean Squared Error (MSE) and R² score, and feature importance analysis was used to identify which image characteristics most influenced predictions.

Results

Model	R²	MSE
- Linear Regression	0.549	0.254
- Random Forest	0.414	0.330

Edge density was consistently the strongest predictor of researcher-rated complexity.

Week 3 – Comparing AI and Human Perception

The same modeling approach was applied to participant-rated complexity to investigate how well AI captures human visual perception.

The analysis focused on:
- Comparing AI predictions with participant ratings
- Measuring agreement between AI and humans
- Identifying images with the largest prediction errors
- Comparing researcher and participant judgments
- Examining differences across image categories

Results

Model	R²	MSE
- Linear Regression	0.325	0.296
- Random Forest	-0.093	0.480

Key Findings
- AI predictions showed a moderately strong positive correlation with participant ratings (r = 0.651, p < 0.001), indicating that simple computational image features capture important aspects of human perception.
- Edge density was the strongest computational predictor of perceived visual complexity, while brightness and color variance contributed less predictive information.
- AI aligned closely with participant ratings for many images but struggled on others, particularly scenes where people appeared to rely on visual cues beyond the extracted image features.
- Researcher and participant ratings were moderately correlated (r = 0.605, p < 0.001), suggesting that expert judgments and everyday human perception do not always evaluate visual complexity in the same way.
- Street scenes and messy desks were generally perceived as the most visually complex, while landscapes and simple rooms received lower average complexity ratings.

Technologies Used
- Python
- OpenCV
- NumPy
- pandas
- Matplotlib
- SciPy
- scikit-learn
- Jupyter Notebook

Repository Structure

visual-complexity-perception/
│
├── data/
│   └── features.csv
│
├── notebooks/
│   ├── week1_feature_extraction.ipynb
│   ├── week2_researcher_prediction.ipynb
│   └── week3_participant_prediction.ipynb
│
├── requirements.txt
└── README.md

Running the Project

1. Clone the repository.
   git clone <repository-url>
2. Install the required packages.
   pip install -r requirements.txt
3. Launch Jupyter Notebook.
   jupyter notebook
4. Run the notebooks in order:
- Week 1 – Feature Extraction
- Week 2 – Researcher Prediction
- Week 3 – Participant Prediction and AI–Human Comparison

Future Work

Potential improvements include:
- Extracting higher-level visual features such as texture, entropy, object count, and deep learning embeddings.
- Expanding the dataset with additional image categories.
- Collecting ratings from more participants to improve reliability.
- Evaluating more advanced machine learning and computer vision models.
- Investigating why AI and humans disagree on certain images and identifying additional visual factors that influence human perception.

Author

Qixuan Lin
University of California, Santa Barbara
Majors: Statistics & Data Science, Psychological & Brain Sciences
