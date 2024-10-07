 ## Post Request to send notes to Notion
 ``` Python
 
 import requests

def create_notion_page(database_id, token, title, content, checkbox=False, status_name="Not started"):
url = "https://api.notion.com/v1/pages"
headers = {
    "Authorization": f"Bearer {token}",
    "Content-Type": "application/json",
    "Notion-Version": "2022-06-28"
}

new_page_data = {
    "parent": {
        "database_id": database_id
    },
    "properties": {
        "All Tasks": {
            "title": [
                {
                    "text": {
                        "content": title
                    }
                }
            ]
        },
        "Checkbox": {
            "checkbox": checkbox
        },
        "Status": {
            "status": {
                "name": status_name
            }
        }
    },
    "children": [
        {
            "object": "block",
            "type": "paragraph",
            "paragraph": {
                "rich_text": [
                    {
                        "type": "text",
                        "text": {
                            "content": content
                        }
                    }
                ]
            }
        }
    ]
}

response = requests.post(url, headers=headers, json=new_page_data)

if response.status_code in range(200, 300):
    print("Page created successfully.")
else:
    print(f"Failed to create page: {response.status_code}")
    print(response.json())
def create_journal_entry(database_id, token, title, content):
url = "https://api.notion.com/v1/pages"
headers = {
    "Authorization": f"Bearer {token}",
    "Content-Type": "application/json",
    "Notion-Version": "2022-06-28"
}

new_page_data = {
    "parent": {
        "database_id": database_id
    },
    "properties": {
        "Journal Entries": {
            "title": [
                {
                    "text": {
                        "content": title
                    }
                }
            ]
        }
    },
    "children": [
        {
            "object": "block",
            "type": "paragraph",
            "paragraph": {
                "rich_text": [
                    {
                        "type": "text",
                        "text": {
                            "content": content
                        }
                    }
                ]
            }
        }
    ]
}

response = requests.post(url, headers=headers, json=new_page_data)

if response.status_code in range(200, 300):
    print("Journal entry created successfully.")
else:
    print(f"Failed to create journal entry: {response.status_code}")
    print(response.json())
```


## Todo Code
```Python
import os
from datetime import datetime
from post import create_notion_page, create_journal_entry

database_id_tasks = "f0560618bd4f491e97c3725ed02c1882"  # Change to your actual task database ID
database_id_journal = "27708705-f2ea-4270-a13a-9d4a973a0c6c"  # Change to your actual journal database ID
token = "secret_MncrJScqXqxF9UA3VN6hqodcafSW9rnP8tq31fUfu9P"  # Change to your actual token

def edit_with_nvim(temp_file_path):
os.system(f'nvim {temp_file_path}')
with open(temp_file_path, 'r') as file:
content = file.read().strip()
return content

def create_task_or_journal_entry(option):
temp_file_path = "/tmp/notion_temp.txt"
if option == '1':
    title = input("Enter the title for the task: ")
    with open(temp_file_path, 'w') as file:
        file.write("Describe your task here...\\n")

    task_content = edit_with_nvim(temp_file_path)
    create_notion_page(database_id_tasks, token, title, task_content, checkbox=False, status_name="Not started")

elif option == '2':
    title = f"Journal Entry {datetime.now().strftime('%Y-%m-%d')}"
    with open(temp_file_path, 'w') as file:
        file.write("Write your journal entry here...\\n")

    journal_content = edit_with_nvim(temp_file_path)
    create_journal_entry(database_id_journal, token, title, journal_content)
def main():
print("""
_____ _                       _     _     _   _       _

|_   *| |                     | |   | |   | | | |     | |
| | | |*_   ___  _   _  __ *| |*_ | |_  | |*| |*   *| |*_
| | | '_ \ / _ \| | | |/ *` | '* \| *| |  _  | | | | ' \
| | | | | | () | || | (| | | | | |  | | | | || | |) |
\/ || ||\/ \,_|\, || ||\| \| |/\,|./
**/ |
|***/
""")
options = input("""
What would you like to do?

