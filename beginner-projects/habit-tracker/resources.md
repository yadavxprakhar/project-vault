# Resources for Habit Tracker

## 📺 Video Tutorials
- [Build a Habit Tracker with HTML, CSS & JavaScript (2026)](https://www.youtube.com/watch?v=oeQ0btgW_7c) - Coding in Public: Complete vanilla JS tutorial with streaks and localStorage
- [Building a Full Habit Tracker App from Scratch (Dev Diaries)](https://www.youtube.com/watch?v=v5A71bur0pg) - Feature-rich implementation with calendar and progress tracking
- [Full Stack Habit Tracker App with React, Next.js & Tailwind (2026)](https://www.youtube.com/watch?v=15-ac463Wr4) - Complete React version with TypeScript and modern state management
- [Habit Tracker with Charts using Chart.js & JavaScript](https://www.youtube.com/watch?v=F0nPz0m9Zqg) - Traversy Media style: Data visualization and streak analytics

## 📚 Written Tutorials
- [How to Build a Habit Tracker App with JavaScript](https://www.freecodecamp.org/news/how-to-build-a-habit-tracker-app/) - freeCodeCamp comprehensive guide (updated 2025)
- [Build a Habit Tracker with Vanilla JavaScript and LocalStorage](https://freshman.tech/habit-tracker/) - Freshman Tech step-by-step (refreshed edition)
- [Modern Habit Tracker using JavaScript, Tailwind and LocalStorage](https://dev.to/code_mystery/habit-tracker-using-javascript-and-localstorage-4h1m) - Dev.to tutorial with calendar heatmap
- [Chart.js for Habit Tracking and Streaks](https://www.chartjs.org/docs/latest/) - Official Chart.js documentation with examples

## 🔧 Tools & Libraries
- [Chart.js](https://www.chartjs.org/) - Simple charting library for progress visualization - **RECOMMENDED**
- [ApexCharts](https://apexcharts.com/) - Modern charts with advanced features
- [date-fns](https://date-fns.org/) - Date manipulation and formatting
- [SweetAlert2](https://sweetalert2.github.io/) - Beautiful modals for habit completion
- [Flatpickr](https://flatpickr.js.org/) - Calendar picker for date selection
- [Animate.css](https://animate.style/) - Animations for streak updates
- [LocalStorage API](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) - Data persistence (built-in)

## 💻 GitHub Repositories
- [Habit Tracker JavaScript](https://github.com/florinpop17/habit-tracker) - Vanilla JS implementation
- [React Habit Tracker](https://github.com/WebDevSimplified/Habit-Tracker) - React version with hooks
- [Advanced Habit Tracker](https://github.com/coleam00/habit-tracker) - Feature-rich example with FastAPI + React
- [Habo Habit Tracker](https://github.com/xpavle00/Habo) - Flutter-based open source habit tracker (for inspiration)
- [Habit Tracker Templates](https://github.com/topics/habit-tracker) - Collection of implementations

## 📖 Learning Resources
- [JavaScript Date Objects](https://www.freecodecamp.org/news/javascript-date-object/) - Working with dates
- [LocalStorage Complete Guide](https://blog.logrocket.com/localstorage-javascript-complete-guide/) - Data persistence patterns
- [Streak Algorithm Explained](https://stackoverflow.com/questions/55150046/algorithm-to-calculate-streaks) - Stack Overflow discussion
- [Chart.js Getting Started](https://www.chartjs.org/docs/latest/getting-started/) - Creating your first chart
- [Array Methods for Habits](https://www.freecodecamp.org/news/javascript-array-methods/) - Filter, map, reduce for habit data

## 🌐 APIs & Services
- [Web Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) - Browser notifications
- [date-fns Documentation](https://date-fns.org/docs) - Date manipulation (v3 updated docs)
- [CSV Export Guide](https://www.geeksforgeeks.org/how-to-export-html-table-to-csv-using-javascript/) - Exporting data

## 🎨 Design Resources
- [Habit Tracker UI Designs](https://dribbble.com/search/habit+tracker) - Dribbble inspiration
- [Calendar UI Components](https://codepen.io/search/pens?q=habit+calendar) - CodePen examples
- [Habit Tracking App Design](https://www.behance.net/search/projects?search=habit%20tracker) - Behance galleries
- [Color Schemes for Habits](https://coolors.co/palettes/trending/habit) - Color palette ideas

## 📚 Sample Data Structure
```javascript
const habits = [
  {
    id: 1,
    name: "Drink water",
    description: "Drink 8 glasses of water daily",
    category: "health",
    completed: [  // Array of dates (YYYY-MM-DD format)
      "2026-01-01",
      "2026-01-02",
      "2026-01-03"
    ],
    color: "#36A2EB",
    target: "daily",
    streak: 3,
    longestStreak: 5
  },
  {
    id: 2,
    name: "Read 30 minutes",
    description: "Read non-fiction for 30 minutes",
    category: "learning",
    completed: ["2026-01-01", "2026-01-03"],
    color: "#FF6384",
    target: "daily",
    streak: 1,
    longestStreak: 1
  }
];