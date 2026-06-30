# TRCS-102
Artificial Intelligence and Machine Learning Diary 

📔 AI/ML Diary - Day 1
📌 Topics Covered

Introduction to Python & Why We Need It

Python's Role in Backend/Legacy Systems

Python Data Types

Python Data Structures

🐍 1. Python for AI/ML
Why Python?: It has a simple, English-like syntax and offers powerful libraries (like NumPy, Pandas, Scikit-learn) specifically built for AI/ML.

Backend/Legacy Role: Python acts as a "Glue Language." It easily connects older backend systems (written in C/C++) and heavy data pipelines with modern ML algorithms.

🔢 2. Data Types
Integer (int): Numbers without decimals. Example: age = 25

Float (float): Numbers with decimals. Example: accuracy = 0.95

String (str): Text data inside quotes. Example: model_name = "LinearRegression"

Boolean (bool): Represents only True or False.

🗂️ 3. Data Structures
List []: Ordered and mutable (changeable). Allows duplicate values.

📔 AI/ML Diary - Day 2📌 Topics CoveredDeep Dive into Advanced Data Structures (Tuple, Set, Dictionary)Python OperatorsPractical Relevance in AI/ML🗂️ 1. Advanced Data Structures (Quick Recap & Nuances)🔹 Tuple ()Key Concept: Ordered and Immutable (cannot be modified after creation).AI/ML Use Case: Used to pass structural configurations that must remain constant, like input shape tensors or weights metadata.Python# Image dimensions: Height, Width, Channels (RGB)
input_shape = (224, 224, 3) 
🔹 Set {}Key Concept: Unordered collection of Unique elements. Automatically eliminates duplicates.AI/ML Use Case: Perfect for finding unique target labels or filtering out duplicate entries during data preprocessing.Python# Extracting unique classes from a text dataset
target_classes = {"Spam", "Ham", "Spam"} # Result: {'Spam', 'Ham'}
🔹 Dictionary {Key: Value}Key Concept: Unordered, mutable collection of Key-Value pairs. Fast lookups using unique keys.AI/ML Use Case: Extensively used for setting up model hyperparameters, training configurations, or evaluation metrics.Python# Tuning deep learning training parameters
hyperparameters = {
    "learning_rate": 0.001,
    "batch_size": 32,
    "optimizer": "Adam"
}
⚡ 2. Python OperatorsOperators are special symbols used to perform computations on variables and values. In AI/ML, these form the baseline for mathematical equations and data filtering.Operator TypeSymbolsAI/ML Practical Use CaseArithmetic+, -, *, /, //, %, **Used in feature scaling, calculating gradients, or updating weights. (** is used for squaring errors).Comparison==, !=, >, <, >=, <=Used in filtering datasets (e.g., separating rows where Age > 30) or evaluating model threshold predictions.Logicaland, or, notUsed to combine multiple data cleaning conditions (e.g., Income > 50k00 and Credit_Score > 700).Assignment=, +=, -=, *=, /=Used for iterative routines, like accumulating loss values or updating optimization loops (loss += current_batch_loss).Membershipin, not inUsed to check if a specific column/feature exists inside a dataset or list.
