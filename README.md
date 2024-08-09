# Multi-labeled Feature Selection with a 2-Phase Scheme

## Overview

This repository contains the code and resources for a research project exploring the effectiveness of a 2-phase scheme for multi-labeled feature selection. The project aims to determine whether an initial filtration technique, followed by a genetic algorithm, improves feature selection compared to using the genetic algorithm alone.

## Repository Contents

### 1. Reading Files
This module contains various functions for reading commonly used multi-labeled datasets. It provides the necessary utilities to load and preprocess data for subsequent analysis.

### 2. Phase 1: Based on Ranks
This script calculates a MIC (Maximal Information Coefficient) matrix to evaluate the relevance of each feature. Non-dominated sorting is then applied to this matrix, modified to maximize the sorting function to identify the dominated features. This technique organizes the features into different ranks or fronts, with those in rank 0 (the dominating features) selected for the next phase.

### 3. Phase 1: Based on Crowding Distance
In cases where all features end up in the top rank, the crowding distance is used to differentiate between them. After calculating MIC scores, the crowding distance is computed to measure the relative density of features within the rank. The top 50% of features with the lowest crowding distances are selected, allowing for a more refined feature selection process.

### 4. Main Algorithm
This file contains the core components of the algorithm. It trains the MLKNN model using features selected by a genetic algorithm over 100 generations (modifiable as needed). The genetic algorithm is applied to both the filtered and original sets of features, aiming to minimize the number of features and the Hamming loss. The results are then stored in pickle files for further analysis.

### 5. Reading Results
This script reads pickle files containing the results of the feature selection process. These results can be manually added to a CSV file for easier analysis and interpretation.

### 6. The Wilcoxon Rank-Sum Test (`The_Wilcoxon_Rank_Sum_Test.ipynb`)
This Jupyter notebook performs statistical tests using the Wilcoxon rank-sum test to determine whether differences in metric values (objectives) between filtered and unfiltered datasets are statistically significant. It also includes functions to calculate averages, plot relationships between features and metrics, and provide detailed output on each metric's performance. The input data is expected in the form of a CSV file.

## Dependencies

This project relies on several key Python libraries, including but not limited to:

- **pandas**: For data manipulation and analysis.
- **numpy**: For numerical computations.
- **scikit-learn**: For machine learning models and evaluation metrics.
- **pymoo**: For implementing and optimizing the genetic algorithm.
- **matplotlib**: For plotting and visualization.
- **scipy**: For statistical tests and calculations.
- **skmultilearn**: For multi-label learning models like MLKNN.

Ensure you have these libraries installed before running the scripts.

## Author

This project was developed by **Dafna Matsegora** ([khri5530@mylaurier.ca](mailto:khri5530@mylaurier.ca)) with guidance from my supervisor, **Azam Asilian Bidgoli**.

## Acknowledgments

This work is part of a research project investigating the effectiveness of a 2-phase scheme for feature selection in multi-labeled datasets. The project explores whether an initial filtration phase, followed by a genetic algorithm, offers better results than using the genetic algorithm alone.

