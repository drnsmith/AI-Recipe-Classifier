# AI Recipe Classifier

This repository contains code and documentation for an AI recipe classifier developed to categorise recipes into difficulty levels, including "Easy," "Medium," "Hard," and "Very Hard." The classifier is built using Python and various machine learning (ML) techniques. This README file provides an overview of the project and its components.

## Model Development

- **Programming Language**: Python
- **Libraries Used**: Pandas, Scikit-learn

### Dataset Pre-processing
The Pandas library was used for dataset loading and pre-processing to ensure that the data is structured appropriately for model training. Special attention was given to handling NaN (Not a Number) values within the text data to avoid adverse impacts on model training.

### Label Assignment

Before model training, difficulty levels were programmatically assigned to each recipe based on various criteria such as the number of ingredients, the length of preparation steps, and three specific metrics:
- **Step Complexity**: Average word count across all preparation steps.
- **Technique Diversity**: Count of various cooking techniques normalised by the total number of techniques considered.
- **Ingredient Diversity**: Number of unique ingredients used.

These metrics were normalised and optionally weighted to compute a "Total Complexity" score for each recipe. Recipes were then categorized into difficulty levels ("Easy," "Medium," "Hard," "Very Hard") based on the quantiles of this score, resulting in well-balanced labels.

### Model Training and Evaluation

A text classification model was developed using a Random Forest Classifier and TF-IDF Vectorisation. The features considered for model training were the complexity metrics calculated earlier. The model was evaluated using k-fold cross-validation and a separate test set, achieving high accuracy scores:
- Mean Cross-Validation Accuracy: ~99.28%
- Test Accuracy: ~99.33%

These results indicate that the difficulty level labels assigned to the text data are highly accurate and reliable.

## Performance across ML Models
Various ML and deep learning models WERE trained and evaluated, including Baseline (Dummy Classifier), Logistic Regression, Gradient Boosting Classifier, Random Forest Classifier, Multi-Layer Perceptron (MLP), Convolutional Neural Network (CNN), Recurrent Neural Network (RNN), Support Vector Machine (SVM), Naive Bayes, and Custom Neural Network (NN).

| Model                 | Accuracy | Precision | Recall | F1 Score |
|-----------------------|----------|-----------|--------|----------|
| Baseline              | 0.2500   | -         | -      | -        |
| Logistic Regression   | 0.6936   | 0.6961    | 0.6936 | 0.6947   |
| Gradient Boosting     | 0.6844   | 0.6846    | 0.6844 | 0.6844   |
| Random Forest         | 0.6360   | 0.6304    | 0.6360 | 0.6324   |
| MLP                   | 0.7183   | 0.7167    | 0.7183 | 0.7170   |
| CNN                   | 0.6900   | 0.6927    | 0.6900 | 0.6908   |
| RNN                   | 0.6821   | 0.6805    | 0.6821 | 0.6807   |
| SVM                   | 0.6668   | 0.6681    | 0.6668 | 0.6674   |
| Naive Bayes           | 0.4494   | 0.4680    | 0.4494 | 0.4408   |
| Initial Custom NN     | 0.7523   | 0.7540    | 0.7523 | 0.7529   |
| Final Custom NN       | 0.7503   | 0.7573    | 0.7503 | 0.7530   |

The final Custom Neural Network (NN) model achieved the highest accuracy and F1 score, indicating its effectiveness in classifying recipe difficulty levels.

## Interpretation with LIME

LIME (Local Interpretable Model-agnostic Explanations) was used to interpret the predictions of the best-performing text classification model (Final Custom NN). LIME provides insights into the model's decision-making process on a per-instance basis.

For example, based on LIME interpretations, the model predicted an instance with a probability distribution as follows:
- Class "Easy": 80%
- Class "Medium": 0%
- Class "Hard": 20%
- Class "Very Hard": 0%

LIME also highlighted influential words in the text, such as "mixtury," "ingredi," "side," "tomato," and "crumb," which played a significant role in the prediction. This information helps us understand why the model made a particular prediction and can be valuable for model debugging and improvement.

Please refer to the [GitHub repository](https://github.com/drnsmith/AI-Recipe-Classifier.git) for the complete code and detailed documentation. Contributions are welcome to expand the repository and support a wide range of use cases.

**Note**: This README provides a high-level overview. Detailed code and additional documentation can be found in the GitHub repository.
