# 2025-ITELEC2-LAB012
Week 04 - Conditional Statements

Laboratory # 12 - Guided Coding Exercise: Simulating a Switch Statement and Ternary Operator in Python

## **Instructions**

### **Step 1.1: Accept the Assignment**

   1. Click on the assignment link provided by your instructor.
   2. GitHub Classroom will create a **private repository** under your GitHub account.
   3. After the repository is created, click **"Go to Repository"** to view your assignment.

---

### **Step 1.2: Setup your Git Environment**
Only perform this if this is the first time you will setup your Git Environment

   1. Create a GitHub Account:
   ```bash
   https://github.com/signup?source=login
   ```
      
   2. Download and Install Git on your Laptop/Desktop:
   ```bash
   https://git-scm.com/downloads
   ```
   
   3. Create a Folder in your Laptop/Desktop
   4. Right-click anywhere in the created folder and select "Open Git Bash Here".
   5. In the Git Bash Terminal, set your git name, perform command:
   ```bash
   git config --global user.name "Your Name"
   ```
   
   6. In the Git Bash Terminal, set your git email, perform command:
   ```bash
   git config --global user.email "your.email@example.com"
   ```
   
   7. Create your SSH Key, just follow the instructions, no need to provide filename and passphrase. In the Git Bash Terminal, perform command:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
   
   8. Copy your SSH Keys into clipboard. In the Git Bash Terminal, perform command:
   ```bash
   clip < ~/.ssh/id_rsa.pub
   ```
   
   9. Log in to your GitHub account.
   10. In the upper-right corner of GitHub, click your profile picture and select Settings.
   11. In the left sidebar, click on SSH and GPG keys.
   12. Click the New SSH key button.
   13. In the Title field, give the key a recognizable name (e.g., "My Windows Laptop").
   14. In the Key field, CTRL + V or paste the keys copied into your clipboard. Save the key.
   15. Go Back to terminal, use command:
   ```bash
   ssh -T git@github.com
   ```

### **Step 2: Clone the Repository to Your Local Machine**

   1. On your repository page, click the green **"Code"** button.
   2. Copy the repository URL (choose HTTPS for simplicity).
   3. Open your terminal (or Git Bash, Command Prompt, or PowerShell) and run:
   
   ```bash
   git clone <git_repo_url>
   ```
   
   4. Navigate into the cloned folder:
   
   ```bash
   cd <git_cloned_folder>
   ```

### **Step 3: Complete the Assignment**

**Laboratory # 12 - Guided Coding Exercise: Simulating a Switch Statement and Ternary Operator in Python**

   **Objective:**
   - Understand how to simulate a switch statement in Python using a dictionary.
   - Learn how to use the ternary operator for inline conditional expressions.
   - Practice dictionary lookups and handling default values.
   - Reinforce input handling and string manipulation.

   **Desired Output (Example 1):**
   ```bash
   Enter a day of the week: Monday
   Today is Monday.
   It's a Weekday!
   ```
   **Desired Output (Example 2):**
   ```bash
   Enter a day of the week: saturday
   Today is Saturday.
   It's a Weekend!
   ```
   **Desired Output (Example 3):**
   ```bash
   Enter a day of the week:  tuesday 
   Today is Tuesday.
   It's a Weekday!
   ```
   **Desired Output (Example 4):**
   ```bash
   Enter a day of the week:  Funday
   Invalid day entered.
   It's a Weekday!
   ```
      
   **Notable Observations (to be discussed after completing the exercise):**
   - Python does not have a built-in switch statement like some other languages. Dictionaries provide a clean and efficient way to achieve similar functionality.
   - The .get() method of a dictionary allows you to retrieve a value associated with a key. Crucially, it also lets you specify a default value that will be returned if the key is not found in the dictionary. This is very useful for handling cases where the user might enter invalid input.
   - The ternary operator (value_if_true if condition else value_if_false) provides a concise way to write conditional expressions in a single line. It's useful for simple conditions where you want to assign one of two values.
   - String methods like .strip() and .lower() are essential for normalizing user input, making your code more robust.

   **Python Best Practices**
   - Input Normalization: Always normalize user input (e.g., convert to lowercase using .lower() and remove leading/trailing whitespace using .strip()) to handle variations in user input and prevent unexpected behavior.
   - Dictionary .get() with Default: Use the .get() method with a default value when retrieving values from a dictionary. This is a best practice, especially when dealing with user input, as it provides a clean way to handle cases where the key might not exist.
   - Readability: Even with concise constructs like the ternary operator, prioritize code readability. If a ternary expression becomes too complex, consider using a regular if...else statement for clarity.
   - Descriptive Variable Names: Use meaningful variable names (e.g., day_messages, day, message, day_type).
   - Comments: Add comments to explain your logic, especially when simulating control flow structures like a switch statement.
   - Test Thoroughly: Test your code with various inputs, including valid days of the week (with different capitalization and spacing) and invalid days, to ensure it handles all cases correctly.

   **Step-by-Step Instructions:**

   1. Setting up: Open your preferred Python environment or Text Editor, and create a Python Script.
      - Required Filename: `switch_ternary_operator.py`
      
   2.  Create a dictionary to simulate a switch statement:
      - Create a dictionary named day_messages. The keys of the dictionary should be the days of the week (in lowercase). The values should be the corresponding messages (e.g., "Today is Monday.", "Today is Tuesday.", etc.).
