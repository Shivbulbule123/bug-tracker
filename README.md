# bug-tracker
import requests
import json

# Authentication credentials
username = 'your-username'
password = 'your-password'
repository = 'your-repository'
owner = 'your-repository-owner'

# URL for creating an issue
url = f'https://api.github.com/repos/{owner}/{repository}/issues'

# Headers
headers = {'Content-Type': 'application/json'}

# Issue data
issue = {
    'title': 'Bug: Description of the bug',
    'body': 'Detailed description of the bug, including steps to reproduce',
    'labels': ['bug']
}

# Send a POST request to create the issue
response = requests.post(url, headers=headers, auth=(username, password), data=json.dumps(issue))

# Check if the issue was created successfully
if response.status_code == 201:
    print('Issue created successfully.')
else:
    print('Error creating issue:', response.content)
