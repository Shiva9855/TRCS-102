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

📔 AI/ML Diary - Day 2

📌 Topics CoveredDeep Dive into Advanced Data Structures (Tuple, Set, Dictionary)Python OperatorsPractical Relevance in AI/ML

🗂️ 1. Advanced Data Structures (Quick Recap & Nuances)

🔹 Tuple ()Key Concept: Ordered and Immutable (cannot be modified after creation).
AI/ML Use Case: Used to pass structural configurations that must remain constant, like input shape tensors or weights metadata.Python# Image dimensions: Height, Width, Channels (RGB)
input_shape = (224, 224, 3) 


🔹 Set {}Key Concept: Unordered collection of Unique elements. Automatically eliminates duplicates.
AI/ML Use Case: Perfect for finding unique target labels or filtering out duplicate entries during data preprocessing.Python# Extracting unique classes from a text dataset
target_classes = {"Spam", "Ham", "Spam"} # Result: {'Spam', 'Ham'}


🔹 Dictionary {Key: Value}Key Concept: Unordered, mutable collection of Key-Value pairs. Fast lookups using unique keys.
AI/ML Use Case: Extensively used for setting up model hyperparameters, training configurations, or evaluation metrics.Python# Tuning deep learning training parameters
hyperparameters = {
    "learning_rate": 0.001,
    "batch_size": 32,
    "optimizer": "Adam"
}


⚡ 2. Python OperatorsOperators are special symbols used to perform computations on variables and values. In AI/ML, these form the baseline for mathematical equations and data filtering.Operator TypeSymbolsAI/ML Practical Use CaseArithmetic+, -, *, /, //, %, **Used in feature scaling, calculating gradients, or updating weights. (** is used for squaring errors).


Comparison==, !=, >, <, >=, <=Used in filtering datasets (e.g., separating rows where Age > 30) or evaluating model threshold predictions.


Logicaland, or, notUsed to combine multiple data cleaning conditions (e.g., Income > 50k00 and Credit_Score > 700).


Assignment=, +=, -=, *=, /=Used for iterative routines, like accumulating loss values or updating optimization loops (loss += current_batch_loss).Membershipin, not inUsed to check if a specific column/feature exists inside a dataset or list.


📔 AI/ML Diary - Day 3

📌 Topics Covered

Conditional Statements (if, elif, else)

Loop Control Statements (break, continue)

Switch Case/Structural Pattern Matching in Python

🚦 1. Conditional Statements

Conditional statements allow our code to make decisions based on certain criteria. In AI/ML, these are widely used for filtering data, setting prediction thresholds, or routing model outputs.

if: Executes a block of code only if a specified condition is true.

elif (short for else if): Checks another condition if the previous conditions were false.

else: Executes if none of the above conditions are met.


🤖 AI/ML Practical Use Case:
Setting classification thresholds for a machine learning model prediction.

Python:code

prediction_probability = 0.85

if prediction_probability >= 0.80:

    print("High Confidence: Dog")
    
    elif prediction_probability >= 0.50:
    
    print("Low Confidence: Dog")
    
else:

    print("Classification: Cat")


    
🔄 2. Loop Control Statements

Loop control statements change the execution flow from its normal sequence.

🚫 break

Concept: Terminates the loop entirely and transfers execution to the statement immediately following the loop.

AI/ML Use Case: Early Stopping. If your model's loss stops decreasing or starts increasing (overfitting), you break the training loop early to save time and compute power.

Python:code

for epoch in range(1, 100):

    if loss < 0.001:
    
        print("Target accuracy reached. Stopping training.")
        
        break

        
⏭️ continue

Concept: Skips the rest of the current iteration and moves directly to the next iteration of the loop.

AI/ML Use Case: Skipping corrupted, missing (NaN), or invalid data points during data preprocessing.

Python : code


for image in dataset:

    if image.is_corrupted:
    
        continue  # Skip this image and move to the next
        
    process_image(image)

    
🎛️ 3. Switch Statement (Match-Case)

Historically, Python did not have a traditional switch statement like C++ or Java. However, from Python 3.10+, structural pattern matching using the match and case keywords was introduced.

Concept: Compares a variable against multiple possible values (patterns) in a cleaner way than long if-elif-else chains.

AI/ML Use Case: Routing different evaluation metrics or selecting specific optimization algorithms based on user configuration.

Python:code

optimizer = "Adam"

