# Custom Snippet for templates/layout.html in Quiz App

To add this HTML layout template as a custom snippet for the `layout.html` page in your code editor, please follow the steps below:

1. Open your code editor's preferences or settings.
2. Go to the User Snippets section.
3. Choose or create a JSON file for HTML snippets.
4. Add the following JSON code to your snippets file:

```json
  "HTML Layout Template for Quiz App": {
    "prefix": "quizAppLayoutHtml",
    "body": [
      "<!DOCTYPE html>",
      "<html lang=\"en\">",
      "<head>",
      "    <meta charset=\"UTF-8\">",
      "    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">",
      "    <title>{% block title %}Quiz Game{% endblock %}</title>",
      "    <!-- Bootstrap CSS -->",
      "    <link rel=\"stylesheet\" href=\"{{ url_for('static', filename='css/bootstrap.min.css') }}\">",
      "    <!-- Custom CSS -->",
      "    <link rel=\"stylesheet\" href=\"{{ url_for('static', filename='css/style.css') }}\">",
      "</head>",
      "<body>",
      "    <nav class=\"navbar navbar-expand-lg navbar-light bg-light\">",
      "        <div class=\"container\">",
      "            <a class=\"navbar-brand\" href=\"/\">Quiz Game</a>",
      "              <div class=\"collapse navbar-collapse\" id=\"navbarNav\">",
      "                <a href=\"/highscores\" class=\"nav-link\">Scores</a>",
      "            </div>",
      "        </div>",
      "    </nav>",
      "",
      "    <div class=\"container\">",
      "        {% block content %}",
      "        <!-- Content will be injected here -->",
      "        {% endblock %}",
      "    </div>",
      "    <!-- Custom JS -->",
      "    <script src=\"{{ url_for('static', filename='js/bootstrap.bundle.min.js') }}\"></script>",
      "</body>",
      "</html>"
    ],
    "description": "Use this snippet to insert the layout.html content for the quiz app, which includes the standard HTML structure, Bootstrap, and custom styles."
}
