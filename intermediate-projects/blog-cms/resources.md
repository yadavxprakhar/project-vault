# Resources for Blog CMS

## 📺 Video Tutorials
- [How to Build an MDX Blog with Next.js 15](https://www.youtube.com/watch?v=9Qd2VC0bsgQ) - Complete MDX + Tailwind tutorial with syntax highlighting and TOC
- [Build a Full Stack Blog with Next.js | Tiptap Editor, Clerk & Database](https://www.youtube.com/watch?v=Dbhb4UYaptk) - Modern full-stack blog with rich text editor
- [Building a Modern Blog with MDX and Next.js 16](https://www.youtube.com/watch?v=J_0SBJMxmcw) - Production-ready MDX setup with React Server Components
- [Rich Text Editor with Tiptap v3 in Next.js 15](https://www.youtube.com/watch?v=QVffer2fRfg) - Tiptap integration with shadcn/ui styling

## 📚 Written Tutorials
- [MDX in Next.js](https://nextjs.org/docs/pages/guides/mdx) - Official Next.js MDX guide (updated for App Router & React Server Components)
- [How to Build a Markdown Blog with Next.js 15](https://www.adeelhere.com/blog/2025-12-10-how-to-build-a-markdown-blog-with-nextjs) - Zero-dependency MDX blog guide
- [Complete Guide to Building a Modern Blog with Next.js](https://www.naufalfaisa.my.id/blog/nextjs-blog-guide.mdx) - Dynamic routing, MDX, SEO, and image optimization
- [Building a Modern Blog with MDX and Next.js 16](https://www.yourtechpilot.com/blog/building-mdx-blog-nextjs) - Production-ready setup with syntax highlighting and table of contents

## 🔧 Tools & Libraries

### Content & Markdown
- [MDX](https://mdxjs.com/) - Markdown for the component era - **RECOMMENDED**
- [Contentlayer](https://www.contentlayer.dev/) - Content SDK for Next.js (still widely used in popular templates)
- [gray-matter](https://github.com/jonschlinkert/gray-matter) - Parse front-matter from markdown
- [remark](https://github.com/remarkjs/remark) - Markdown processor
- [rehype](https://github.com/rehypejs/rehype) - HTML processor for syntax highlighting

### Rich Text Editors
- [Tiptap](https://tiptap.dev/) - Headless editor framework - **RECOMMENDED**
- [Lexical](https://lexical.dev/) - Facebook's extensible text editor
- [Slate.js](https://www.slatejs.org/) - Customizable framework for rich text
- [Editor.js](https://editorjs.io/) - Block-style editor

### SEO & Metadata
- [next-seo](https://github.com/garmeeh/next-seo) - SEO plugin for Next.js
- [React Helmet Async](https://github.com/nfl/react-helmet-async) - Manage document head
- [next-sitemap](https://github.com/iamvishnusankar/next-sitemap) - Sitemap generator
- [Built-in Metadata API](https://nextjs.org/docs/app/building-your-application/optimizing/metadata) - Next.js 15+ native SEO

### Email & Newsletters
- [Resend](https://resend.com/) - Email API for developers - **RECOMMENDED**
- [React Email](https://react.email/) - Email templates with React
- [Mailchimp API](https://mailchimp.com/developer/) - Newsletter management
- [ConvertKit API](https://developers.convertkit.com/) - Email marketing

## 💻 GitHub Repositories
- [Tailwind Nextjs Starter Blog](https://github.com/timlrx/tailwind-nextjs-starter-blog) - Most popular feature-rich MDX blog template
- [Next.js Blog Starter](https://github.com/vercel/next.js/tree/canary/examples/blog-starter) - Official Next.js example
- [Taxonomy](https://github.com/shadcn-ui/taxonomy) - Next.js 14+ blog template by shadcn
- [Next.js MDX Blog](https://github.com/leerob/next-mdx-blog) - Clean MDX + TypeScript + Tailwind example
- [Ghost](https://github.com/TryGhost/Ghost) - Open-source blogging platform (for reference)

## 📖 Learning Resources

### MDX & Markdown
- [MDX Documentation](https://mdxjs.com/docs/) - Complete MDX guide
- [Markdown Guide](https://www.markdownguide.org/) - Markdown syntax reference
- [Writing MDX](https://mdxjs.com/docs/using-mdx/) - Best practices for MDX
- [Contentlayer Tutorial](https://www.contentlayer.dev/docs/getting-started) - Content management

### SEO Best Practices
- [Google SEO Starter Guide](https://developers.google.com/search/docs/beginner/seo-starter-guide) - Official Google guide
- [Next.js SEO](https://nextjs.org/learn/seo/introduction-to-seo) - SEO for Next.js apps
- [Schema.org](https://schema.org/) - Structured data for search engines
- [Open Graph Protocol](https://ogp.me/) - Social media previews

### Content Strategy
- [Content Strategy for Blogs](https://contentmarketinginstitute.com/articles/content-strategy-basics/) - CMI guide
- [Writing for the Web](https://www.nngroup.com/articles/how-users-read-on-the-web/) - Nielsen Norman Group
- [Blog Post Structure](https://backlinko.com/blog-post-templates) - Backlinko templates

## 🌐 APIs & Services
- [Payload CMS](https://payloadcms.com/) - TypeScript-native, self-hosted headless CMS (rising fast in 2026)
- [Sanity.io](https://www.sanity.io/) - Headless CMS with real-time collaboration
- [Strapi](https://strapi.io/) - Open-source headless CMS
- [Contentful](https://www.contentful.com/) - Enterprise content platform
- [Prismic](https://prismic.io/) - Headless page builder
- [Hygraph](https://hygraph.com/) - GraphQL-based CMS

## 🎨 Design Resources
- [Blog UI Designs](https://dribbble.com/search/blog-design) - Dribbble inspiration
- [Medium Design](https://medium.design/) - Medium's design system
- [Substack Design](https://substack.com/) - Clean blog layouts
- [Figma Blog Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=blog) - Free templates

## 📚 MDX Integration Example
```typescript
// contentlayer.config.ts
import { defineDocumentType, makeSource } from 'contentlayer/source-files';

export const Post = defineDocumentType(() => ({
  name: 'Post',
  filePathPattern: `**/*.mdx`,
  contentType: 'mdx',
  fields: {
    title: { type: 'string', required: true },
    date: { type: 'date', required: true },
    description: { type: 'string', required: true },
    image: { type: 'string' },
    categories: { type: 'list', of: { type: 'string' } },
    tags: { type: 'list', of: { type: 'string' } },
  },
  computedFields: {
    slug: {
      type: 'string',
      resolve: (post) => post._raw.flattenedPath,
    },
    readingTime: {
      type: 'number',
      resolve: (post) => {
        const wordsPerMinute = 200;
        const words = post.body.raw.split(/\s+/).length;
        return Math.ceil(words / wordsPerMinute);
      },
    },
  },
}));

export default makeSource({
  contentDirPath: 'content/posts',
  documentTypes: [Post],
});

### 🚀 Blog Post Page Example

// app/blog/[slug]/page.tsx
import { allPosts } from 'contentlayer/generated';
import { notFound } from 'next/navigation';
import { Mdx } from '@/components/mdx-components';

export async function generateStaticParams() {
  return allPosts.map((post) => ({
    slug: post.slug,
  }));
}

export default function BlogPost({ params }: { params: { slug: string } }) {
  const post = allPosts.find((p) => p.slug === params.slug);

  if (!post) notFound();

  return (
    <article>
      <h1>{post.title}</h1>
      <time>{new Date(post.date).toLocaleDateString()}</time>
      <p>{post.description}</p>
      <Mdx code={post.body.code} />
    </article>
  );
}

export async function generateMetadata({ params }) {
  const post = allPosts.find((p) => p.slug === params.slug);

  return {
    title: post?.title,
    description: post?.description,
    openGraph: {
      title: post?.title,
      description: post?.description,
      images: [post?.image],
    },
  };
}

### 📊 Database Schema Example (Prisma)

model Post {
  id          String    @id @default(cuid())
  title       String
  slug        String    @unique
  content     String    @db.Text
  excerpt     String?
  coverImage  String?
  published   Boolean   @default(false)
  publishedAt DateTime?
  authorId    String
  author      User      @relation(fields: [authorId], references: [id])
  categories  Category[]
  tags        Tag[]
  comments    Comment[]
  views       Int       @default(0)
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt
}

model Comment {
  id        String   @id @default(cuid())
  content   String
  postId    String
  post      Post     @relation(fields: [postId], references: [id])
  authorId  String
  author    User     @relation(fields: [authorId], references: [id])
  approved  Boolean  @default(false)
  createdAt DateTime @default(now())
}

model Category {
  id    String @id @default(cuid())
  name  String @unique
  slug  String @unique
  posts Post[]
}

model Tag {
  id    String @id @default(cuid())
  name  String @unique
  slug  String @unique
  posts Post[]
}

### 📧 Newsletter Subscription Example

// app/api/subscribe/route.ts
import { Resend } from 'resend';

const resend = new Resend(process.env.RESEND_API_KEY);

export async function POST(req: Request) {
  const { email } = await req.json();

  try {
    await resend.contacts.create({
      email,
      audienceId: process.env.RESEND_AUDIENCE_ID,
    });

    return Response.json({ message: 'Subscribed successfully' });
  } catch (error) {
    return Response.json({ error: 'Subscription failed' }, { status: 500 });
  }
}