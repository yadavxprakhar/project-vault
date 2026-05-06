# Resources for Kanban Board Project

## 📺 Video Tutorials
- [Build a Trello Clone with React & dnd-kit](https://www.youtube.com/watch?v=8r0vN3Z0v7E) - Clever Programmer: Modern drag-and-drop implementation (2025)
- [Full Stack Kanban Board with Next.js, Prisma & Supabase](https://www.youtube.com/watch?v=wOYVAABwwUA) - JavaScript Mastery: Complete MERN-style tutorial
- [Next.js 15 Kanban App with dnd-kit & Tailwind](https://www.youtube.com/watch?v=vsrQhfKcWYA) - Code with Antonio: Modern Next.js 15 approach
- [Master Drag and Drop in React with dnd-kit](https://www.youtube.com/watch?v=aYZRRyukuIw) - Web Dev Simplified: Mastering drag and drop (updated)

## 📚 Written Tutorials
- [Build a Kanban Board with React & dnd-kit](https://www.freecodecamp.org/news/how-to-build-a-kanban-board-with-react/) - freeCodeCamp comprehensive guide (2025 edition)
- [Trello Clone with React, TypeScript & dnd-kit](https://dev.to/naveenkumarnain/how-to-build-a-trello-clone-with-react-and-redux-2hc5) - Dev.to step-by-step (updated)
- [Drag and Drop in React with dnd-kit](https://blog.logrocket.com/drag-and-drop-react-dnd-kit/) - LogRocket dnd-kit guide
- [Building a Kanban Board with Next.js 15, Prisma & Supabase](https://vercel.com/guides/nextjs-prisma-postgres) - Vercel official guide (updated 2026)

## 🔧 Tools & Libraries

### Drag & Drop
- [dnd-kit](https://dndkit.com/) - Modern, lightweight drag and drop toolkit - **RECOMMENDED**
- [@hello-pangea/dnd](https://github.com/hello-pangea/dnd) - Modern maintained fork of react-beautiful-dnd
- [react-dnd](https://react-dnd.github.io/react-dnd/) - Flexible drag and drop library

### State Management
- [Redux Toolkit](https://redux-toolkit.js.org/) - Official Redux toolset with best practices
- [Zustand](https://github.com/pmndrs/zustand) - Minimal state management (300 bytes)
- [Jotai](https://jotai.org/) - Primitive and flexible atomic state management
- [TanStack Query](https://tanstack.com/query/latest) - Data fetching and synchronization (formerly React Query)

### UI Components
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [shadcn/ui](https://ui.shadcn.com/) - Re-usable components built with Radix + Tailwind - **HIGHLY RECOMMENDED**
- [Radix UI](https://www.radix-ui.com/) - Unstyled, accessible primitives
- [Headless UI](https://headlessui.com/) - Unstyled components by Tailwind
- [Chakra UI](https://chakra-ui.com/) - Accessible React component library

### Backend & Database
- [Supabase](https://supabase.com/) - Open-source Firebase alternative (Postgres)
- [Prisma](https://www.prisma.io/) - Next-gen TypeScript ORM
- [tRPC](https://trpc.io/) - End-to-end typesafe APIs
- [Drizzle ORM](https://orm.drizzle.team/) - Lightweight TypeScript ORM

## 💻 GitHub Repositories
- [React Kanban Board](https://github.com/yogaboll/react-kanban) - Clean vanilla implementation
- [Trello Clone - Full Stack](https://github.com/Railly/trello-clone) - Complete MERN example
- [Next.js Kanban with dnd-kit](https://github.com/lucasmcartney/nextjs-kanban) - Modern Next.js stack
- [Kanban Task Manager](https://github.com/Frontendmentor-Projects/kanban-task-management) - Production-ready with TypeScript
- [Jira Clone React](https://github.com/oldboyxx/jira_clone) - Advanced features and beautiful UI

## 📖 Learning Resources

### State Management
- [Redux Essentials](https://redux.js.org/tutorials/essentials/part-1-overview-concepts) - Official Redux tutorial
- [Understanding React State](https://kentcdodds.com/blog/application-state-management-with-react) - Kent C. Dodds
- [State Management Patterns](https://www.patterns.dev/posts/state-management/) - Patterns.dev guide
- [Zustand Tutorial](https://docs.pmnd.rs/zustand/getting-started/introduction) - Lightweight alternative

### Drag & Drop
- [dnd-kit Documentation](https://docs.dndkit.com/) - Complete dnd-kit guide
- [Drag and Drop Accessibility](https://www.smashingmagazine.com/2018/01/drag-drop-web-pages-accessibility/) - A11y guide
- [React DnD Tutorial](https://react-dnd.github.io/react-dnd/docs/tutorial) - Official react-dnd tutorial

### Database Design
- [Database Normalization](https://www.freecodecamp.org/news/database-normalization-1nf-2nf-3nf-table-examples/) - Schema design
- [PostgreSQL for Beginners](https://www.postgresqltutorial.com/) - SQL fundamentals
- [Prisma Schema Guide](https://www.prisma.io/docs/concepts/components/prisma-schema) - Modern ORM approach

## 🌐 APIs & Services
- [Supabase](https://supabase.com/) - Backend as a service (generous free tier)
- [Firebase](https://firebase.google.com/) - Alternative backend platform
- [Vercel](https://vercel.com/) - Deployment platform (free hobby tier)
- [Cloudinary](https://cloudinary.com/) - File attachment storage
- [Uploadthing](https://uploadthing.com/) - File uploads for Next.js

## 🎨 Design Resources
- [Trello Design System](https://atlassian.design/) - Official Trello design inspiration
- [Figma Kanban Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=kanban) - Free UI kits
- [Kanban UI Kit](https://www.uistore.design/items/kanban-free-ui-kit/) - Pre-made components
- [Linear Design](https://linear.app/) - Modern project management UI inspiration

## 📚 Advanced Topics
- [Optimistic UI Updates](https://www.apollographql.com/docs/react/performance/optimistic-ui/) - Better UX patterns
- [Real-time Collaboration](https://liveblocks.io/examples) - Multiplayer features with Liveblocks
- [Undo/Redo Implementation](https://redux.js.org/usage/implementing-undo-history) - Complex state patterns
- [CRDT for Collaboration](https://crdt.tech/) - Conflict-free replicated data types

## 🚀 Quick Start Code Snippet
```typescript
// Example with dnd-kit
import { DndContext, closestCenter } from '@dnd-kit/core';
import { SortableContext, verticalListSortingStrategy } from '@dnd-kit/sortable';

function KanbanBoard() {
  const [columns, setColumns] = useState({
    todo: ['Task 1', 'Task 2'],
    inProgress: ['Task 3'],
    done: ['Task 4']
  });

  const handleDragEnd = (event) => {
    const { active, over } = event;
    if (!over) return;

    // Logic to move card between columns
    // Update state optimistically
  };

  return (
    <DndContext collisionDetection={closestCenter} onDragEnd={handleDragEnd}>
      <div className="board">
        {Object.entries(columns).map(([columnId, tasks]) => (
          <SortableContext
            key={columnId}
            items={tasks}
            strategy={verticalListSortingStrategy}
          >
            <Column id={columnId} tasks={tasks} />
          </SortableContext>
        ))}
      </div>
    </DndContext>
  );
}


### 📊 Database Schema Example (Prisma)

model Board {
  id          String   @id @default(cuid())
  title       String
  description String?
  ownerId     String
  owner       User     @relation(fields: [ownerId], references: [id])
  columns     Column[]
  members     BoardMember[]
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
}

model Column {
  id        String   @id @default(cuid())
  title     String
  position  Int
  boardId   String
  board     Board    @relation(fields: [boardId], references: [id])
  cards     Card[]
  createdAt DateTime @default(now())
}

model Card {
  id          String   @id @default(cuid())
  title       String
  description String?
  position    Int
  columnId    String
  column      Column   @relation(fields: [columnId], references: [id])
  assignees   User[]
  labels      Label[]
  dueDate     DateTime?
  attachments String[]
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
}