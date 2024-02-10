# SQL Schema Snippet for Quiz App

To add this SQL schema as a custom snippet in your code editor, please follow these steps:

1. Open your code editor's preferences or settings.
2. Navigate to the User Snippets section.
3. Choose or create a JSON file for SQL snippets.
4. Insert the following JSON code into your snippets file:

```json
{
  "SQL Schema for Quiz App": {
    "prefix": "quizAppSchema",
    "body": [
      "-- Table structure for `fruits`",
      "CREATE TABLE `fruits` (",
      "  `id` int(11) NOT NULL,",
      "  `name` varchar(255) DEFAULT NULL,",
      "  `image_url` varchar(255) DEFAULT NULL",
      ") ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;",
      "",
      "-- Inserting data into `fruits`",
      "INSERT INTO `fruits` (`id`, `name`, `image_url`) VALUES",
      "(1, 'Apple', 'images/apple.jpg'),",
      "(2, 'Banana', 'images/banana.jpg'),",
      "(3, 'Cherry', 'images/cherry.png'),",
      "(4, 'Atis', 'images/atis.jpg'),",
      "(5, 'Elderberry', 'images/elderberry.jpg'),",
      "(6, 'Orange', 'images/orange.jpg'),",
      "(7, 'Grape', 'images/grape.jpg'),",
      "(8, 'Honeydew', 'images/honeydew.jpg');",
      "",
      "-- Table structure for `highscore`",
      "CREATE TABLE `highscore` (",
      "  `id` int(11) NOT NULL,",
      "  `player_id` int(11) DEFAULT NULL,",
      "  `score` int(11) DEFAULT NULL,",
      "  `time` int(11) DEFAULT NULL",
      ") ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;",
      "",
      "-- Table structure for `player`",
      "CREATE TABLE `player` (",
      "  `id` int(11) NOT NULL,",
      "  `name` varchar(255) DEFAULT NULL,",
      "  `start_time` datetime DEFAULT NULL,",
      "  `end_time` datetime DEFAULT NULL,",
      "  `score` int(11) DEFAULT NULL,",
      "  `duration_of_play` int(11) DEFAULT NULL",
      ") ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;",
      "",
      "-- Table structure for `question`",
      "CREATE TABLE `question` (",
      "  `id` int(11) NOT NULL,",
      "  `fruit_id` int(11) DEFAULT NULL,",
      "  `choice_1_id` int(11) DEFAULT NULL,",
      "  `choice_2_id` int(11) DEFAULT NULL,",
      "  `choice_3_id` int(11) DEFAULT NULL,",
      "  `choice_4_id` int(11) DEFAULT NULL,",
      "  `correct_choice_id` int(11) DEFAULT NULL",
      ") ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;",
      "",
      "-- Inserting data into `question`",
      "INSERT INTO `question` (`id`, `fruit_id`, `choice_1_id`, `choice_2_id`, `choice_3_id`, `choice_4_id`, `correct_choice_id`) VALUES",
      "(1, 1, 1, 2, 3, 4, 1),",
      "(2, 2, 1, 2, 3, 5, 2),",
      "(3, 3, 2, 3, 4, 6, 3),",
      "(4, 4, 3, 4, 5, 7, 4),",
      "(5, 5, 4, 5, 6, 8, 5),",
      "(6, 6, 5, 6, 7, 1, 6),",
      "(7, 7, 6, 7, 8, 2, 7),",
      "(8, 8, 7, 8, 1, 3, 8),",
      "(9, 1, 8, 1, 2, 4, 1),",
      "(10, 2, 1, 3, 5, 2, 2);"
    ],
    "description": "This snippet inserts the SQL schema for the quiz app, including tables for `fruits`, `highscore`, `player`, and `question`, with specific data for the `fruits` and `question` tables."
  }
}
