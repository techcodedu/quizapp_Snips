# Custom Snippet for the get_next_question Function in Quiz App

To retrieve the next question in the game flow of the quiz app, you will need to implement the `get_next_question` function. Add the following code snippet to your `routes.py` file:

```json
  "Function to Get Next Question": {
    "prefix": "getQuizNextQuestion",
    "body": [
      "def get_next_question():",
      "    cursor = mysql.connection.cursor()",
      "    # Make sure to handle the case where no questions have been asked yet",
      "    if not session.get('question_ids_asked'):",
      "        cursor.execute(\"SELECT * FROM question ORDER BY RAND() LIMIT 1\")",
      "    else:",
      "        placeholders = ', '.join(['%s'] * len(session['question_ids_asked']))",
      "        cursor.execute(f\"SELECT * FROM question WHERE id NOT IN ({placeholders}) ORDER BY RAND() LIMIT 1\",",
      "                    session['question_ids_asked'])",
      "    ",
      "    question_row = cursor.fetchone()",
      "    if question_row:",
      "        # Fetch the fruit names for the choice IDs",
      "        cursor.execute(\"SELECT id, name FROM fruits WHERE id IN (%s, %s, %s, %s)\",",
      "                       (question_row['choice_1_id'],",
      "                        question_row['choice_2_id'],",
      "                        question_row['choice_3_id'],",
      "                        question_row['choice_4_id']))",
      "        choices = cursor.fetchall()",
      "",
      "        # Fetch the correct fruit's image URL",
      "        cursor.execute(\"SELECT image_url FROM fruits WHERE id = %s\", (question_row['correct_choice_id'],))",
      "        correct_fruit_image = cursor.fetchone()",
      "",
      "        question = {",
      "            'text': 'Which one is this fruit?',",
      "            'image_url': correct_fruit_image['image_url'],",
      "            'choices': choices,",
      "            'correct_choice_id': question_row['correct_choice_id']",
      "        }",
      "",
      "        return question",
      "",
      "    cursor.close()",
      "    return None"
    ],
    "description": "This function fetches the next question from the database for the quiz game, ensuring questions are not repeated."

}
