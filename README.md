Multilingual Automatic Speech Understanding

System Based on Synthetic Voice



Abstract

This paper presents an ensemble model designed for the automatic understanding of multilingual synthetic voice samples. Combining a Multi-layer Perceptron (MLP) and a Random Forest classifier, our system achieves a remarkable mean accuracy of 84.14%, a significant improvement from the initial 0.52. Utilizing elementary prepro- cessing steps and a diverse dataset encompassing Arabic, English, and French, the sys- tem demonstrates robust performance, emphasizing key metrics such as precision, recall, and F1-score. This project contributes to the development of an automatic speech un- derstanding system, highlighting its effectiveness across different languages and classes.

1  Introduction

Synthetic voices refer to artificially generated or synthesized vocalizations created by computer programs or systems. These voices are designed to mimic human speech and are often used in various applications, such as virtual assistants, navigation systems, and accessibility tools. Understanding syn- thetic voices involves examining the techniques used to create them, the quality of the generated speech, and the implications for user experience and accessibility.

The central objective is to develop a multilingual automatic speech understanding system that leverages synthetic voice. This involves adapting natural language processing models to better compre- hend artificially generated voices. The system should provide accurate and consistent results, even in conditions where synthetic voice may introduce additional challenges. Ultimately, the goal is to demon- strate the effectiveness of this system in practical applications based on synthetic voice.

2  Dataset

This multilingual dataset is tailored for the task of synthetic voice comprehension across Arabic, English, and French languages. The dataset encompasses three distinct classes: ”Diploma,” ”Note,” and ”Certificate.” Synthetic voices for each class were generated from a diverse textual dataset using five distinct agents for English and French and four for Arabic. The resulting audio samples, standardized to a 16,000Hz sampling rate, offer a comprehensive collection for multilingual voice classification.

1. Data Generation Process:
- Textual Dataset: The original dataset comprises textual content in Arabic, English, and French, categorized into three classes: ”Diploma,” ”Note,” and ”Certificate.”
- Voice Synthesis: Synthetic voices were generated for each text in the dataset using four different agents, introducing variations in voice characteristics and styles.
- Audio Sampling Rate: All audio samples were standardized to a sampling rate of 16,000Hz to ensure uniformity in the dataset.
2. Dataset Split:

The dataset is divided into training and test sets, ensuring a balanced representation of voices across each class in Arabic, English, and French.

3  System Architecture

In our multilingual automatic speech understanding system, we follow a comprehensive approach comprising three main stages: audio data loading and feature extraction, feature standardization, and ensemble classification. For the initial step, we use the Librosa library to load audio data from speci- fied paths and extract crucial features, including Mel-frequency cepstral coefficients (MFCCs) and pitch features. These features are then processed to form a concatenated feature vector. Subsequently, the extracted features undergo standardization using the StandardScaler to ensure uniformity and compatibil- ity. The standardized feature set serves as input for our ensemble classification model. We experimented with different models, including MLPClassifier, RandomForest, MLPClassifier (Partial), KNN (Partial), Ensemble (RF + KNN) (Partial), Stacked Ensemble (Partial), SVM, Ensemble (SVM + MLP), Ensemble (SVM + MLP) (Partial), and Ensemble (MLP + RF) (Cross-Validated), to achieve the best performing configuration.

The ensemble model combines two robust classifiers, the Multi-layer Perceptron (MLP) and Ran- domForest, through a VotingClassifier employing a hard voting strategy. After extensive experimentation, we found that the Ensemble (MLP + RF) (Cross-Validated) configuration consistently demonstrated su- perior performance, achieving the highest test accuracy of 84.14%. This remarkable accuracy is indicative of the ensemble model’s effectiveness in understanding multilingual synthetic voice samples.

The system undergoes cross-validation using StratifiedKFold with five splits, evaluating perfor- mance metrics such as accuracy scores, confusion matrix, and classification report. In conclusion, our system architecture seamlessly integrates audio data processing, feature extraction, and ensemble classi- fication, showcasing its potential for accurate multilingual automatic speech understanding in practical applications based on synthetic voice samples.

