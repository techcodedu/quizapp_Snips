# Custom Snippet for templates/game.html in Quiz App

To add this HTML game template as a custom snippet for the `game.html` page in your code editor, follow these steps:

1. Open your code editor's preferences or settings.
2. Go to the User Snippets section.
3. Choose or create a JSON file for HTML snippets.
4. Insert the following JSON code into your snippets file:

```json
{
  "HTML Game Template for Quiz App": {
    "prefix": "quizAppGameHtml",
    "body": [
      "{% extends 'layout.html' %}",
      "",
      "{% block content %}",
      "<div class=\"container mt-5\">",
      "    <div class=\"row\">",
      "        <div class=\"col-12 mb-3\">",
      "            <h2>Score: {{ session['score'] }}</h2>",
      "        </div>",
      "        <div class=\"col-12 mb-3\">",
      "            <img src=\"{{ url_for('static', filename=question['image_url']) }}\" alt=\"Random Image\" class=\"img-fluid\">",
      "        </div>",
      "        <div class=\"col-12\">",
      "            <form action=\"{{ url_for('answer') }}\" method=\"post\" class=\"d-grid gap-2\">",
      "                <div class=\"choices\">",
      "                    {% for choice in question['choices'] %}",
      "                        <button type=\"submit\" name=\"choice\" value=\"{{ choice.id }}\" class=\"btn btn-primary\">{{ choice.name }}</button>",
      "                    {% endfor %}",
      "                </div>",
      "            </form>",
      "        </div>",
      "    </div>",
      "</div>",
      "{% endblock %}"
    ],
    "description": "Use this snippet to insert the game.html content for the quiz app, which is used to display the game's questions and choices to the player."
  }
}
