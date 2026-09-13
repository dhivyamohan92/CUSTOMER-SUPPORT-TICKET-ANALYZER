# CUSTOMER-SUPPORT-TICKET-ANALYZER


## 📌 Project Overview

The **Customer Support Ticket Analyzer** is a Python-based data analytics project that organizes, cleans, and analyzes customer support ticket data.

The project uses Python **dictionaries, lists, loops, functions, string operations, sets, and conditional statements** to process customer support issues and generate useful insights.

The program allows users to:

* View existing support tickets
* Add new tickets dynamically
* Automatically generate ticket numbers
* Validate ticket priorities
* Clean customer issue descriptions
* Analyze common keywords
* Analyze ticket priority distribution
* Find the longest issue description
* Identify unique words used across all tickets

---

## 🎯 Objectives

The main objectives of this project are:

* Organize customer support ticket data using Python
* Practice data cleaning and text processing
* Implement loops and conditional statements
* Create reusable Python functions
* Perform keyword-based text analysis
* Calculate basic summary statistics
* Identify unique words from text data
* Generate meaningful business insights

---

## 🛠️ Technologies Used

* **Python 3**
* **Google Colab / Jupyter Notebook**
* Python Data Structures
* String Manipulation
* Basic Data Analysis

---

## 📂 Dataset Structure

The project uses a dictionary containing four lists:

| Column              | Description              |
| ------------------- | ------------------------ |
| `Ticket_No`         | Unique ticket number     |
| `Customer_Name`     | Customer name            |
| `Issue_Description` | Customer's support issue |
| `Priority`          | High, Medium, or Low     |

### Sample Data

```python
ticket_data = {
    'Ticket_No': [1, 2, 3, 4, 5],
    'Customer_Name': [
        'Ravi',
        'Meera',
        'Sam',
        'Anu',
        'Rakesh'
    ],
    'Issue_Description': [
        'Internet not working!!!',
        'slow response, very poor service',
        'GREAT support! issue resolved.',
        'okay... need help',
        'not BAD but slow'
    ],
    'Priority': [
        'High',
        'Low',
        'High',
        'Medium',
        'Low'
    ]
}
```

---

# 🔄 Project Workflow

```text
Load Ticket Data
       ↓
Display Initial Tickets
       ↓
Add New Tickets
       ↓
Validate Ticket Priority
       ↓
Generate Ticket Numbers
       ↓
Clean Issue Descriptions
       ↓
Keyword Analysis
       ↓
Priority Analysis
       ↓
Find Longest Issue
       ↓
Find Unique Words
       ↓
Generate Final Insights
```

---

# 🧹 Data Cleaning

The project performs the following text-cleaning operations:

### 1. Convert text to lowercase

```python
text = text.lower()
```

Example:

```text
GREAT SUPPORT
```

becomes:

```text
great support
```

### 2. Replace shorthand

```python
text = text.replace("ok", "okay")
```

### 3. Remove punctuation

The following punctuation marks are removed:

```text
. , ! ? -
```

### 4. Remove extra spaces

```python
text = " ".join(text.split())
```

### 5. Remove leading and trailing spaces

```python
text = text.strip()
```

---

# 🔍 Keyword Analysis

A reusable function is created to count the number of tickets containing a particular word.

```python
def count_tickets_with_word(word):

    count = 0

    word = word.lower()

    for description in ticket_data['Issue_Description']:

        words = description.split()

        if word in words:

            count += 1

    return count
```

The project analyzes the following keywords:

* `poor`
* `good`
* `slow`
* `excellent`

### Initial Dataset Results

| Keyword   | Number of Tickets |
| --------- | ----------------: |
| Poor      |                 2 |
| Good      |                 3 |
| Slow      |                 3 |
| Excellent |                 1 |

> The results will change if additional tickets are entered by the user.

---

# 📊 Priority Analysis

The project calculates the number of tickets for each priority level.

```python
high_count = ticket_data['Priority'].count('High')

medium_count = ticket_data['Priority'].count('Medium')

low_count = ticket_data['Priority'].count('Low')
```

### Initial Dataset