4  Experiments and Results

After an extensive experimentation phase, we carefully selected the ten best-performing configu- rations based on the development and test phases. Table 1 and Table 2 provides a detailed overview of these experiments, encompassing different models, feature sets, and preprocessing techniques. Through meticulous evaluation, the 10th experiment consistently demonstrated superior performance, achieving the highest test accuracy of 84.14%. This remarkable accuracy is indicative of the ensemble model’s effectiveness in understanding multilingual synthetic voice samples.

Table 1: Summary of Audio Classification Top 10 Experiments - Features and Models

|N°|Features|Model|Test Accuracy|
| - | - | - | - |
|1|MFCC (mean, std) + Pitches (mean, std)|MLPClassifier|75\.00%|
|2|MFCC (mean, std) + Pitches (mean, std)|RandomForest|76\.97%|
|3|MFCC (mean, std) + Pitches (mean, std)|MLPClassifier (Partial)|83\.71%|
|4|MFCC (mean, std) + Pitches (mean, std)|KNN (Partial)|76\.97%|
|5|MFCC (mean, std) + Pitches (mean, std)|Ensemble (RF + KNN) (Partial)|75\.28%|
|6|MFCC (mean, std) + Pitches (mean, std)|Stacked Ensemble (Partial)|82\.02%|
|7|MFCC (mean, std) + Pitches (mean, std)|SVM|81\.46%|
|8|MFCC (mean, std) + Pitches (mean, std)|Ensemble (SVM + MLP)|82\.00%|
|9|MFCC (mean, std) + Pitches (mean, std)|Ensemble (SVM + MLP) (Partial)|83\.00%|
|10|MFCC (mean, std) + Pitches (mean, std)|Ensemble (MLP + RF) (Cross-Validated)|84\.14% (Mean)|


Analysis and Comparison of the Top Ten Experiments:

- Experiment 3 with the MLP Classifier on partial training data achieved high test accuracy (83.71%).
- Ensemble methods, especially the Stacked Ensemble (Experiment 6), demonstrated strong perfor- mance, highlighting the effectiveness of model combinations.
- The use of MFCC and Pitches features appears to be effective for audio classification.
- Experiment 10, an Ensemble (MLP + RF) (Cross-Validated), achieved the highest test accuracy of 84.14%, further showcasing the model’s robustness and effectiveness.
- Cross-validation results analysis (Experiment 10) confirms the robustness of the models and stability of performance across different folds.
- Repeated experiments (Experiment 9) showcase the consistency of performance across executions.

These analyses emphasize the importance of selecting appropriate models, leveraging informative features, and considering ensemble strategies to enhance model performance.

These results demonstrate the effectiveness of our multilingual automatic speech understanding system based on synthetic voice. The ensemble of MLPClassifier and RandomForestClassifier provides robust performance across different languages and classes, showcasing its adaptability to synthetic voice data.

5 Conclusion

In the pursuit of enhancing the performance of our automatic speech understanding system, this study started with a base accuracy of 0.52. Employing a meticulous approach, we systematically explored and implemented improvements to various components of the system. Our focus on preprocessing steps, encompassing the extraction of MFCC features and pitch features, was a key strategy. The utilization of a sophisticated ensemble model, combining the strengths of a Multi-layer Perceptron (MLP) and a Random Forest classifier, further contributed to refining our system.

The cross-validation results showcase a significant improvement, with the mean accuracy now standing at 84.14%. This marks a substantial advancement from the initial accuracy of 0.52. The precision, recall, and F1-score metrics for each class demonstrate the system’s ability to make more accurate and reliable predictions across diverse languages and classes.

The ensemble model, consisting of MLP and RandomForest classifiers, has proven to be highly effective in adapting to various linguistic contexts. The confusion matrix and classification report, based on mean cross-validation scores, validate the success of our improvements.

These findings not only underscore the significant enhancement achieved but also highlight the potential for further refinement. As we continue to fine-tune our approach and explore additional avenues, there is optimism for achieving even greater accuracy and applicability in real-world scenarios.



