import os
import subprocess

# Step 1: Create a new directory for the repository
repo_dir = 'simple_git_repo'
os.makedirs(repo_dir, exist_ok=True)
print(f"Directory '{repo_dir}' created.")

# Step 2: Initialize a new Git repository in that directory
os.chdir(repo_dir)
subprocess.run(['git', 'init'])
print("Git repository initialized.")

# Step 3: Create a simple text file in the repository
file_name = 'README.md'
with open(file_name, 'w') as file:
    file.write("# Simple Git Repository\nThis is a simple README file for our Git repository.")
print(f"File '{file_name}' created.")

# Step 4: Add the text file to the staging area
subprocess.run(['git', 'add', file_name])
print(f"File '{file_name}' added to staging area.")

# Step 5: Commit the added file to the repository
commit_message = 'Initial commit'
subprocess.run(['git', 'commit', '-m', commit_message])
print(f"Changes committed with message: '{commit_message}'.")
