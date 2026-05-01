# Resources for Recipe Finder

## 📺 Video Tutorials
- [Build a Recipe Finder App with HTML, CSS & JavaScript](https://www.youtube.com/watch?v=Ci9Z-5cekrs) - Complete tutorial with TheMealDB API
- [Recipe Finder App using TheMealDB API](https://www.youtube.com/watch?v=IgAtl7x5ES4) - Step-by-step series focusing on search and filters
- [Build a Recipe App with React & Spoonacular API (2025)](https://www.youtube.com/watch?v=-bxhKTKxtOM) - Full React implementation with modern hooks
- [Advanced Recipe Finder with Filters and Pagination](https://www.youtube.com/watch?v=U9T6YkEDkMo) - JavaScript Mastery: Multiple filters, favorites and localStorage

## 📚 Written Tutorials
- [Design a Recipe App in HTML CSS & JavaScript](https://www.geeksforgeeks.org/javascript/design-a-recipe-app-in-html-css-javascript/) - GeeksforGeeks comprehensive guide (updated 2025)
- [Build a Recipe Finder App with React and TheMealDB](https://dev.to/kunaal438/build-a-recipe-app-with-react-2ch5) - Dev.to React walkthrough with modern best practices
- [Spoonacular API Documentation](https://spoonacular.com/food-api/docs) - Official comprehensive API documentation
- [TheMealDB API Guide](https://www.themealdb.com/api.php) - Free recipe API docs and usage examples

## 🔧 Tools & Libraries
- [Spoonacular API](https://spoonacular.com/food-api) - Comprehensive recipe API with nutrition data (150 points/day free) - **RECOMMENDED**
- [TheMealDB API](https://www.themealdb.com/api.php) - Completely free recipe database API (ideal for beginners)
- [Edamam Recipe API](https://developer.edamam.com/edamam-recipe-api) - Strong nutrition and recipe data with generous free tier
- [API-Ninjas Recipe API](https://api-ninjas.com/api/recipe) - Access to 200,000+ recipes across cuisines
- [Axios](https://axios-http.com/) - HTTP client for cleaner API requests
- [vanilla-lazyload](https://github.com/verlok/vanilla-lazyload) - Optimize image loading for recipe cards

## 💻 GitHub Repositories
- [recipe-finder](https://github.com/bradtraversy/vanillawebprojects/tree/master/recipe-finder) - Vanilla JS with TheMealDB by Traversy Media
- [React-Recipe-App](https://github.com/WebDevSimplified/React-Recipe-App) - React implementation with search and favorites
- [recipe-app](https://github.com/florinpop17/recipe-app) - Feature-rich example with multiple filters
- [react-recipe-finder](https://github.com/kunaal438/react-recipe-app) - React with localStorage favorites and modern UI
- [spoonacular-recipe-examples](https://github.com/topics/spoonacular-api) - Collection of Spoonacular implementations

## 📖 Learning Resources
- [Working with REST APIs in JavaScript](https://www.freecodecamp.org/news/how-to-use-rest-api/) - API basics for beginners
- [JavaScript Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) - MDN fetch tutorial
- [CSS Grid Layout for Cards](https://css-tricks.com/snippets/css/complete-guide-grid/) - Recipe card layouts
- [Handling API Rate Limits](https://blog.logrocket.com/handle-api-rate-limits-react/) - Stay within free tier
- [Image Lazy Loading Best Practices](https://web.dev/browser-level-image-lazy-loading/) - Performance optimization for food images

## 🌐 APIs & Services
- [Spoonacular API](https://spoonacular.com/food-api/console#Dashboard) - Get free API key (150 points/day)
- [TheMealDB API](https://www.themealdb.com/api.php) - No API key needed for most calls (use test key "1")
- [Edamam Recipe Search](https://developer.edamam.com/edamam-recipe-api) - 10,000 requests/month free
- [API-Ninjas Recipe API](https://api-ninjas.com/api/recipe) - Large recipe database with simple REST access
- [USDA FoodData Central API](https://fdc.nal.usda.gov/api-guide.html) - Accurate nutritional data

## 🎨 Design Resources
- [Recipe App UI Designs](https://dribbble.com/search/recipe-app) - Dribbble inspiration
- [Food Photography](https://unsplash.com/s/photos/food) - Free high-quality recipe images (Unsplash)
- [Recipe Card Templates](https://codepen.io/search/pens?q=recipe+card) - CodePen layouts
- [Cooking Icons](https://www.flaticon.com/packs/cooking-57) - Free cooking-related icons

## 📚 API Response Example (Spoonacular)
```javascript
// Example search response structure
{
  "results": [
    {
      "id": 715538,
      "title": "Bruschetta with Tomato and Basil",
      "image": "https://...",
      "readyInMinutes": 45,
      "servings": 4,
      "vegetarian": true,
      "vegan": false,
      "glutenFree": false
    }
  ],
  "totalResults": 86
}