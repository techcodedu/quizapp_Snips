# Custom Snippet for the Results Route in Quiz App

To finalize and display the game results in your quiz app, implement the following `results` route in your Flask application's `routes.py` file:

```json
{
  "Flask Route for Game Results": {
    "prefix": "quizAppResultsRoute",
    "body": [
      "@app.route('/results')",
      "def results():",
      "    score = session.get('score', 0)",
      "    player_name = session.get('player_name', 'Player')",
      "    start_time_str = session.get('start_time')",
      "",
      "    # Convert start_time from string back to datetime",
      "    if start_time_str:",
      "        start_time = datetime.strptime(start_time_str, '%Y-%m-%d %H:%M:%S')",
      "    else:",
      "        start_time = datetime.utcnow()  # Fallback if start_time is not in session",
      "",
      "    # Use utcnow() for end_time to be consistent with start_time",
      "    end_time = datetime.utcnow()",
      "    duration_of_play = (end_time - start_time).total_seconds()",
      "",
      "    cursor = mysql.connection.cursor()",
      "",
      "    # Insert player data into the player table",
      "    insert_player_query = '''",
      "    INSERT INTO player (name, start_time, end_time, score, duration_of_play) ",
      "    VALUES (%s, %s, %s, %s, %s)",
      "    '''",
      "    cursor.execute(insert_player_query, (player_name, start_time, end_time, score, duration_of_play))",
      "",
      "    # Retrieve the last inserted player_id",
      "    player_id = cursor.lastrowid",
      "",
      "    # Insert score data into the highscore table",
      "    insert_score_query = '''",
      "    INSERT INTO highscore (player_id, score, time) ",
      "    VALUES (%s, %s, %s)",
      "    '''",
      "    cursor.execute(insert_score_query, (player_id, score, duration_of_play))",
      "",
      "    mysql.connection.commit()",
      "    cursor.close()",
      "",
      "    # Clear the session",
      "    session.clear()",
      "",
      "    return render_template('results.html', score=score, player_name=player_name)"
    ],
    "description": "This route calculates the final score and duration of play, stores player details and score in the database, clears the session, and displays the results page."
  }
}
