# Custom Snippet for Highscores Display in Quiz App

To display player scores with ranks on score and time in your quiz app, use the following HTML snippet. Add this to your `highscores.html` template:

```json

  "HTML Template for Displaying Highscores": {
    "prefix": "displayHighscoresHtml",
    "body": [
      "{% extends 'layout.html' %}",
      "",
      "{% block content %}",
      "<table class=\"table table-striped\">",
      "    <thead>",
      "        <tr>",
      "            <th>Date Played</th>",
      "            <th>Username</th>",
      "            <th>Score</th>",
      "            <th>Time</th>",
      "        </tr>",
      "    </thead>",
      "    <tbody>",
      "        {% for highscore in highscores %}",
      "        <tr>",
      "            <td>{{ highscore.DatePlayed }}</td>",
      "            <td>{{ highscore.Username }}</td>",
      "            <td>{{ highscore.Score }}</td>",
      "            <td>{{ highscore.Time }} seconds</td>",
      "        </tr>",
      "        {% endfor %}",
      "    </tbody>",
      "</table>",
      "",
      "{% endblock %}"
    ],
    "description": "This snippet is used for the highscores.html template in the quiz app, displaying a table of player scores, including date played, username, score, and time."

}
