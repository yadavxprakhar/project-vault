# Resources for Quiz App

## 📺 Video Tutorials
- [Build A Quiz App With JavaScript](https://www.youtube.com/watch?v=riDzcEQbX6k) - Web Dev Simplified: Complete vanilla JS tutorial with timer
- [How To Make Quiz App Using JavaScript](https://www.youtube.com/watch?v=PBcqGxrr9g8) - GreatStack: Progressive difficulty with category selection and scoring
- [Build a Flashcard Quiz App in ReactJS (2025)](https://www.youtube.com/watch?v=dv1IvTOVbnU) - Full React implementation with hooks for beginners
- [How to Make a Quiz App using HTML CSS Javascript](https://www.youtube.com/watch?v=f4fB9Xg2JEY) - Dev Ed: Categories, difficulty levels, high scores

## 📚 Written Tutorials
- [Create a Quiz Application Using JavaScript](https://www.geeksforgeeks.org/javascript/how-to-create-a-simple-javascript-quiz/) - GeeksforGeeks comprehensive guide with API integration
- [How to Make a Simple JavaScript Quiz](https://www.sitepoint.com/simple-javascript-quiz/) - SitePoint step-by-step tutorial (updated 2024)
- [How to Build a Quiz App Using React](https://www.freecodecamp.org/news/how-to-build-a-quiz-app-using-react/) - freeCodeCamp React detailed walkthrough
- [Build a Quiz App with Timer using HTML CSS and JavaScript](https://www.codingnepalweb.com/build-quiz-app-html-css-javascript/) - CodingNepal with timer implementation (updated 2026)

## 🔧 Tools & Libraries
- [Open Trivia Database API](https://opentdb.com/api_config.php) - Free quiz questions API (4000+ questions) - **HIGHLY RECOMMENDED**
- [QuizAPI](https://quizapi.io/) - Alternative quiz questions API with categories
- [canvas-confetti](https://github.com/catdad/canvas-confetti) - Performant confetti animation for quiz completion celebration
- [Animate.css](https://animate.style/) - CSS animations for question transitions
- [SweetAlert2](https://sweetalert2.github.io/) - Beautiful modals for results display
- [LocalStorage API](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) - Save high scores (built-in)

## 💻 GitHub Repositories
- [Build-A-Quiz-App-With-HTML-CSS-and-JavaScript](https://github.com/jamesqquick/Build-A-Quiz-App-With-HTML-CSS-and-JavaScript) - Full course repo by James Q Quick with Open Trivia API
- [JavaScript-Quiz-App](https://github.com/yashcrest/JavaScript-Quiz-App) - Vanilla JS quiz app leveraging Open Trivia API with category selection
- [QuizApp](https://github.com/constgenius/QuizApp) - Clean HTML/CSS/JS quiz app with live preview
- [react-quiz](https://github.com/weibenfalk/react-quiz) - React + TypeScript version with Vite setup
- [Quiz App Topics on GitHub](https://github.com/topics/quiz-app?l=javascript) - Collection of 600+ JavaScript quiz app repositories

## 📖 Learning Resources
- [JavaScript Timer Functions](https://www.freecodecamp.org/news/javascript-timers-everything-you-need-to-know/) - setInterval and setTimeout explained
- [Array Methods for Quiz Logic](https://www.freecodecamp.org/news/javascript-array-methods/) - Map, filter, reduce for questions
- [Event Handling in JavaScript](https://javascript.info/events) - Handling button clicks and selections
- [Working with JSON](https://www.freecodecamp.org/news/what-is-json-a-json-file-example/) - Structuring question data
- [Fisher-Yates Shuffle Algorithm](https://bost.ocks.org/mike/shuffle/) - Randomize question order

## 🌐 APIs & Services
- [Open Trivia Database API](https://opentdb.com/) - Free trivia questions (no API key needed)
- [Quiz API Documentation](https://opentdb.com/api_config.php) - Configuration and usage guide
- [The Trivia API](https://the-trivia-api.com/) - Modern REST API for trivia questions
- [jService (Jeopardy Questions)](http://jservice.io/) - Jeopardy-style questions API

## 🎨 Design Resources
- [Quiz App UI Designs](https://dribbble.com/search/quiz-app) - Dribbble inspiration
- [Question Card Layouts](https://codepen.io/search/pens?q=quiz+card) - CodePen examples
- [Quiz Result Screens](https://www.behance.net/search/projects?search=quiz%20app) - Behance designs
- [Color Schemes for Quizzes](https://coolors.co/palettes/trending/quiz) - Color palette ideas

## 📚 Sample Question Structure
```javascript
const questions = [
  {
    question: "What is the capital of France?",
    options: ["London", "Berlin", "Paris", "Madrid"],
    correctAnswer: 2, // index of correct answer
    category: "Geography",
    difficulty: "easy"
  },
  {
    question: "Which planet is known as the Red Planet?",
    options: ["Venus", "Mars", "Jupiter", "Saturn"],
    correctAnswer: 1,
    category: "Science",
    difficulty: "easy"
  }
];