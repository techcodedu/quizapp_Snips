# Custom Snippet for templates/index.html in Quiz App

To add this HTML template as a custom snippet for the `index.html` page in your code editor, follow these instructions:

1. Open your code editor's preferences or settings.
2. Navigate to the User Snippets section.
3. Choose or create a JSON file for HTML snippets.
4. Insert the following JSON code into your snippets file:

```json
{
  "HTML Template for Quiz App Index Page": {
    "prefix": "quizAppIndexHtml",
    "body": [
      "{% extends 'layout.html' %}",
      "{% block title %}Welcome to the Quiz Game!{% endblock %}",
      "{% block content %}",
      "<div class=\"vh-100 d-flex justify-content-center align-items-center\">",
      "  <div class=\"text-center\">",
      "    <h1 class=\"display-4 mb-4\">Welcome to the Quiz Game!</h1>",
      "    <form action=\"/start_game\" method=\"post\">",
      "      <div class=\"form-group\">",
      "        <input",
      "          type=\"text\"",
      "          class=\"form-control\"",
      "          name=\"player_name\"",
      "          placeholder=\"Enter your name\"",
      "          required",
      "          autofocus",
      "        />",
      "      </div>",
      "      <button type=\"submit\" class=\"btn btn-lg btn-primary mt-3\">",
      "        Start Game",
      "      </button>",
      "    </form>",
      "  </div>",
      "</div>",
      "{% endblock %}"
    ],
    "description": "Use this snippet to insert the index.html content for the quiz app where players enter their name to start the game."
  }
}
