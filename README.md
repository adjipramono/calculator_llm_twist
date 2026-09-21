# Project: Calculator with a Natural-Language Twist

**Objective:** Build a Python program that acts like a smart assistant! Instead of typing rigid math equations, your user will ask math questions in plain English (like "what is 10 percent of 250?"), and your program will figure out what they mean and calculate the answer.

## 📋 Requirements

Your program must meet the following criteria:

1. **Accept Natural Language:** Ask the user to input a math question as a full sentence.

2. **Extract Numbers:** Find and pull out any numbers hidden inside the user's sentence, including decimals (floats).

3. **Keyword Detection:** Search the user's sentence for specific math words to decide which operation to perform.

4. **Supported Operations:**

   * **Percentages:** Triggered by the word `"percent"`.

   * **Addition:** Triggered by `"plus"`, `"sum"`, or `"add"`.

   * **Subtraction:** Triggered by `"minus"` or `"difference"`.

   * **Multiplication:** Triggered by `"times"`, `"multiplied"`, or `"product"`.

   * **Division:** Triggered by `"divided"` or `"quotient"`.

5. **Fallback Message:** If the program doesn't recognize the math words, it should print a polite error message (e.g., "Sorry, I couldn't understand that question.").

## 🛠️ Step-by-Step Guide

### Step 1: Get Input and Clean It

* Prompt the user to ask a math question.

* Convert the entire input string to lowercase using `.lower()`. This ensures that "Add" and "add" are treated the same way.

### Step 2: Extract the Numbers

* You need to isolate the numbers from the rest of the words. Break the sentence into a list of words using `.split()`.

* Loop through the list of words. If a word is a number, convert it to a `float` and save it in a new list.

* *Pro-Tip for Decimals:* Python's built-in `.isdigit()` method gets confused by the decimal point in floats. To check if a string is a float, you can temporarily remove the decimal point like this: `word.replace('.', '', 1).isdigit()`.

### Step 3: Keyword Detection (The Logic)

* Use an `if/elif/else` block to check if certain math keywords exist in the user's sentence (e.g., `if "percent" in text:`).

* Make sure you check for multiple keywords for the same operation using `or` (e.g., `elif "plus" in text or "add" in text:`).

### Step 4: Calculate and Print

* Once you know what operation to perform, use the numbers you extracted in Step 2 to do the math.

* For addition, you can use Python's built-in `sum()` function to add up all extracted numbers.

* For the others, you can usually assume the first extracted number is `numbers[0]` and the second is `numbers[1]`.

* *Don't forget to prevent division by zero!*

## 💻 Example Output

**Run 1:**

```
Ask a math question (e.g. 'what is 10 percent of 250'): What is 15 percent of 80?
15.0% of 80.0 is 12.0

```

**Run 2:**

```
Ask a math question (e.g. 'what is 10 percent of 250'): Please add 4.5 and 9
Sum: 13.5

```

**Run 3:**

```
Ask a math question (e.g. 'what is 10 percent of 250'): What's the capital of France?
Sorry, I couldn't understand that question.

```

## 🚀 Bonus Challenges (Optional)

Finished early? Try adding these features:

1. **Continuous Loop:** Wrap your program in a `while` loop so the user can keep asking questions until they type "quit" or "exit".

2. **Integrate a Real LLM (AI):** Instead of using basic `if/elif` keyword checks, connect your Python script to a real Large Language Model! 
   * Sign up for a free API key from a provider like **Google Gemini**, **Groq**, or **Hugging Face**.
   * Use Python's `requests` library (or the provider's official SDK) to send the user's math question to the AI.
   * Write a prompt instructing the AI to output *only* the final mathematical answer.
   * *Hint:* This is exactly how modern AI assistants understand complex natural language!

3. **Advanced Math:** Add support for exponents (e.g., "what is 2 to the power of 3") or square roots.