match optimizer:

    case "SGD":
    
        print("Initializing Stochastic Gradient Descent")
        
    case "Adam":
    
        print("Initializing Adam Optimizer")
    case "RMSprop":
        print("Initializing RMSprop Optimizer")
    case _:
        print("Unknown optimizer. Defaulting to SGD.")  # '_' acts as the 'default' case


📔 AI/ML Diary - Day 4       
📌 Topics Covered

Introduction to Loops

The for Loop

The while Loop

Infinite Loops (while True)

Introduction to Functions

🔄 1. Loops in Python

Loops are used to execute a block of code repeatedly. In AI/ML, loops are fundamental for iterating through large datasets, processing images one by one, or running iterative training algorithms across multiple iterations (epochs).

🔹 The for Loop

Concept: Used for iterating over a sequence (like a list, tuple, dictionary, set, string, or a range of numbers). It runs a specific number of times.

AI/ML Use Case: Iterating through epochs to train a model, or looping over a list of files to load data.

Python

# Simulating a model training loop over 3 epochs
for epoch in range(1, 4):
   print(f"Training Epoch {epoch}...")
    
🔹 The while Loop

Concept: Executes a block of code as long as a specified condition remains True. It is used when the exact number of iterations is not known beforehand.

AI/ML Use Case: Training an agent in Reinforcement Learning until it reaches a specific goal or target score.

Python

loss = 0.5
# Loop runs until the loss drops below the acceptable threshold
while loss > 0.1:
    print(f"Current loss: {loss:.2f}. Optimizing model...")
       loss -= 0.15  # Simulating loss reduction
    
🔹 Infinite Loops (while True)

Concept: A loop that runs indefinitely because its conditional expression always evaluates to true. It is usually paired with a break statement to exit based on an internal trigger.

AI/ML Use Case: Setting up real-time computer vision or camera streams (e.g., OpenCV) where the script must process video frames continuously until the user presses a 'quit' key.

Python
# Simulating a continuous video stream frame processor

while True:

    frame_status = check_camera_feed()
    if frame_status == "No Frame" or user_pressed_esc():
        print("Stopping video stream.")
        break 
    process_frame()
    

📔 AI/ML Diary - Day 5

📌 Topics Covered
Deep Dive into Functions

Functions with Arguments (Positional, Keyword, Default, *args, kwargs)

Recursion in Python

🧩 1. Deep Dive into Functions
Functions are self-contained modules of code that accomplish a specific task. They prevent code duplication and make machine learning pipelines cleaner, scalable, and easier to debug.

Python

def greet_developer():

    print("Ready to train models!")

greet_developer()  # Calling the function


⚙️ 2. Functions with Arguments

Arguments are the actual data/values passed into a function when calling it. Python offers highly flexible ways to handle inputs, which is essential when configuring intricate ML model architectures.

🔹 Positional & Keyword Arguments

Positional: Arguments passed in the exact sequence defined by the function.

Keyword: Arguments passed explicitly using name=value pairs, ignoring the sequence.

Python

def configure_layer(neurons, activation):

    print(f"Layer created with {neurons} neurons and {activation} activation.")

configure_layer(64, "ReLU")               # Positional

configure_layer(activation="Sigmoid", neurons=32) # Keyword


🔹 Default Arguments

Allows parameters to have a default value if no argument is passed during the function call. This is exactly how popular ML libraries like Scikit-Learn handle hyperparameters (e.g., defaulting learning_rate or max_depth).

Python

def train_model(epochs=10):  # Default value is 10

    print(f"Training model for {epochs} epochs...")

train_model()    # Uses default (10)

train_model(50)  # Overrides default to 50

🔹 Arbitrary Arguments (*args and kwargs)

*args (Non-Keyword Arguments): Allows a function to accept any number of positional arguments as a tuple.

kwargs (Keyword Arguments): Allows a function to accept any number of keyworded arguments as a dictionary.

Python

# *args Use Case: Passing multiple feature arrays to process at once
def clean_features(*features):

    print(f"Processing datasets: {features}") 

# **kwargs Use Case: Dynamic hyperparameter configurations
def build_model(**hyperparameters):

    for param, value in hyperparameters.items():
    
        print(f"Setting {param} to {value}")

build_model(lr=0.01, batch_size=64, optimizer="Adam")


🔄 3. Recursion

Recursion is a programming technique where a function calls itself directly or indirectly to solve a smaller instance of the same problem.

