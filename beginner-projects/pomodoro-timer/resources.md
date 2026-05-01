# Resources for Pomodoro Timer

## 📺 Video Tutorials
- [Build a Pomodoro Timer with JavaScript](https://www.youtube.com/watch?v=jWlsixNWKjM) - GreatStack: Clean vanilla JS implementation
- [Pomodoro Clock - freeCodeCamp Project](https://www.youtube.com/watch?v=vMZPRjK8M1A) - freeCodeCamp: Complete walkthrough
- [React Pomodoro Timer](https://www.youtube.com/watch?v=K3AMzW0kS-Q) - Coding Addict: React Hooks version
- [Advanced Pomodoro with Circular Progress](https://www.youtube.com/watch?v=PIiWSszGgZ0) - Online Tutorials: SVG progress ring

## 📚 Written Tutorials
- [How to Build a Pomodoro Timer App](https://www.freecodecamp.org/news/how-to-build-a-pomodoro-clock/) - freeCodeCamp detailed guide
- [Create a Pomodoro timer with HTML, CSS, and vanilla JavaScript](https://webdesign.tutsplus.com/create-a-pomodoro-timer-with-html-css-and-vanilla-javascript--cms-107050t) - Envato Tuts+ step-by-step
- [Build a Pomodoro Timer App using HTML, CSS, and JavaScript](https://dev.to/sahilmevada/create-a-pomodoro-timer-app-using-html-css-and-javascript-41f8) - Dev.to with modern implementation guide
- [Circular Progress Bar SVG](https://css-tricks.com/building-progress-ring-quickly/) - CSS-Tricks SVG tutorial

## 🔧 Tools & Libraries
- [Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) - Browser notifications (built-in)
- [Howler.js](https://howlerjs.com/) - Audio library for alarm sounds
- [Chart.js](https://www.chartjs.org/) - For productivity statistics charts
- [date-fns](https://date-fns.org/) - Time formatting and calculations
- [React Circular Progressbar](https://www.npmjs.com/package/react-circular-progressbar) - For React version
- [Animate.css](https://animate.style/) - Animations for session transitions

## 💻 GitHub Repositories
- [pomodoro-react-app](https://github.com/astroud/pomodoro-react-app) - React Pomodoro timer + Frontend Mentor's visual design
- [pomodoro-react](https://github.com/jakewies/pomodoro-react) - React tutorial code and implementation
- [pomodoro](https://github.com/DanOpcode/pomodoro) - Feature-rich example with Next.js, TypeScript and Foundation
- [Pomodoro Tracker](https://github.com/luizbatanero/pomodoro-react) - With task tracking and browser notifications
- [Minimal Pomodoro](https://github.com/chrisrhymes/pomodoro-react) - Clean, simple version built in React

## 📖 Learning Resources
- [JavaScript Timers: setTimeout and setInterval](https://www.freecodecamp.org/news/javascript-timers-everything-you-need-to-know/) - Essential timer concepts
- [Web Notifications API Guide](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API) - MDN notifications tutorial
- [SVG Circle Progress Bar](https://www.youtube.com/watch?v=C_JKlr4WKKs) - Creating circular progress indicators
- [Audio API Basics](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) - Playing notification sounds
- [The Pomodoro Technique Explained](https://francescocirillo.com/pages/pomodoro-technique) - Official methodology

## 🌐 APIs & Services
- [Web Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/notification) - Browser notifications (no API key needed)
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) - Sound playback (built-in)
- [Freesound.org](https://freesound.org/) - Free alarm/notification sounds
- [Mixkit Sound Effects](https://mixkit.co/free-sound-effects/alarm/) - Free sound effects for timers

## 🎨 Design Resources
- [Pomodoro Timer UI Designs](https://dribbble.com/search/pomodoro) - Dribbble inspiration
- [Circular Timer Animations](https://codepen.io/search/pens?q=circular+timer) - CodePen examples
- [Minimalist Timer Designs](https://www.behance.net/search/projects?search=pomodoro%20timer) - Behance galleries
- [Timer Sound Effects](https://mixkit.co/free-sound-effects/alarm/) - Free alarm sounds

## 📚 Mathematical Reference for Circular Progress
```javascript
// Calculate SVG circle progress
const radius = 90;
const circumference = 2 * Math.PI * radius;
const progress = (timeRemaining / totalTime) * circumference;
circle.style.strokeDashoffset = circumference - progress;