### Command-Line Arguments:
   1. In Python, command-line arguments are inputs passed to a script when running it from the terminal.
   2. Command-line arguments excel at controlling immediate script behavior per execution.
      
      Python provides three primary ways to capture and process inputs sent directly from the console
     a. The Raw Approach: sys.argv:
        The sys module exposes sys.argv, a built-in list containing all elements typed in the shell execution statement.
      - sys.argv[0]: Contains the script name.
      - sys.argv[1:]: Contains all remaining arguments passed as strings.

import sys
#Execution: python script.py 10 "hello"

print(f"Script: {sys.argv[0]}")  # script.py
print(f"Arguments: {sys.argv[1:]}")  # ['10', 'hello']

### Environment Variables:
1. Environment variables are system-wide key-value pairs stored outside the application code to manage configurations and secrets.
2. Environment variables are ideal for keeping database credentials or API keys safe from source control.
   a. Native Reading & Writing: os.environ
      The native os module maps system environment settings to a Python dictionary format.
    - os.environ['KEY']: Retrieves a variable, but raises a KeyError if it is missing.
    - os.getenv('KEY', default): Safely retrieves a variable, returning None or a custom default if missing

import os

#Reading an environment variable

db_user = os.getenv("DB_USER", "guest") 

# Setting an environment variable mid-script (string values only)
os.environ["APP_STAGE"] = "production" 




