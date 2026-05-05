# Resources for URL Shortener

## 📺 Video Tutorials
- [Build a URL Shortener with Node.js & Express (2025)](https://www.youtube.com/watch?v=QRlS0izLvU0) - Complete Express.js tutorial with modern best practices
- [Build and Deploy a URL Shortener App with MERN Stack](https://www.youtube.com/watch?v=xqUh9IKvXM8) - Full-stack implementation with MongoDB, Express, React, and Node.js
- [Build a Modern URL Shortener with React & Node.js](https://www.youtube.com/watch?v=5QlE6o-iYcE) - React frontend with Express backend and analytics
- [QR Code Generation for URL Shortener](https://www.youtube.com/watch?v=G1IbRujko-A) - JavaScript QR code tutorial with custom styling

## 📚 Written Tutorials
- [Creating Your Own URL Shortener with Node.js (2025 Edition)](https://habtesoft.medium.com/creating-your-own-url-shortener-with-node-js-2025-edition-b82927307ac2) - Modern production-ready guide using nanoid and Express
- [Building a Scalable URL Shortener with Node.js](https://dev.to/joanroucoux/building-a-scalable-url-shortener-with-nodejs-part-12-232i) - Dev.to step-by-step with React frontend
- [Express.js REST API](https://expressjs.com/en/starter/hello-world.html) - Official Express tutorial (updated)
- [Building a Production-Ready URL Shortener with Node.js and SQLite](https://medium.com/@ebojacky/building-a-production-ready-url-shortener-with-node-js-and-sqlite-9e4aa38a9db9) - SQLite integration with security best practices

## 🔧 Tools & Libraries
- [Express.js](https://expressjs.com/) - Minimal web framework for Node.js - **RECOMMENDED**
- [NanoID](https://github.com/ai/nanoid) - Tiny, secure URL-friendly unique string generator
- [qrcode](https://github.com/soldair/node-qrcode) - Modern JavaScript QR code generator
- [Prisma](https://www.prisma.io/) - Modern ORM for database modeling (MongoDB, PostgreSQL, SQLite)
- [SQLite3](https://github.com/TryGhost/node-sqlite3) - SQLite database driver
- [Axios](https://axios-http.com/) - HTTP client for API calls
- [CORS](https://expressjs.com/en/resources/middleware/cors.html) - Enable CORS for API endpoints
- [Helmet](https://helmetjs.github.io/) - Security middleware for Express

## 💻 GitHub Repositories
- [URL Shortener Node.js](https://github.com/bradtraversy/url-shortener) - Vanilla Node.js implementation
- [URL-Shortener](https://github.com/BoddepallyVenkatesh06/URL-Shortener) - React + Node.js full-stack example
- [reduced.to](https://github.com/origranot/reduced.to) - Modern, feature-rich open source URL shortener
- [shlink](https://github.com/shlinkio/shlink) - Popular self-hosted URL shortener with analytics
- [zws](https://github.com/zws-im/zws) - URL shortener using invisible spaces (unique approach)

## 📖 Learning Resources
- [REST API Design Best Practices](https://restfulapi.net/) - REST fundamentals
- [HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) - Understanding 301, 404, etc.
- [Database Design for URL Shorteners](https://www.mongodb.com/blog/post/building-a-url-shortener-with-mongodb) - Schema design
- [Deploying Node.js Apps to Render](https://www.freecodecamp.org/news/how-to-deploy-a-node-js-app-to-render/) - Modern deployment guide
- [Environment Variables Best Practices](https://www.freecodecamp.org/news/environment-variables/) - Secure configuration

## 🌐 APIs & Services
- [Express.js Documentation](https://expressjs.com/en/4x/api.html) - Official docs
- [NanoID Documentation](https://github.com/ai/nanoid#readme) - URL-friendly ID generation
- [Rebrandly API](https://www.rebrandly.com/api) - Branded short links with analytics
- [Vercel](https://vercel.com/) - Free deployment for serverless functions and full-stack apps
- [Railway](https://railway.app/) - Modern alternative for deploying Node.js apps with databases

## 🎨 Design Resources
- [URL Shortener UI Designs](https://dribbble.com/search/url-shortener) - Dribbble inspiration
- [Form Design Best Practices](https://www.smashingmagazine.com/2018/08/best-practices-for-mobile-form-design/) - Input form styling
- [QR Code Styling](https://www.qrcode-monkey.com/) - Custom QR code design

## 📚 Sample Project Structure
```bash
url-shortener/
├── backend/
│   ├── src/
│   │   ├── config/db.js
│   │   ├── controllers/urlController.js
│   │   ├── models/Url.js
│   │   ├── routes/urlRoutes.js
│   │   └── middleware/
│   ├── .env
│   └── server.js
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
├── package.json
└── README.md


## 🔐 Security Considerations
- Always validate URLs before shortening
- Use HTTPS for all redirects
- Implement rate limiting to prevent abuse
- Sanitize user input to prevent XSS attacks
- Consider using a library like `validator.js` for URL validation

## 🚀 Quick Start Code Snippet
```javascript
// Express.js server example
const express = require('express');
const { nanoid } = require('nanoid');
const app = express();

// In-memory storage (for demo)
const urlMap = new Map();

app.post('/shorten', express.json(), (req, res) => {
  const { longUrl } = req.body;
  const shortId = nanoid(6);
  urlMap.set(shortId, longUrl);
  res.json({ shortUrl: `https://short.url/${shortId}` });
});

app.get('/:shortId', (req, res) => {
  const { shortId } = req.params;
  const longUrl = urlMap.get(shortId);
  if (longUrl) {
    res.redirect(longUrl);
  } else {
    res.status(404).send('URL not found');
  }
});

app.listen(3000, () => console.log('Server running on port 3000'));

## 📚 Database Schema Example
```javascript
// MongoDB URL document structure
{
  originalUrl: "https://example.com/very/long/url/that/needs/shortening",
  shortCode: "abc123",
  shortUrl: "https://yourdomain.com/abc123",
  clicks: 42,
  createdAt: "2024-01-15T10:30:00Z",
  expiresAt: null, // optional expiration
  analytics: {
    lastClickedAt: "2024-01-16T14:22:00Z",
    devices: { desktop: 25, mobile: 15, tablet: 2 },
    countries: { US: 20, UK: 10, IN: 12 }
  }
}