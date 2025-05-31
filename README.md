# Bubble Click Game 🎮

A fun and interactive HTML5 game where players click on bubbles to score points within a time limit. The game features multiple rounds, a progress bar with levels (Yellow, Orange, Red), and the ability to track the best or last score. Perfect for engaging users in marketing campaigns, educational activities, or gamified experiences.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Use Cases](#use-cases)
- [Installation](#installation)
- [Usage](#usage)
- [Integration with Forms](#integration-with-forms)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Overview
The Bubble Click Game is a lightweight, mobile-friendly game built with HTML, CSS, and JavaScript. Players click on filled bubbles to earn points within 20 seconds per round. The game tracks scores across multiple plays (up to 3 rounds by default) and assigns a level (Yellow, Orange, or Red) based on the player's performance. The final score (or best score, depending on the admin setting) is stored in a hidden input field, making it easy to integrate with form generators like Gravity Forms for capturing user results.

## Features
- **Interactive Gameplay**: Click on filled bubbles to score points within a 20-second time limit.
- **Progress Bar with Levels**: Visual progress bar with checkpoints at 33.33% (Yellow), 66.66% (Orange), and 100% (Red).
- **Multiple Rounds**: Supports up to 3 plays with an optional reset feature after the first round.
- **Score Tracking**: Stores scores from each play and can display either the best score or the last score (configurable via `USE_BEST_SCORE` flag).
- **Mobile-Friendly**: Optimized for mobile devices with touch support (`touch-action: manipulation`).
- **Form Integration**: Outputs the final level (Yellow, Orange, or Red) to a hidden input field for easy form submission.
- **Customizable**: Easily adjust game settings like duration, max plays, and bubble behavior by modifying constants in the script.

## Use Cases
- **Fun Sale Campaigns**: Engage customers during promotional events by integrating the game into your website. Offer discounts or rewards based on the player's level (e.g., Yellow = 10% off, Orange = 20% off, Red = 30% off).
- **Gamified Marketing**: Add an interactive element to your marketing campaigns to increase user engagement and collect user data via form submissions.
- **Educational Tools**: Use the game in educational settings to make learning fun, rewarding students based on their performance.
- **Event Entertainment**: Embed the game in event landing pages to entertain visitors and encourage participation.

## Installation
1. **Clone or Download**:
   - Clone this repository to your local machine:
     ```bash
     git clone https://github.com/mohsenr1/bubble-click-game.git
     ```
   - Alternatively, download the ZIP file and extract it.

2. **Host the Game**:
   - Upload the `index.html` file to your web server or hosting platform.
   - Alternatively, open `index.html` directly in a web browser for local testing (some features may require a server due to form submissions).

## Usage
1. **Play the Game**:
   - Open the `index.html` file in a web browser.
   - Click the "Start" button to begin the game.
   - Click on filled (white) bubbles to score points within 20 seconds.
   - After the round ends, a popup displays your score and level (Yellow, Orange, or Red).
   - You can reset to play again (up to 3 total plays) or submit your score via the "Go to Next Page" button.

2. **Game Mechanics**:
   - **Scoring**: Each filled bubble clicked adds 1 point to your score.
   - **Levels**:
     - Yellow: 0–33.33% of total clicks (0–21 points).
     - Orange: 33.33%–66.66% of total clicks (22–43 points).
     - Red: 66.66%–100% of total clicks (44–65 points).
   - **Rounds**: You can play up to 3 rounds. After the first round, you can reset to try again, but the reset option is disabled after the third play.
   - **Score Display**: The popup shows either the best score or the last score, depending on the `USE_BEST_SCORE` setting.

## Integration with Forms
The game is designed to integrate seamlessly with form generators like Gravity Forms, Ninja Forms, or any other form builder that supports HTML components and hidden fields.

### Steps to Integrate with Gravity Forms
1. **Add an HTML Field**:
   - In your Gravity Forms editor, add an HTML field to your form.
   - Copy the entire content of `index.html` (from `<!DOCTYPE html>` to `</html>`) and paste it into the HTML field.

2. **Capture the Final Score**:
   - The game outputs the final level (Yellow, Orange, or Red) to a hidden input field with the name `final-score`.
   - In Gravity Forms, add a hidden field to your form and set its "Field Key" or "Parameter Name" to `final-score`. This will capture the level when the form is submitted.

3. **Set the Form Action**:
   - In the `<form>` tag within the game's popup, update the `action` attribute to point to your desired URL (e.g., a thank-you page or the next step in your campaign):
     ```html
     <form action="https://yourwebsite.com/thank-you" method="GET">
     ```

4. **Submit the Form**:
   - After playing, the user can click "Go to Next Page" to submit the form, sending the `final-score` value (Yellow, Orange, or Red) to your server for processing.

### Example Use Case
- **Sale Campaign**: Offer discounts based on the user's level:
  - Yellow: 10% off
  - Orange: 20% off
  - Red: 30% off
- After the user submits the form, your server can process the `final-score` value and apply the appropriate discount or reward.

## Customization
You can customize the game by modifying the constants at the top of the `<script>` section in `index.html`:

- `TOTAL_CLICKS`: Total clicks needed to reach 100% (default: 65).
- `GAME_DURATION`: Duration of each round in seconds (default: 20).
- `MAX_PLAYS`: Maximum number of plays allowed (default: 3).
- `BUBBLE_INTERVAL`: Interval (ms) between bubble updates (default: 300).
- `BUBBLE_DURATION`: Duration (ms) a bubble stays filled (default: 800).
- `MAX_FILLED_BUBBLES`: Maximum number of filled bubbles at once (default: 2).
- `USE_BEST_SCORE`: Set to `true` to show the best score across plays, or `false` to show the last score (default: true).

### Example: Change Game Duration
To make each round 30 seconds long, update the `GAME_DURATION`:
```javascript
const GAME_DURATION = 30;

## Contributing
Contributions are welcome! If you have ideas for new features, bug fixes, or improvements, feel free to:
   - Fork the repository.
   - Create a new branch (`git checkout -b feature/your-feature`).
   - Make your changes and commit them (`git commit -m "Add your feature"`).
   - Push to your branch (`git push origin feature/your-feature`).
   - Open a Pull Request.

##License
This project is licensed under the MIT License. See the LICENSE file for details.

