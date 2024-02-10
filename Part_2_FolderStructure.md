# Folder Structure Snippet for Quiz App

If you need to recall the folder structure of the quiz app, you can use the following custom snippet. Here's how to add it to your code editor:

1. Open your code editor's preferences or settings.
2. Navigate to the User Snippets section.
3. Choose or create a JSON file for your workspace snippets.
4. Insert the following JSON code into your snippets file:

```json
{
  "Folder Structure for Quiz App": {
    "prefix": "quizAppFolders",
    "body": [
      "quizapp/",
      "├── static/",
      "│   ├── css/",
      "│   ├── images/",
      "│   └── js/",
      "├── templates/",
      "│   ├── game.html",
      "│   ├── highscores.html",
      "│   ├── index.html",
      "│   ├── layout.html",
      "│   └── results.html",
      "├── __init__.py",
      "├── routes.py",
      "├── qenv/",
      "├── README.md",
      "├── requirements.txt",
      "└── run.py"
    ],
    "description": "Use this snippet to insert the folder structure of the quiz app into your documentation or to recall the project structure."
  }
}
