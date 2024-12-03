# Tasks
I want to create 10 folders to store activity worksheets in each folder for Lessons 1 to 10.

Folder name is:
- Example: Lesson 02 Game Planning
- Start with "Lesson ", pluse lesson number 01 to 10, plus the lesson name


Lessons:

- https://www.stemgames.org.au/secondary-teacher-resources#lessons

# Steps:

1. Use ChatGPT to clean up the text from the lesson web page and find a list of lessons using the prompt:

Extract the lesson name for me. Like this: 2. Game Planning  Planning
Then, Convert it to: Lesson 02 Game Planning

2. Collect the list:

```
Lesson 01 Introduction  
Lesson 02 Game Planning  
Lesson 03 Game Overview  
Lesson 04 Gameplay and Mechanics  
Lesson 05 Visual Design  
Lesson 06 Audio Design  
Lesson 07 Prototyping  
Lesson 08 Alpha Testing  
Lesson 09 Beta Testing  
Lesson 10 Modifying and Finalising  
```

3. Use Python's pathlib

```Python
# FolderMaker.py
from pathlib import Path

lessons = [
    'Lesson 01 Introduction',
    'Lesson 02 Game Planning',
    'Lesson 03 Game Overview',
    'Lesson 04 Gameplay and Mechanics',
    'Lesson 05 Visual Design',
    'Lesson 06 Audio Design',
    'Lesson 07 Prototyping',
    'Lesson 08 Alpha Testing',
    'Lesson 09 Beta Testing',
    'Lesson 10 Modifying and Finalising',
]
# Base path for the lesson folders
base_path = Path(".")  # This is where you create the folders
base_path.mkdir(parents=True, exist_ok=True)

# Create folders for each lesson using Pathlib
for lesson in lessons:
    lesson_folder = base_path / lesson
    lesson_folder.mkdir(exist_ok=True)

# Confirm creation
[folder.name for folder in base_path.iterdir() if folder.is_dir()]
```