Every recursive function requires:

Base Case: The condition that stops the recursion from running infinitely.

Recursive Case: The part where the function calls itself with a modified input.

🤖 AI/ML Relevance:

Recursion is heavily utilized in tree-based machine learning algorithms (like Decision Trees and Random Forests) to split nodes into child branches until a stopping criterion (base case) is reached.

Python

# Classic Example: Calculating Factorial
def factorial(n):

    if n == 1:  # Base Case
    
        return 1
        
    else: # Recursive Case
    
        return n * factorial(n - 1)

print(factorial(5))  # Output: 120


📔 AI/ML Diary - Day 6

📌 Topics Covered

Introduction to File Handling

File Operations (Open, Read, Write, Close)

File Modes (r, w, a, r+)

The with Statement (Context Manager)

Relevance in AI/ML

📂 1. Introduction to File Handling

File handling is a crucial concept in programming that allows us to create, read, update, and delete files stored on the local disk.

In AI/ML, data rarely lives directly inside your code script. Instead, it is stored externally in formats like .txt, .csv, .json, or .xlsx. Learning how to stream and manipulate these files is the first step toward building actual data pipelines.

⚙️ 2. Basic File Operations & Modes
Python has a built-in open() function to interact with files. It requires two main parameters: the File Name and the Mode.

🛠️ Common File Modes:

'r' (Read): Default mode. Opens a file for reading; raises an error if the file does not exist.

'w' (Write): Opens a file for writing. Creates a new file if it doesn't exist, or truncates (overwrites) the file if it does.

'a' (Append): Opens a file to add data to the end of it without erasing existing content.

'rb' / 'wb' (Binary Modes): Used for non-text files like images, videos, or serialized ML models.

🚫 The Traditional Approach (Manual Close):

When you open a file manually, you must close it using .close() to free up system memory resources.

Python

file = open("dataset.txt", "r")

content = file.read()

print(content)

file.close()  # Mandatory to avoid memory leaks


🔒 3. The Modern Approach: Using with Keyword

The standard best practice in Python is using the with statement (also known as a Context Manager).

Why use it?: It automatically closes the file as soon as the nested code block completes execution, even if an unexpected error or crash occurs midway.

Python

# Writing to a log file
with open("training_logs.txt", "w") as file:

    file.write("Epoch 1: Loss = 0.045\n")
    
    file.write("Epoch 2: Loss = 0.012\n")

# Reading from the log file
with open("training_logs.txt", "r") as file:

    lines = file.readlines()  # Reads file line by line into a list
    
    for line in lines:
    
        print(line.strip())
        
🤖 4. Practical Relevance in AI/ML

File handling forms the foundation for data ingestion and model persistence:

Loading Raw Data: Parsing unstructured .txt text files for Natural Language Processing (NLP) or loading flat config metrics.

Saving Logs: Recording loss, accuracy values, and timestamp details during long training sessions so you can inspect them later.

Model Serialization (Pickling): Saving your trained algorithm weights into a binary file (.pkl or .h5) onto the disk so it can be deployed to production later without retraining.



📔 AI/ML Diary - Day 7

📌 Topics Covered

Introduction to Errors vs. Exceptions

The try-except Block

Handling Multiple Exceptions

The else and finally Blocks

Raising Custom Exceptions (raise)

Relevance in AI/ML

⚠️ 1. Errors vs. Exceptions

Syntax Errors: Mistakes in the code structure that prevent Python from compiling/running it (e.g., forgetting a colon : or bad indentation).