1. Task for the day.
2. Create a Journal entry
3. List tasks for the day.
4. List Journal Entries.

""")

if options in ['1', '2']:
    create_task_or_journal_entry(options)
    
if name == "main":
main()
```


## Edit Tasks Scripts
```Python
#!/usr/bin/env python3

import os
import requests
from datetime import datetime

database_id_tasks = "f0560618bd4f491e97c3725ed02c1882"  # Change to your actual task database ID
database_id_journal = "27708705f2ea4270a13a9d4a973a0c6c"  # Change to your actual journal database ID
token = "secret_MncrJScqXqxF9UA3VN6hqodcafSW9rnP8tq31fUfu9P"  # Change to your actual token

# Function to edit content using nvim
def edit_with_nvim(temp_file_path):
    os.system(f'nvim {temp_file_path}')
    with open(temp_file_path, 'r') as file:
        content = file.read().strip()
    return content

# Function to create a new task
def create_notion_page(database_id, token, title, content, checkbox=False, status_name="Not started"):
    url = "https://api.notion.com/v1/pages"
    
    headers = {
        "Authorization": f"Bearer {token}",
        "Content-Type": "application/json",
        "Notion-Version": "2022-06-28"
    }
    
    new_page_data = {
        "parent": {
            "database_id": database_id
        },
        "properties": {
            "All Tasks": {
                "title": [
                    {
                        "text": {
                            "content": title
                        }
                    }
                ]
            },
            "Checkbox": {
                "checkbox": checkbox
            },
            "Status": {
                "status": {
                    "name": status_name
                }
            }
        },
        "children": [
            {
                "object": "block",
                "type": "paragraph",
                "paragraph": {
                    "rich_text": [
                        {
                            "type": "text",
                            "text": {
                                "content": content
                            }
                        }
                    ]
                }
            }
        ]
    }

    response = requests.post(url, headers=headers, json=new_page_data)
    
    if response.status_code in range(200, 300):
        print("Page created successfully.")
    else:
        print(f"Failed to create page: {response.status_code}")
        print(response.json())

# Function to create a new journal entry
def create_journal_entry(database_id, token, title, content):
    url = "https://api.notion.com/v1/pages"
    
    headers = {
        "Authorization": f"Bearer {token}",
        "Content-Type": "application/json",
        "Notion-Version": "2022-06-28"
    }
    
    new_page_data = {
        "parent": {
            "database_id": database_id
        },
        "properties": {
            "Journal Entries": {
                "title": [
                    {
                        "text": {
                            "content": title
                        }
                    }
                ]
            }
        },
        "children": [
            {
                "object": "block",
                "type": "paragraph",
                "paragraph": {
                    "rich_text": [
                        {
                            "type": "text",
                            "text": {
                                "content": content
                            }
                        }
                    ]
                }
            }
        ]
    }

    response = requests.post(url, headers=headers, json=new_page_data)
    
    if response.status_code in range(200, 300):
        print("Journal entry created successfully.")
    else:
        print(f"Failed to create journal entry: {response.status_code}")
        print(response.json())

# Function to list tasks
def list_notion_tasks(database_id, token):
    url = f"https://api.notion.com/v1/databases/{database_id}/query"
    headers = {
        "Authorization": f"Bearer {token}",
        "Content-Type": "application/json",
        "Notion-Version": "2022-06-28"
    }

    response = requests.post(url, headers=headers)

    if response.status_code in range(200, 300):
        results = response.json().get("results", [])
        tasks = []
        for task in results:
            task_id = task["id"]
            task_title = task["properties"]["All Tasks"]["title"][0]["text"]["content"] if task["properties"]["All Tasks"]["title"] else "Untitled"
            tasks.append((task_title, task_id))
        return tasks
    else:
        print(f"Failed to retrieve tasks: {response.status_code}")
        print(response.json())
        return []

# Function to retrieve the body content of a task
def get_notion_task_body(token, task_id):
    url = f"https://api.notion.com/v1/blocks/{task_id}/children"
    headers = {
        "Authorization": f"Bearer {token}",
        "Content-Type": "application/json",
        "Notion-Version": "2022-06-28"
    }

    response = requests.get(url, headers=headers)

    if response.status_code in range(200, 300):
        blocks = response.json().get("results", [])
        paragraphs = []
        for block in blocks:
            if block['type'] == 'paragraph':
                rich_text = block['paragraph'].get('rich_text', [])
                if rich_text and 'text' in rich_text[0]:
                    paragraphs.append(rich_text[0]['text']['content'])
        return "\n".join(paragraphs)
    else:
        print(f"Failed to retrieve task body: {response.status_code}")
        print(response.json())
        return ""

# Function to update a task's body content
def update_notion_task_body(token, task_id, updated_content):
    url = f"https://api.notion.com/v1/blocks/{task_id}/children"
    headers = {
        "Authorization": f"Bearer {token}",
        "Content-Type": "application/json",
        "Notion-Version": "2022-06-28"
    }

    update_data = {
        "children": [
            {
                "object": "block",
                "type": "paragraph",
                "paragraph": {
                    "rich_text": [
                        {
                            "type": "text",
                            "text": {
                                "content": updated_content
                            }
                        }
                    ]
                }
            }
        ]
    }

    response = requests.patch(url, headers=headers, json=update_data)

    if response.status_code in range(200, 300):
        print("Task body updated successfully.")
    else:
        print(f"Failed to update task body: {response.status_code}")
        print(response.json())

# Function to create or edit tasks and journal entries
def create_task_or_journal_entry(option):
    temp_file_path = "/tmp/notion_temp.txt"

    if option == '1':  # Create a new task
        title = input("Enter the title for the task: ")
        with open(temp_file_path, 'w') as file:
            file.write("Describe your task here...\n")

        task_content = edit_with_nvim(temp_file_path)
        create_notion_page(database_id_tasks, token, title, task_content, checkbox=False, status_name="Not started")

    elif option == '2':  # Create a new journal entry
        title = f"Journal Entry {datetime.now().strftime('%Y-%m-%d')}"
        with open(temp_file_path, 'w') as file:
            file.write("Write your journal entry here...\n")

        journal_content = edit_with_nvim(temp_file_path)
        create_journal_entry(database_id_journal, token, title, journal_content)

    elif option == '3':  # List and edit tasks
        tasks = list_notion_tasks(database_id_tasks, token)
        if tasks:
            print("Tasks:")
            for index, (task_title, task_id) in enumerate(tasks, start=1):
                print(f"{index}: {task_title} (ID: {task_id})")
            task_choice = int(input("\nEnter the number of the task you want to edit: ")) - 1
            task_title, task_id = tasks[task_choice]
            
            # Fetch the current body content of the task
            current_body = get_notion_task_body(token, task_id)
            with open(temp_file_path, 'w') as file:
                file.write(f"{current_body}\n")

            updated_body = edit_with_nvim(temp_file_path)
            update_notion_task_body(token, task_id, updated_body)
        else:
            print("No tasks found.")

def main():
    print("""
     _____ _                       _     _     _   _       _     
    |_   _| |                     | |   | |   | | | |     | |    
      | | | |__   ___  _   _  __ _| |__ | |_  | |_| |_   _| |__  
      | | | '_ \ / _ \| | | |/ _` | '_ \| __| |  _  | | | | '_ \ 
      | | | | | | (_) | |_| | (_| | | | | |_  | | | | |_| | |_) |
      \_/ |_| |_|\___/ \__,_|\__, |_| |_|\__| \_| |_/\__,_|_.__/ 
                              __/ |                             
                             |___/                              
    """)
    print("Options:\n1: Create a new task\n2: Create a new journal entry\n3: List and edit tasks")
    option = input("Choose an option: ")
    create_task_or_journal_entry(option)

if __name__ == "__main__":
    main()

```