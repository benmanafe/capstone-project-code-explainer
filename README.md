# capstone-project-code-explainer

Dataset Link: https://www.kaggle.com/datasets/thedevastator/python-code-instruction-dataset

# **Project overview**

This project is about being able for AI to be able to explain the code clearly based on the code itself presented, the input and the expected output. The output of this project is the model hopefully is able to produce the code explanation from the given code. For this project, I used granite-3.3-8b-instruct because we are dealing with codes with specific use cases and can be very long lines of code. We will first get the dataset and feed it to the model which hopefully will give a good explanation of the code given.

# **Analysis process**

Since codes can be very long and specific, I used granite-3.3-8b-instruct which can handle those things really well. The process is just gonna feed the dataset to the model, train it and hopefully give a good explanation on the code.

# **Insights & Findings**

## **Input**
--- Selected Problem Instruction: --- 
Create a python code to convert a string of comma-separated numbers into list.

--- Corresponding Input: --- 
numbers = '1,2,3,4,5,6' 

--- Original Code Generation Prompt: --- 
Below is an instruction that describes a task. Write a response that appropriately completes the request. ### Instruction: Create a python code to convert a string of comma-separated numbers into list. ### Input: numbers = '1,2,3,4,5,6' ### Output: numbers = '1,2,3,4,5,6' numbers_list = [int(x) for x in numbers.split(',')] print(numbers_list) # [1, 2, 3, 4, 5, 6] 

--- Code to be Explained: --- 
```python numbers = '1,2,3,4,5,6' numbers_list = [int(x) for x in numbers.split(',')] print(numbers_list) # [1, 2, 3, 4, 5, 6] ```

---

## **Prompt**
prompt = f"""You are an expert programmer and code explainer.
Please explain the following Python code snippet in simple, clear language.
The code was generated to fulfill the following instruction:
"{problem_instruction}"

 It was designed to handle input like:
"{problem_input}"

Focus on:
1. **Purpose:** What does the code aim to achieve, considering the instruction?
2. **How it Works:** Step-by-step breakdown of its functionality.
3. **Key Concepts/Libraries:** Mention any important programming concepts or external libraries used.

Code:
``python
{code_to_explain}"""

---

## **Output**
--- Code Explanation (from Granite) --- 

1. Purpose: The purpose of this Python code snippet is to convert a string of comma-separated numbers into a list of integers. This fulfills the instruction provided, which required creating a Python code to handle input like "1,2,3,4,5,6" and convert it into a list format suitable for numerical operations.
2. How it Works: 
- First, the code assigns the string '1,2,3,4,5,6' to the variable `numbers`. - The line `numbers.split(',')` splits this string into a list of substrings using the comma (`,`) as a delimiter. The result is `['1', '2', '3', '4', '5', '6']`.
3. Key Concepts/Libraries:
- **String Splitting:** The `split()` method is a built-in Python string method that divides a string into a list of substrings based on a specified delimiter. In this case, the delimiter is a comma (`,`).
- **List Comprehension:** This is a concise way to create lists in Python. It consists of brackets `[]` enclosing an expression followed by a `for` clause, then zero or more `for` or `if` clauses. The expression is evaluated once for each item in the input list (or other iterable), and the results are collected into a new list.
- **Type Conversion:** The `int()` function is used to convert a string or a number (in string format) to an integer.


This code efficiently converts a comma-separated string of numbers into a list of integers using basic Python functionalities without the need for external libraries.

- The list comprehension `[int(x) for x in numbers.split(',')]` then iterates over each element (`x`) in the list obtained from the previous step. For each `x`, it applies the `int()` function to convert the string representation of a number into an integer. 

- As a result, a new list `numbers_list` is created containing the integer values `[1, 2, 3, 4, 5, 6]`. - Finally, the `print(numbers_list)` statement outputs this list to the console.

Based on those code outputs, we can safely assume that the model was able to explain the code very well. The explanations are on point and clear enough with a good step-by-step to it.

# **Conclusion & Recommendations**

From the output, we can see that the model performed well and can be very good to use for people starting to code and need some explanations on how to do things.

# **AI support Explanations**
AI is used here to explain code starting from taking in the input from the dataset, analyzing it and give a clear output. It is basically the core of this project.

AI is used here to explain code starting from taking in the input from the dataset, analyzing it and give a clear output. It is basically the core of this project.
