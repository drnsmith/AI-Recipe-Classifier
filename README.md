### AI-Powered Recipe Difficulty Classification with NLP and Machine Learning

#### **Overview**
This project introduces an innovative **AI-powered recipe difficulty classifier**, designed to categorise recipes into one of four levels: **Easy, Medium, Hard, or Very Hard**. By analysing ingredients and preparation steps, the model empowers users to make informed culinary decisions based on their skills and time constraints. The classifier demonstrates the application of **Natural Language Processing (NLP)** and **machine learning (ML)** to streamline the culinary experience.

---

#### **Motivation**
Cooking can be intimidating, especially when recipe difficulty levels are unclear. This project aims to:
1. **Simplify Culinary Choices**: Help users select recipes that align with their skill levels and available time.
2. **Demonstrate AI Applications**: Showcase the use of NLP and ML in real-world applications like recipe analysis.
3. **Support Culinary Accessibility**: Provide a scalable solution that caters to diverse cuisines and dietary preferences.

---

## **Dataset Description**
- **Source**: The dataset is sourced from **RecipeNLG**, a large collection of recipes with detailed ingredients and instructions.
- **Structure**:
  - Recipes include textual descriptions, a list of ingredients, and preparation steps.
  - Labels indicate difficulty levels, either provided or inferred based on analysis.
- **Pre-processing**:
  - Text cleaning: Removed special characters, numbers, and extra spaces.
  - Tokenisation: Split sentences into words for processing.
  - Lemmatization: Normalised words to their base forms.

---

## **Model Architectures**

### **1. Feature Engineering**
- **Text Representation**:
  - **TF-IDF**: Captured term frequency and inverse document frequency to represent recipe text.
  - **Word2Vec**: Created vector embeddings for semantic analysis of ingredients and instructions.
  - **BERT**: Used pre-trained transformers for contextual word representations.

### **2. Machine Learning Models**
- **Logistic Regression**:
  - Served as a baseline classifier.
- **Random Forest**:
  - Provided a robust approach to handle non-linear patterns.
- **Gradient Boosting (XGBoost)**:
  - Leveraged sequential decision trees for improved predictions.
- **Neural Networks**:
  - Used dense layers for capturing complex relationships in text data.

---
### Label Assignment

Before model training, difficulty levels were programmatically assigned to each recipe based on:
- **Step Complexity**: Average word count across all preparation steps.
- **Technique Diversity**: Count of various cooking techniques normalised by the total number of techniques considered.
- **Ingredient Diversity**: Number of unique ingredients used.

These metrics were normalised and weighted to compute a "Total Complexity" score for each recipe. Recipes were then categorised into difficulty levels ("Easy", "Medium", "Hard", "Very Hard") based on the quantiles of this score, resulting in well-balanced labels.

## Performance across ML Models
Various ML and deep learning models were trained and evaluated, including Baseline (Dummy Classifier), Logistic Regression, Gradient Boosting Classifier, Random Forest Classifier, Multi-Layer Perceptron (MLP), Convolutional Neural Network (CNN), Recurrent Neural Network (RNN), Support Vector Machine (SVM), Naive Bayes, and Custom Neural Network (NN).

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

The final Custom NN model achieved the highest accuracy and F1 score, indicating its effectiveness in classifying recipes.

## Interpretation with LIME

LIME (Local Interpretable Model-agnostic Explanations) was used to interpret the predictions of the best-performing text classification model (Final Custom NN). LIME provides insights into the model's decision-making process on a per-instance basis. Based on LIME interpretations, the model predicted an instance with a probability distribution as follows, class"
- "Easy": 80%
- "Medium": 0%
- "Hard": 20%
- "Very Hard": 0%

LIME also highlighted influential words in the text, such as "mixtury", "ingredi", "side", "tomato", and "crumb", which played a significant role in the prediction. This information helps us understand why the model made a particular prediction and can be valuable for model debugging and improvement.

---
### Productisation  
The AI-powered recipe difficulty classifier can be transformed into a **personalised cooking assistant**, integrating with **recipe websites, mobile apps, and smart kitchen devices**. By leveraging **real-time NLP analysis**, the system can dynamically **adjust recipe difficulty levels based on user preferences, available ingredients, and past cooking history**. Expanding the platform to support **voice assistants and interactive cooking tutorials** would make it a valuable tool for both beginner and experienced home cooks.

### Monetisation  
This project can be monetised through **subscription-based API licensing**, allowing food bloggers, recipe platforms, and meal kit services to incorporate **AI-driven difficulty classification into their applications**. Additionally, a **premium mobile app** offering **AI-powered meal recommendations, step-by-step guidance, and difficulty-based recipe filtering** can generate revenue through **freemium models, in-app purchases, and affiliate partnerships with grocery retailers**.

---

## Contributing
Contributions are welcome! If you have ideas or improvements to share, please follow these steps:

1. **Fork the Repository:**
Create your own copy of the repository by clicking the "Fork" button at the top right of this page.

2. **Create a Feature Branch:**
Work on your changes in a dedicated branch.

```bash
git checkout -b feature/YourFeatureName
```
3. **Commit Your Changes:**
Write clear and concise commit messages explaining what you’ve done.

```bash
git commit -m "Add YourFeatureName"
```
4. **Push Your Changes:**
Push your feature branch to your forked repository.
```bash
git push origin feature/YourFeatureName
```
5. **Open a Pull Request:**
Submit your changes to the main repository by opening a pull request (PR). Ensure your PR description explains your changes clearly.

6. **Review and Feedback:**
I will review your PR and may suggest improvements before merging it into the main branch.

Thank you for your interest in contributing!

---
## Repository History Cleaned

As part of preparing this repository for collaboration, its commit history has been cleaned. This action ensures a more streamlined project for contributors and removes outdated or redundant information in the history. 

The current state reflects the latest progress as of 24/01/2025.

For questions regarding prior work or additional details, please contact the author.

---

## License
Distributed under the MIT License. See `LICENSE` for more information.

