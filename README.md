# Neural Network Model Report for Alphabet Soup 🧠
---
## Overview of the Analysis

The goal of this analysis was to build a machine learning model (a neural network) that predicts whether an applicant funded by Alphabet Soup will be successful with their project. Using a dataset with over 34,000 organizations and their funding details, I designed a binary classifier to help Alphabet Soup decide who has the best chance of success when given funding.

---
## Results

### Data Preprocessing 🧹

- **Target variable:**  
  The target variable was `IS_SUCCESSFUL`, which indicates if the funding was used effectively by the applicant (1 = successful, 0 = not successful).

- **Feature variables:**  
  Features were all other relevant columns after removing identification columns and the target. This included things like `APPLICATION_TYPE`, `AFFILIATION`, `ASK_AMT`, and more.

- **Removed variables:**  
  I removed the `EIN` and `NAME` columns since these were just identifiers and don’t actually help the model learn anything useful about success.

- **Categorical data handling:**  
  For categorical columns with many unique values (like `APPLICATION_TYPE`), I grouped rare categories into “Other” to reduce noise and simplify the model. Then I converted all categorical variables to numeric using one-hot encoding (`pd.get_dummies`).

- **Feature scaling:**  
  Finally, I scaled the feature data with `StandardScaler` to normalize values, which helps the neural network train more efficiently.

---

### Compiling, Training, and Evaluating the Model 🧠⚙️

- **Model architecture:**  
  - Input layer matching the number of features  
  - Two hidden layers with 80 and 30 neurons, respectively  
  - ReLU activation function in hidden layers to learn non-linear relationships efficiently  
  - Output layer with one neuron and sigmoid activation for binary classification  

- **Training:**  
  The model was trained over 50 epochs using the Adam optimizer and binary cross-entropy loss.

- **Performance:**  
  The model reached **about 72.5% accuracy** on the test data with a loss of approximately 0.56.  
  While it didn’t hit the target of 75% accuracy, it still provides a reasonably good prediction of applicant success.

---

### Model Optimization Attempts 📊🛠️

To improve the model, I tried:

- Grouping rare categorical values more aggressively  
- Adding or reducing neurons in the hidden layers  
- Changing the number of epochs  
- Adjusting the number of hidden layers  

Each change affected performance somewhat, but improvements plateaued near 72–73% accuracy.

---

## Summary

Overall, this neural network model does a decent job predicting which Alphabet Soup applicants are likely to succeed. It’s not perfect, but it provides valuable guidance that can help prioritize funding decisions.

While this neural network gave decent results, I know there are other machine learning methods designed for tabular data, such as Random Forests or Gradient Boosting. I haven’t explored those yet, but they are often recommended for similar problems and might improve accuracy. Exploring these could be a good next step.