```python
day_messages = {
    "monday": "Today is Monday.",
    "tuesday": "Today is Tuesday.",
    "wednesday": "Today is Wednesday.",
    "thursday": "Today is Thursday.",
    "friday": "Today is Friday.",
    "saturday": "Today is Saturday.",
    "sunday": "Today is Sunday."
}
```
      
   3.  Get input from the user and normalize it:
      - Use the input() function to prompt the user to enter a day of the week.
      - Use .strip() to remove any leading or trailing whitespace from the user's input.
      - Use .lower() to convert the input to lowercase. This makes the comparison case-insensitive.
      - Store the normalized input in a variable named day.
```python
day = input("Enter a day of the week: ").strip().lower()
```

   4. Retrieve the message using the dictionary with a default:
      - Use the .get() method of the day_messages dictionary to retrieve the message associated with the day entered by the user.
      - Provide a default value to the .get() method. This default value will be returned if the day is not found as a key in the dictionary. Use something like "Invalid day entered." as the default.
      - Store the returned message in a variable named message.
```python
message = day_messages.get(day, "Invalid day entered.")
```

   5. Use the ternary operator to determine weekend vs. weekday:
      - Use the ternary operator to determine if the day is a weekend (Saturday or Sunday) or a weekday.
      - The condition should check if day is present in the tuple ("saturday", "sunday").
      - If the condition is true, assign the string "Weekend" to the variable day_type. Otherwise, assign "Weekday".
```python
day_type = "Weekend" if day in ("saturday", "sunday") else "Weekday"
```

   6. Use the ternary operator to determine weekend vs. weekday:
      - Use the print() function to display the message (from the dictionary lookup) and the day_type (determined by the ternary operator).
```python
print(message)
print("It's a", day_type + "!")
```

   7. Complete Code: Combine the steps above to form the complete program.
   8. Run the code: Execute your Python code.
   9. Observe the output: Test the program with different days of the week (including variations in capitalization and spacing) and invalid day names.

   **Conclusion**
   This exercise demonstrated two important Python techniques: simulating a switch statement using dictionaries and using the ternary operator for concise conditional expressions. You learned how to use dictionary lookups with default values and how to normalize user input for more robust code.  These techniques are valuable tools for writing cleaner, more efficient, and easier-to-read Python code.

### **Step 4: Push Changes to GitHub**
Once you've completed your changes, follow these steps to upload your work to your GitHub repository.

1. Check the status of your changes:
   Open the terminal and run:
   
```bash
git status
```
   This command shows any modified or new files.
   
2. Stage the changes:
   Add all modified files to staging:
   
```bash
git add .
```
   
3. Commit your changes:
   Write a meaningful commit message:
   
```bash
git commit -m "Submitting Python Week 04 - Laboratory # 12"
```
   
4. Push your changes to GitHub:
   Upload your changes to your remote repository:
   
```bash
git push origin main
```
