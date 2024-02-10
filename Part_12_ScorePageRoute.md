# Custom Snippet for Highscores Route in Quiz App

Implement the following Flask route in your `routes.py` file to fetch and display player scores and rankings on the `highscores.html` template:

```json
{
  "Flask Route for Displaying Highscores": {
    "prefix": "quizAppHighscoresRoute",
    "body": [
      "@app.route('/highscores')",
      "def highscores():",
      "    cursor = mysql.connection.cursor()",
      "    ",
      "    # Execute the query to retrieve highscores",
      "    cursor.execute('''",
      "        SELECT p.name AS Username, h.score AS Score, h.time AS Time, p.start_time",
      "        FROM highscore h",
      "        JOIN player p ON h.player_id = p.id",
      "        ORDER BY h.score DESC, h.time ASC, p.start_time ASC",
      "    ''')",
      "    ",
      "    highscores = cursor.fetchall()",
      "    cursor.close()",
      "    ",
      "    # Format the date in Python",
      "    for highscore in highscores:",
      "        highscore['DatePlayed'] = highscore['start_time'].strftime('%m/%d/%Y')",
      "    ",
      "    return render_template('highscores.html', highscores=highscores)"
    ],
    "description": "This route fetches and formats highscores from the database, then displays them on the highscores.html page, ordered by score and time."
  }
}
