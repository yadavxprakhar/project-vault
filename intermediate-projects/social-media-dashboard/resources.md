# Resources for Social Media Dashboard

## 📺 Video Tutorials
- [Build a Social Media Dashboard with React & Recharts](https://www.youtube.com/watch?v=5QlE6o-iYcE) - JavaScript Mastery: Complete React dashboard (updated 2025)
- [X (Twitter) API v2 Integration with React & Node.js](https://www.youtube.com/watch?v=xvFZjo5PgG0) - Traversy Media: X API v2 tutorial
- [OAuth 2.0 Explained with Real-World Examples](https://www.youtube.com/watch?v=996OiexHze0) - OAuth authentication flow
- [Data Visualization with Recharts & Chart.js in React](https://www.youtube.com/watch?v=Cd0gUgvWez8) - Chart implementation tutorial (2026 update)

## 📚 Written Tutorials
- [Building a Social Media Dashboard with React & TanStack Query](https://www.freecodecamp.org/news/how-to-build-a-social-media-dashboard/) - freeCodeCamp guide (updated 2026)
- [X API v2 Tutorial & Getting Started](https://developer.x.com/en/docs/tutorials) - Official X (Twitter) docs
- [Instagram Graph API Guide (Meta for Developers)](https://developers.facebook.com/docs/instagram-api/) - Facebook Instagram API
- [OAuth 2.0 Simplified](https://aaronparecki.com/oauth-2-simplified/) - OAuth explanation (latest edition)

## 🔧 Tools & Libraries

### Data Visualization
- [Recharts](https://recharts.org/) - React charting library built on D3 - **RECOMMENDED**
- [Chart.js](https://www.chartjs.org/) - Simple yet flexible JavaScript charting
- [ApexCharts](https://apexcharts.com/) - Modern interactive charts
- [Nivo](https://nivo.rocks/) - Beautiful React charts based on D3

### API Integration
- [Auth.js](https://authjs.dev/) - Authentication for Next.js with OAuth providers (formerly NextAuth.js)
- [Passport.js](http://www.passportjs.org/) - Authentication middleware for Node.js
- [Axios](https://axios-http.com/) - Promise-based HTTP client
- [SWR](https://swr.vercel.app/) - React Hooks for data fetching with caching
- [TanStack Query](https://tanstack.com/query/latest) - Powerful async state management

### Cron & Scheduling
- [node-cron](https://github.com/node-cron/node-cron) - Task scheduler for Node.js
- [Agenda](https://github.com/agenda/agenda) - Job scheduling with MongoDB
- [Bull](https://github.com/OptimalBits/bull) - Redis-based queue for Node.js

## 💻 GitHub Repositories
- [Social Media Dashboard React](https://github.com/topics/social-media-dashboard) - Various implementations
- [X (Twitter) Dashboard](https://github.com/suhailzone/twitter-dashboard) - X analytics example
- [Instagram Analytics Dashboard](https://github.com/topics/instagram-analytics) - Instagram integrations
- [Multi-Platform Social Dashboard](https://github.com/bradtraversy/social-dashboard) - Multi-API example

## 📖 Learning Resources

### OAuth & Authentication
- [OAuth 2.0 Playground](https://www.oauth.com/playground/) - Interactive OAuth testing
- [Understanding OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) - DigitalOcean guide
- [Auth.js Documentation](https://authjs.dev/getting-started/introduction) - Complete auth guide

### API Documentation
- [X API v2 Docs](https://developer.x.com/en/docs/x-api) - Official X (Twitter) API
- [Instagram Graph API](https://developers.facebook.com/docs/instagram-api) - Instagram data access
- [Facebook Graph API](https://developers.facebook.com/docs/graph-api/) - Facebook platform API
- [YouTube Analytics API](https://developers.google.com/youtube/analytics) - YouTube data
- [LinkedIn API](https://learn.microsoft.com/en-us/linkedin/) - LinkedIn integration

### Data Visualization
- [Recharts Documentation](https://recharts.org/en-US/api) - Complete Recharts guide
- [Data Visualization Best Practices](https://www.tableau.com/learn/articles/data-visualization) - Tableau guide
- [Chart Design Patterns](https://www.fusioncharts.com/blog/best-practices-for-creating-effective-charts/) - Chart selection

## 🌐 APIs & Services

### Social Media APIs
- [X API](https://developer.x.com/en/portal/dashboard) - Free tier: 100 posts/month (read) + basic access
- [Instagram Graph API](https://developers.facebook.com/apps/) - Requires Facebook App approval
- [Facebook Graph API](https://developers.facebook.com/docs/graph-api/) - Free with rate limits
- [YouTube Data API](https://console.cloud.google.com/) - 10,000 units/day free
- [LinkedIn API](https://www.linkedin.com/developers/apps) - OAuth required

### Alternative Data Sources
- [RapidAPI Social Media](https://rapidapi.com/category/Social) - Aggregated social APIs
- [Apify](https://apify.com/) - Web scraping for social data (alternative)
- [Social Blade API](https://socialblade.com/info/api) - Public social stats

## 🎨 Design Resources
- [Social Media Dashboard UI](https://dribbble.com/search/social-media-dashboard) - Dribbble designs
- [Analytics Dashboard Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=analytics+dashboard) - Figma templates
- [Data Visualization Color Palettes](https://coolors.co/palettes/trending/data) - Color schemes

## 📚 OAuth Flow Example
```javascript
// Auth.js configuration (formerly NextAuth.js)
import NextAuth from 'next-auth';
import TwitterProvider from 'next-auth/providers/twitter';

export default NextAuth({
  providers: [
    TwitterProvider({
      clientId: process.env.TWITTER_CLIENT_ID,
      clientSecret: process.env.TWITTER_CLIENT_SECRET,
      version: '2.0',
    }),
  ],
  callbacks: {
    async jwt({ token, account }) {
      if (account) {
        token.accessToken = account.access_token;
      }
      return token;
    },
    async session({ session, token }) {
      session.accessToken = token.accessToken;
      return session;
    },
  },
});

### 🚀 API Integration Example
// Fetch Twitter user metrics
async function getTwitterMetrics(accessToken) {
  const response = await fetch(
    'https://api.twitter.com/2/users/me?user.fields=public_metrics',
    {
      headers: {
        Authorization: `Bearer ${accessToken}`,
      },
    }
  );

  const data = await response.json();
  return {
    followers: data.data.public_metrics.followers_count,
    following: data.data.public_metrics.following_count,
    tweets: data.data.public_metrics.tweet_count,
  };
}

### 📊 Data Aggregation Example

// Combine metrics from multiple platforms
async function getAggregatedMetrics(userId) {
  const [twitter, instagram, facebook] = await Promise.all([
    getTwitterMetrics(userId),
    getInstagramMetrics(userId),
    getFacebookMetrics(userId),
  ]);

  return {
    totalFollowers: twitter.followers + instagram.followers + facebook.followers,
    platforms: { twitter, instagram, facebook },
    growthRate: calculateGrowthRate(/* ... */),
  };
}

### 🔐 Rate Limiting Handling

// Handle API rate limits gracefully
const rateLimitCache = new Map();

async function fetchWithRateLimit(url, options) {
  const cacheKey = url;
  const cached = rateLimitCache.get(cacheKey);

  if (cached && Date.now() < cached.expiry) {
    return cached.data;
  }

  try {
    const response = await fetch(url, options);

    if (response.status === 429) {
      const retryAfter = response.headers.get('Retry-After') || 60;
      throw new Error(`Rate limited. Retry after ${retryAfter}s`);
    }

    const data = await response.json();
    rateLimitCache.set(cacheKey, {
      data,
      expiry: Date.now() + 15 * 60 * 1000, // 15 min cache
    });

    return data;
  } catch (error) {
    console.error('API Error:', error);
    throw error;
  }
}