| Priority  | Tickets |
| --------- | ------: |
| High      |       4 |
| Medium    |       3 |
| Low       |       3 |
| **Total** |  **10** |

---

# 📝 Longest Issue Description

The project calculates the number of words in every issue description and identifies the ticket with the highest word count.

The output includes:

* Ticket Number
* Customer Name
* Cleaned Issue Description
* Word Count

This helps identify tickets that contain more detailed customer concerns.

---

# 🔤 Unique Word Analysis

A Python `set` is used to identify unique words.

```python
unique_words = set()

for description in ticket_data['Issue_Description']:

    words = description.split()

    for word in words:

        unique_words.add(word)
```

The unique words are then sorted alphabetically:

```python
sorted_unique_words = sorted(unique_words)
```

The program displays:

* Total number of unique words
* Complete sorted list of unique words

---

# ➕ Adding New Tickets

Users can enter the number of new tickets they want to add.

The program automatically generates the next ticket number.

For example:

```text
Existing tickets: 1–10

New Ticket → 11
Next Ticket → 12
Next Ticket → 13
```

The program also validates priority input and accepts only:

```text
High
Medium
Low
```

Invalid values are rejected and the user is asked to enter the priority again.

---

# 🧠 Python Concepts Demonstrated

This project demonstrates:

* Variables
* Dictionaries
* Lists
* Indexing
* `for` loops
* `while` loops
* `if-else`
* `break`
* `continue`
* `try-except`
* Functions
* User input
* f-strings
* `.append()`
* `.count()`
* `.lower()`
* `.replace()`
* `.split()`
* `.strip()`
* `join()`
* `len()`
* `max()`
* `set()`
* `sorted()`

---

# 📈 Business Insights

The project provides basic insights that can help a customer support team:

1. Identify the distribution of high, medium, and low-priority tickets.
2. Identify frequently occurring words in customer complaints.
3. Detect negative keywords such as **poor** and **slow**.
4. Identify positive keywords such as **good** and **excellent**.
5. Find tickets with longer and more detailed issue descriptions.
6. Standardize customer feedback through text cleaning.
7. Support better understanding of common customer concerns.

---

# 📁 Project Structure

```text
Customer-Support-Ticket-Analyzer/
│
├── Customer_Support_Ticket_Analyzer.ipynb
│
├── README.md
│
└── Project_Documentation.docx
```

---

# 🚀 How to Run the Project

### Option 1 – Google Colab

1. Open Google Colab.
2. Upload `Customer_Support_Ticket_Analyzer.ipynb`.
3. Run the cells from top to bottom.
4. Enter the number of new tickets when prompted.
5. Enter the customer details.
6. Enter the issue description.
7. Enter the ticket priority.
8. Review the final analysis.

### Option 2 – Jupyter Notebook

1. Install Python.
2. Open Jupyter Notebook.
3. Open the project notebook.
4. Run all cells.
5. Provide inputs when requested.

---

# 💡 Sample User Input

```text
How many new tickets do you want to add? 2

Enter details for Ticket 11
Customer Name: Kumar
Issue Description: Internet is very slow!!!
Priority (High / Medium / Low): High

Enter details for Ticket 12
Customer Name: Priya
Issue Description: good support and quick response
Priority (High / Medium / Low): Medium
```

The ticket numbers are automatically assigned as **11 and 12**.

---

# 📌 Key Learning Outcomes

After completing this project, I gained practical experience in:

* Python data structures
* Text cleaning
* String manipulation
* Data transformation
* Keyword analysis
* Basic statistical summaries
* Functions and loops
* Input validation
* Data organization
* Extracting business insights from textual data

---

# 🏆 Conclusion

The **Customer Support Ticket Analyzer** demonstrates how Python can be applied to a simple real-world customer support analytics problem.

The project combines **data organization, data cleaning, text analysis, loops, functions, and summary statistics** to transform raw customer ticket information into useful insights.

This project is a practical demonstration of Python skills relevant to **Data Analytics and Business Intelligence**.

---

## 👩‍💻 Author

**Dhivya M**

**Aspiring Data Analyst | Power BI | SQL | Excel | Python**

---

⭐ If you found this project useful, feel free to explore the repository and provide feedback.