Exceptions: Errors detected during execution (runtime). The syntax is correct, but an operation fails (e.g., dividing by zero or trying to load a file that doesn't exist).

If an exception is not handled, the program crashes instantly. In production AI pipelines, we use Exception Handling to keep the application running smoothly even when errors occur.

🛠️ 2. The Core Exception Blocks (try, except, else, finally)

Python handles exceptions using a structured block layout:

Python

try:

    # Code that might crash/throw an exception
    
    result = 10 / 0
    
except ZeroDivisionError as e:

    # Code that executes if a specific exception occurs
    
    print(f"Error caught: {e}")
    
else:

    # Code that executes ONLY if NO exception occurred in the try block
    
    print("Everything ran successfully!")
    
finally:

    # Code that ALWAYS executes, no matter what (used for cleanup)
    
    print("Cleanup operations complete.")

    
🗂️ 3. Handling Multiple Exceptions

A single block of code can throw different types of exceptions. You can catch them specifically to handle each scenario cleanly.

Python

try:

    with open("dataset.csv", "r") as file:
    
        data = file.read()
        
    value = data[10] / 0  # Might trigger IndexError or ZeroDivisionError
    

except FileNotFoundError:

    print("The requested data file is missing!")
    
except ZeroDivisionError:

    print("Cannot compute metrics; division by zero encountered.")
    
except Exception as e:

    # Generic catch-all for any other unforeseen errors
    
    print(f"An unexpected error occurred: {e}")

    
🚀 4. Raising Exceptions (raise)

You can force an exception to occur manually using the raise keyword if specific business logic constraints are violated.

Python

def check_batch_size(batch_size):

    if batch_size <= 0:
    
        raise ValueError("Batch size must be a positive integer greater than 0!")
        
    print(f"Batch size configured to {batch_size}")

check_batch_size(-5) 


🤖 5. Practical Relevance in AI/ML

Exception handling is vital for building resilient automation and data science loops:

Robust Data Ingestion: If you are scraping thousands of images or text files from the web and one link is broken (URLError / HTTPError), an exception handler allows your script to skip that file and continue downloading the rest without crashing.

Dynamic System Checkpoints: Ensuring user inputs match model expectations (e.g., throwing an error if a user submits text data to a model that only takes image arrays).

API Deployment: When serving a model using frameworks like Flask or FastAPI, exception blocks ensure that invalid incoming user requests return a clean 400 Bad Request error message instead of crashing the entire backend server.



📔 AI/ML Diary - Day 8

📌 Topics Covered

Introduction to Object-Oriented Programming (OOP) in Python

What is Inheritance?

Types of Inheritance (Single, Multiple, Multilevel, Hierarchical, Hybrid)

Relevance in AI/ML

🏗️ 1. What is Inheritance?

Inheritance is a core pillar of OOP that allows a Child class (Derived class) to adopt attributes and methods from a Parent class (Base class). This promotes code reusability and helps build organized, scalable software architectures.

🌿 2. Types of Inheritance in Python

🔹 1. Single Inheritance

A child class inherits from only one parent class.

AI/ML Use Case: Creating a specific baseline Neural Network layer from a generic layer template.

Python

class Model: # Parent

    def train(self): print("Training...")

class LinearRegression(Model): # Child

    def predict(self): print("Predicting...")

    
🔹 2. Multiple Inheritance

A child class inherits features from more than one parent class.

AI/ML Use Case: Combining separate independent utilities, like an image data preprocessor and an evaluation logger, into a single trainer pipeline.

Python

class DataPreprocessor: def clean(self): print("Cleaning data...")

class Logger: def log(self): print("Logging metrics...")

class TrainingPipeline(DataPreprocessor, Logger): # Inherits from both

    pass

    
🔹 3. Multilevel Inheritance

A child class inherits from a parent class, which itself is a child of another parent class (forming a chain).

Python

class Component: def initialize(self): print("Hardware Init")

class GPU(Component): def allocate_mem(self): print("VRAM allocated")

class CudaCore(GPU): def compute(self): print("Parallel processing execution")


🔹 4. Hierarchical Inheritance

Multiple child classes inherit from one single parent class.

AI/ML Use Case: This is exactly how popular frameworks like PyTorch or Scikit-Learn structure their algorithms. A base model class branches out into specific architectures.

Python

class Classifier: # Single Parent

    def evaluate(self): print("Calculating Accuracy...")

class SVM(Classifier): pass       # Child 1

class RandomForest(Classifier): pass # Child 2


🔹 5. Hybrid Inheritance

A blend of two or more types of inheritance mentioned above. It often forms a diamond shape structure, which Python resolves smoothly using the MRO (Method Resolution Order) protocol.

🤖 3. Practical Relevance in AI/ML

If you open the source code of library tools like PyTorch (torch.nn.Module) or Scikit-Learn (BaseEstimator), you will see that everything relies heavily on inheritance:

Custom Deep Learning Layers: When building a custom neural network layer in PyTorch, your custom class must inherit from nn.Module. This lets your class automatically use heavy background tools like .to('cuda'), parameters tracking, and backpropagation mechanics without you having to code them from scratch.

Custom Scikit-Learn Transformers: By inheriting from BaseEstimator and TransformerMixin, your custom text/image cleaner can plug cleanly directly into a standard Pipeline object.
