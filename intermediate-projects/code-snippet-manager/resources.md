# Resources for Code Snippet Manager

## 📺 Video Tutorials
- [Build a Code Snippet Manager with Next.js 16 & Monaco Editor](https://www.youtube.com/watch?v=5QlE6o-iYcE) - Complete React tutorial (2025/2026 edition)
- [Monaco Editor Integration in Next.js](https://www.youtube.com/watch?v=LWFGUOpLXEo) - VS Code editor in browser with modern setup
- [Syntax Highlighting with Shiki & Prism.js](https://www.youtube.com/watch?v=2-xvPbWUyLU) - Prism.js + Shiki implementation
- [Full-Stack Code Sharing Platform with Next.js & Prisma](https://www.youtube.com/watch?v=fRLebWuIhqs) - Full-stack example

## 📚 Written Tutorials
- [Build a Code Snippet Manager with Next.js 16](https://www.freecodecamp.org/news/how-to-build-a-code-snippet-manager/) - freeCodeCamp guide (updated 2026)
- [Monaco Editor Guide](https://microsoft.github.io/monaco-editor/) - Official documentation
- [Syntax Highlighting with Prism.js & Shiki](https://prismjs.com/#basic-usage) - Prism.js tutorial
- [Search Implementation with Algolia & Fuse.js](https://www.algolia.com/doc/guides/building-search-ui/what-is-instantsearch/react/) - Algolia search guide

## 🔧 Tools & Libraries

### Code Editors
- [Monaco Editor](https://microsoft.github.io/monaco-editor/) - VS Code's editor - **RECOMMENDED**
- [CodeMirror](https://codemirror.net/) - Versatile text editor
- [Ace Editor](https://ace.c9.io/) - High-performance code editor
- [react-simple-code-editor](https://github.com/satya164/react-simple-code-editor) - Lightweight alternative

### Syntax Highlighting
- [Shiki](https://shiki.matsu.io/) - VS Code's syntax highlighter - **RECOMMENDED**
- [Prism.js](https://prismjs.com/) - Lightweight syntax highlighter
- [Highlight.js](https://highlightjs.org/) - Syntax highlighting
- [react-syntax-highlighter](https://github.com/react-syntax-highlighter/react-syntax-highlighter) - React component

### Search
- [Algolia](https://www.algolia.com/) - Hosted search API
- [Fuse.js](https://fusejs.io/) - Lightweight fuzzy search
- [FlexSearch](https://github.com/nextapps-de/flexsearch) - Full-text search
- [PostgreSQL Full-Text](https://www.postgresql.org/docs/current/textsearch.html) - Built-in search

### Markdown
- [react-markdown](https://github.com/remarkjs/react-markdown) - Markdown to React
- [MDX](https://mdxjs.com/) - Markdown + JSX
- [remark](https://github.com/remarkjs/remark) - Markdown processor
- [rehype](https://github.com/rehypejs/rehype) - HTML processor

## 💻 GitHub Repositories
- [GitHub Gist](https://gist.github.com/) - Official Gist platform (reference)
- [Carbon](https://github.com/carbon-app/carbon) - Code screenshot generator
- [SnippetBox](https://github.com/topics/code-snippets) - Various implementations
- [CodePen](https://codepen.io/) - Online code editor (reference)
- [Ray.so](https://ray.so/) - Code screenshot tool (inspiration)

## 📖 Learning Resources

### Code Editors
- [Monaco Editor Documentation](https://microsoft.github.io/monaco-editor/docs.html) - Complete guide
- [CodeMirror 6 Guide](https://codemirror.net/docs/guide/) - Modern CodeMirror
- [Building Code Editors](https://blog.replit.com/code-editors) - Replit's guide

### Syntax Highlighting
- [Prism.js Documentation](https://prismjs.com/docs/) - Complete Prism guide
- [Language Grammars](https://macromates.com/manual/en/language_grammars) - TextMate grammars
- [Shiki Documentation](https://shiki.matsu.io/guide/) - VS Code themes

### Search Implementation
- [Full-Text Search Guide](https://www.postgresql.org/docs/current/textsearch-intro.html) - PostgreSQL search
- [Algolia Documentation](https://www.algolia.com/doc/) - Algolia setup
- [Fuzzy Search Algorithms](https://www.freecodecamp.org/news/fuzzy-string-matching-with-postgresql/) - Fuzzy matching

## 🌐 APIs & Services
- [GitHub Gist API](https://docs.github.com/en/rest/gists) - Import/export gists
- [Algolia](https://www.algolia.com/) - Search as a service (10k searches/month free)
- [Carbon API](https://carbon.now.sh/) - Code screenshot generation
- [Prettier API](https://prettier.io/docs/en/api.html) - Code formatting

## 🎨 Design Resources
- [GitHub Gist UI](https://gist.github.com/) - Design reference
- [Carbon Design](https://carbon.now.sh/) - Screenshot tool inspiration
- [Ray.so UI](https://ray.so/) - Modern code sharing design
- [Figma Code Editor Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=code+editor) - Templates

## 📚 Monaco Editor Integration Example
```tsx
import Editor from '@monaco-editor/react';

export function CodeEditor({ value, language, onChange, theme = 'vs-dark' }) {
  return (
    <Editor
      height="400px"
      language={language}
      value={value}
      theme={theme}
      onChange={onChange}
      options={{
        minimap: { enabled: false },
        fontSize: 14,
        lineNumbers: 'on',
        scrollBeyondLastLine: false,
        automaticLayout: true,
        tabSize: 2,
      }}
    />
  );
}