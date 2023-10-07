import requests
from bs4 import BeautifulSoup
import spacy

# Function to perform a Google search and retrieve search results
def google_search(query):
    # ... (same as before)

# Function to perform NLP using spaCy
def perform_nlp(text):
    # ... (same as before)

# Function to execute Python code
def execute_code(code):
    try:
        # Create a dictionary for local variables
        local_vars = {}
        # Execute the code with restricted globals and locals
        exec(code, globals(), local_vars)
        
        # Retrieve any variables created by the code
        results = {key: val for key, val in local_vars.items() if not key.startswith("__")}
        return results
    except Exception as e:
        return str(e)

# Example usage
query = "How does natural language processing work?"
search_results = google_search(query)

if search_results:
    for i, result in enumerate(search_results, start=1):
        print(f"Result {i}: {result}")

    # Perform NLP on the first search result
    if search_results:
        nlp_result = perform_nlp(search_results[0])
        print("\nNouns in the first search result:")
        print(nlp_result)

    # Example: Execute Python code
    code_to_execute = """
    x = 5
    y = 10
    result = x + y
    """
    code_execution_result = execute_code(code_to_execute)
    print("\nCode Execution Result:")
    print(code_execution_result)
else:
    print("Failed to retrieve search results.")