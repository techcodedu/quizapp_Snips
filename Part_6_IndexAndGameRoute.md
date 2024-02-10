# Flask Routes for Index and Game HTML in Quiz App

To set up the `index.html` and `game.html` templates to work with Flask, use the custom snippet below in your routes.py. This snippet should be placed in your code editor's user snippets file for Python:

```json
{
  "Flask Routes for Index and Game HTML": {
    "prefix": "quizAppRoutes",
    "body": [
      "from flask import render_template, request, redirect, url_for, session",
      "from quizapp import app, mysql",
      "from datetime import datetime",
      "import random",
      "",
      "@app.route('/')",
      "def index():",
      "    return render_template('index.html')",
      "",
      "@app.route('/start_game', methods=['POST'])",
      "def start_game():",
      "    player_name = request.form['player_name']",
      "    session.clear()",
      "    session['player_name'] = player_name",
      "    session['score'] = 0",
      "    session['question_ids_asked'] = []",
      "    session['question_number'] = 1",
      "    session['start_time'] = datetime.utcnow().strftime('%Y-%m-%d %H:%M:%S')",
      "    return redirect(url_for('game'))",
      "",
      "@app.route('/game')",
      "def game():",
      "    if 'question_ids_asked' not in session or len(session['question_ids_asked']) >= 10:",
      "        return redirect(url_for('results'))",
      "",
      "    question = get_next_question()",
      "    if question is None:",
      "        return redirect(url_for('results'))",
      "",
      "    session['correct_choice'] = question['correct_choice_id']",
      "    return render_template('game.html', question=question)"
    ],
    "description": "Flask routes for initializing the index and game functionality in the Quiz App."
  }
}
