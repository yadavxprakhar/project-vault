# GitHub Profile Viewer

## 📌 Overview
A web application that allows users to search for any GitHub username and view their profile information, repositories, contribution statistics, and activity in a clean, organized dashboard. Similar to a simplified GitHub profile page, this app fetches data from the GitHub REST API and displays it in an attractive card-based layout.

## ✨ Features
- Search any GitHub username with input field
- Display user avatar, bio, and basic profile info
- Show repository count, followers, and following stats
- List public repositories with name, description, and stars
- Filter repositories by language or stars
- Display contribution graph and activity statistics
- Show most used programming languages
- View individual repository details (issues, forks, watchers)
- Click repository to open GitHub link in new tab
- Display recent activity/events feed
- Error handling for invalid usernames
- Loading skeletons while fetching data
- Responsive grid layout for mobile and desktop
- Dark mode toggle with persistence

## 🛠️ Tech Stack
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla or React)
- **API**: GitHub REST API (no API key required for basic usage)
- **GraphQL**: GitHub GraphQL API (for advanced queries)
- **Styling**: CSS Grid/Flexbox or Tailwind CSS
- **Charts**: Chart.js for language statistics visualization
- **HTTP Client**: Fetch API, Axios, or Octokit (GitHub's official client)
- **Storage**: LocalStorage for search history and theme preference
- **Icons**: Font Awesome or GitHub's Octicons

## 📊 Difficulty Level
**Beginner** - Excellent second API project after Weather Dashboard. Introduces more complex API responses, data filtering, multiple endpoint calls, and user-centric UI design.

## 🎯 Expected Outcomes
After completing this project, you will:
- Master working with REST APIs and complex JSON responses
- Make multiple API calls and aggregate data
- Handle API rate limits (60 requests/hour unauthenticated)
- Implement search with real-time or submit-based patterns
- Display data in organized card layouts and tables
- Work with third-party client libraries (Octokit)
- Handle loading, empty, and error states gracefully
- Parse dates and format relative time ("2 hours ago")
- Implement data caching to reduce API calls
- Build search history functionality

## 🔥 Optional Enhancements
- Compare two GitHub profiles side-by-side
- Follower/following list with search
- Organization profiles support
- Repository star history charts (stargazers over time)
- Code preview for repository files
- Download profile as PDF report
- Save favorite profiles for quick access
- Dark/light/system theme toggle
- Commit activity calendar heatmap
- Language color-coded statistics donut chart
- Repository README preview
- Issues and pull requests viewer
- GitHub Actions workflow status display
- Contribution timeline visualization
- Share profile card on social media
- Export profile data as JSON
- Keyboard shortcuts (Enter to search, Esc to clear)

## 📸 Example/Demo
![GitHub Profile Viewer Preview](https://via.placeholder.com/800x400?text=GitHub+Profile+Viewer+Preview)