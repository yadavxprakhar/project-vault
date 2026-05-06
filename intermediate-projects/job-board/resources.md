# Resources for Job Board Platform

## 📺 Video Tutorials
- [Build a Job Board with Next.js 16 & Prisma](https://www.youtube.com/watch?v=5QlE6o-iYcE) - Full-stack implementation (2025/2026 edition)
- [Job Portal with Next.js 16, Clerk & Uploadthing](https://www.youtube.com/watch?v=4zmvgRbdDT0) - Complete tutorial with authentication and file uploads
- [Indeed Clone with Next.js 16, TanStack Query & Algolia](https://www.youtube.com/watch?v=xKs2IZZya7c) - JavaScript Mastery
- [Resume Upload & File Handling with Uploadthing](https://www.youtube.com/watch?v=1r-F3FIONl8) - Modern file handling tutorial

## 📚 Written Tutorials
- [Build a Job Board Application with Next.js 16](https://www.freecodecamp.org/news/how-to-build-a-job-board/) - freeCodeCamp guide (updated 2026)
- [Next.js Job Portal with Prisma, Clerk & Algolia](https://dev.to/codewithmarish/building-a-job-portal-with-nextjs-3h9p) - Dev.to tutorial (2025 edition)
- [Resume Upload with Uploadthing & S3](https://docs.uploadthing.com/getting-started) - Modern file upload guide
- [Email Notifications with Resend](https://resend.com/docs/send-with-nextjs) - Resend documentation

## 🔧 Tools & Libraries

### Search & Filtering
- [Algolia](https://www.algolia.com/) - Hosted search API - **RECOMMENDED**
- [Meilisearch](https://www.meilisearch.com/) - Open-source search engine
- [PostgreSQL Full-Text Search](https://www.postgresql.org/docs/current/textsearch.html) - Built-in search
- [Fuse.js](https://fusejs.io/) - Lightweight fuzzy search

### File Upload
- [Uploadthing](https://uploadthing.com/) - File uploads for Next.js - **RECOMMENDED**
- [AWS S3](https://aws.amazon.com/s3/) - Cloud storage
- [Multer](https://github.com/expressjs/multer) - File upload middleware
- [react-dropzone](https://react-dropzone.js.org/) - Drag-and-drop file upload

### Email Services
- [Resend](https://resend.com/) - Developer-first email API
- [SendGrid](https://sendgrid.com/) - Email delivery platform
- [Nodemailer](https://nodemailer.com/) - Email sending library
- [React Email](https://react.email/) - Email templates

### Forms & Validation
- [React Hook Form](https://react-hook-form.com/) - Performant forms
- [Zod](https://zod.dev/) - TypeScript-first schema validation
- [Formik](https://formik.org/) - Alternative form library

## 💻 GitHub Repositories
- [Job Board Next.js 16](https://github.com/adrianhajdin/project_next13_job_board) - Complete modern implementation
- [Indeed Clone with Next.js](https://github.com/topics/job-board) - Various implementations
- [Open Source Job Board](https://github.com/JobtechSwe/mydata-cv) - Reference project
- [ATS System with Next.js & Prisma](https://github.com/topics/applicant-tracking-system) - ATS examples
- [Job Board with Clerk & Uploadthing](https://github.com/topics/job-board) - Modern auth + file upload examples

## 📖 Learning Resources

### Job Board Domain
- [How ATSs Work](https://www.themuse.com/advice/beat-the-robots-how-to-get-your-resume-past-the-system-into-human-hands) - ATS basics
- [Job Board UX Best Practices](https://www.nngroup.com/articles/job-search-strategies/) - Nielsen Norman Group
- [Recruitment Process](https://www.shrm.org/resourcesandtools/tools-and-samples/toolkits/pages/recruiting.aspx) - HR guide

### Search Implementation
- [Algolia Documentation](https://www.algolia.com/doc/) - Complete search guide
- [Meilisearch Documentation](https://www.meilisearch.com/docs) - Open-source search guide
- [PostgreSQL Text Search](https://www.compose.com/articles/mastering-postgresql-tools-full-text-search-and-phrase-search/) - Text search guide

### Email Automation
- [Email Best Practices](https://sendgrid.com/blog/email-best-practices/) - SendGrid guide
- [Transactional Emails](https://postmarkapp.com/guides/transactional-email-best-practices) - Postmark guide
- [Email Templates](https://react.email/examples) - React Email examples

## 🌐 APIs & Services
- [Algolia](https://www.algolia.com/) - Search API (10k searches/month free)
- [Uploadthing](https://uploadthing.com/) - File uploads (free tier available)
- [Resend](https://resend.com/) - Email API (100 emails/day free)
- [Google Maps API](https://developers.google.com/maps) - Location autocomplete
- [LinkedIn Jobs API](https://learn.microsoft.com/en-us/linkedin/) - Job data (enterprise)

## 🎨 Design Resources
- [Indeed Design](https://www.indeed.com/) - Job board reference
- [LinkedIn Jobs](https://www.linkedin.com/jobs/) - UI inspiration
- [Wellfound (AngelList)](https://wellfound.com/) - Startup job board design
- [Figma Job Board Templates](https://www.figma.com/community/search?resource_type=mixed&sort_by=relevancy&query=job+board) - Free templates

## 📚 Database Schema Example
```prisma
model User {
  id            String        @id @default(cuid())
  email         String        @unique
  name          String
  role          UserRole      @default(JOB_SEEKER)
  profile       Profile?
  company       Company?
  applications  Application[]
  savedJobs     SavedJob[]
  createdAt     DateTime      @default(now())
}

enum UserRole {
  JOB_SEEKER
  EMPLOYER
  ADMIN
}

model Profile {
  id            String   @id @default(cuid())
  userId        String   @unique
  user          User     @relation(fields: [userId], references: [id])
  resumeUrl     String?
  phone         String?
  location      String?
  bio           String?
  skills        String[]
  experience    Json[]   // Array of work experience objects
  education     Json[]   // Array of education objects
  linkedinUrl   String?
  portfolioUrl  String?
}

model Company {
  id          String   @id @default(cuid())
  name        String
  logo        String?
  website     String?
  description String?
  location    String?
  size        String?
  industry    String?
  ownerId     String   @unique
  owner       User     @relation(fields: [ownerId], references: [id])
  jobs        Job[]
  createdAt   DateTime @default(now())
}

model Job {
  id            String        @id @default(cuid())
  title         String
  description   String        @db.Text
  location      String
  type          JobType       // FULL_TIME, PART_TIME, CONTRACT, INTERNSHIP
  workMode      WorkMode      // REMOTE, HYBRID, ONSITE
  experience    ExperienceLevel
  salaryMin     Int?
  salaryMax     Int?
  skills        String[]
  companyId     String
  company       Company       @relation(fields: [companyId], references: [id])
  applications  Application[]
  savedBy       SavedJob[]
  status        JobStatus     @default(ACTIVE)
  views         Int           @default(0)
  applications  Int           @default(0)
  publishedAt   DateTime?
  expiresAt     DateTime?
  createdAt     DateTime      @default(now())
  updatedAt     DateTime      @updatedAt
}

enum JobType {
  FULL_TIME
  PART_TIME
  CONTRACT
  INTERNSHIP
}

enum WorkMode {
  REMOTE
  HYBRID
  ONSITE
}

enum ExperienceLevel {
  ENTRY
  MID
  SENIOR
  LEAD
}

enum JobStatus {
  DRAFT
  ACTIVE
  CLOSED
  EXPIRED
}

model Application {
  id          String            @id @default(cuid())
  jobId       String
  job         Job               @relation(fields: [jobId], references: [id])
  userId      String
  user        User              @relation(fields: [userId], references: [id])
  resumeUrl   String
  coverLetter String?           @db.Text
  status      ApplicationStatus @default(APPLIED)
  appliedAt   DateTime          @default(now())
  updatedAt   DateTime          @updatedAt

  @@unique([jobId, userId])
}

enum ApplicationStatus {
  APPLIED
  REVIEWING
  SHORTLISTED
  INTERVIEW
  OFFER
  REJECTED
}

model SavedJob {
  id        String   @id @default(cuid())
  userId    String
  user      User     @relation(fields: [userId], references: [id])
  jobId     String
  job       Job      @relation(fields: [jobId], references: [id])
  savedAt   DateTime @default(now())

  @@unique([userId, jobId])
}