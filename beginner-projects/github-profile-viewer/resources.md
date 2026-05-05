# Resources for GitHub Profile Viewer

## 📺 Video Tutorials
- [GitHub Profile Viewer App with HTML, CSS & JavaScript](https://www.youtube.com/watch?v=KvWg9WEp9vo) - Codynn: Complete vanilla JS tutorial with Fetch API
- [Build GitHub Profile Search App Using React JS & GitHub API](https://www.youtube.com/watch?v=XI4GpNQQ7b4) - React implementation with modern hooks
- [Advanced GitHub Profile & Repository Explorer — React.js + Tailwind CSS](https://www.youtube.com/watch?v=RM9LXkrY7Bk) - Traversy Media style: Advanced React features and repo listing
- [Working with GitHub API using Axios and React (2026)](https://www.youtube.com/watch?v=8WN_u_GQCB0) - JavaScript Mastery style: Modern approach with error handling and debouncing

## 📚 Written Tutorials
- [Building a Simple Styled GitHub Profile Viewer with React & Tailwind CSS v4](https://medium.com/@frontendqueens/building-a-simple-styled-github-profile-viewer-with-react-tailwind-css-v4-e89d98e52d40) - Medium comprehensive guide (updated 2026)
- [GitHub REST API Documentation](https://docs.github.com/en/rest) - Official GitHub REST API documentation (v2026-03-10)
- [Working with the GitHub API in JavaScript](https://blog.logrocket.com/working-with-github-api/) - LogRocket tutorial with Octokit examples
- [GitHub GraphQL API Guide](https://docs.github.com/en/graphql) - GraphQL alternative with updated explorer

## 🔧 Tools & Libraries
- [GitHub REST API](https://docs.github.com/en/rest) - Official API (no key needed for public data) - **RECOMMENDED**
- [GitHub GraphQL API](https://docs.github.com/en/graphql) - More data, requires personal access token
- [Octokit.js](https://github.com/octokit/octokit.js) - Official JavaScript client for GitHub API (preferred over raw fetch)
- [Chart.js](https://www.chartjs.org/) - For contribution graphs and statistics
- [date-fns](https://date-fns.org/) - Date formatting and calculations
- [React Icons](https://react-icons.github.io/react-icons/) - GitHub Octicons and other icons
- [React Router](https://reactrouter.com/) - For repository detail pages (React version)

## 💻 GitHub Repositories
- [GitHub Profile Viewer React](https://github.com/erikprogramador/react-github-profiles) - React implementation with repository listing
- [Vanilla GitHub Profile Viewer](https://github.com/bradtraversy/github-profile-viewer) - Vanilla JS example (updated fork)
- [Advanced GitHub Explorer](https://github.com/WebDevSimplified/GitHub-Profile-Viewer) - Feature-rich version with Tailwind
- [GitHub Stats Cards](https://github.com/anuraghazra/github-readme-stats) - GitHub stats cards (for inspiration and API patterns)
- [GitHub API Examples](https://github.com/topics/github-api) - Collection of implementations

## 📖 Learning Resources
- [GitHub REST API Overview](https://docs.github.com/en/rest/overview) - API basics (2026 version)
- [Working with GitHub API](https://docs.github.com/en/rest) - Official guide with rate limiting updates
- [JavaScript Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) - MDN fetch tutorial
- [Debouncing Search Inputs](https://www.freecodecamp.org/news/javascript-debounce-example/) - Prevent API spam
- [Rate Limiting Guide](https://docs.github.com/en/rest/overview/resources-in-the-rest-api#rate-limiting) - GitHub rate limits (updated 2026)

## 🌐 APIs & Services
- [GitHub REST API](https://docs.github.com/en/rest) - Official API documentation (v2026-03-10)
- [GitHub GraphQL Explorer](https://docs.github.com/en/graphql/overview/explorer) - Test GraphQL queries
- [GitHub Personal Access Tokens](https://github.com/settings/tokens) - Generate tokens for authenticated requests
- [GitHub Badges](https://shields.io/category/social) - Status badges for profiles

## 🎨 Design Resources
- [GitHub Profile UI Designs](https://dribbble.com/search/github+profile) - Dribbble inspiration
- [GitHub Dark Theme](https://github.com/settings/appearance) - Official dark theme colors
- [GitHub Octicons](https://primer.style/octicons/) - Official GitHub icons
- [Profile Card Designs](https://codepen.io/search/pens?q=github+profile) - CodePen examples

## 📚 Sample API Response Structure
```json
// User profile response
{
  "login": "octocat",
  "id": 583231,
  "avatar_url": "https://avatars.githubusercontent.com/u/583231?v=4",
  "name": "The Octocat",
  "bio": "Nothing to see here",
  "public_repos": 8,
  "followers": 3938,
  "following": 9,
  "created_at": "2011-01-25T18:44:36Z",
  "updated_at": "2026-01-15T10:30:00Z"
}

// Repository response
{
  "name": "Hello-World",
  "full_name": "octocat/Hello-World",
  "private": false,
  "html_url": "https://github.com/octocat/Hello-World",
  "description": "My first repository on GitHub!",
  "language": "JavaScript",
  "stargazers_count": 183,
  "forks_count": 30,
  "open_issues_count": 5,
  "pushed_at": "2025-12-10T14:23:01Z"
}