# 🚀 Job Genie

> Your AI-powered companion for landing your dream job

![Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-1.0.0-informational)



## 📋 Table of Contents

- [✨ Features](#-features)
- [🛠️ Tech Stack](#️-tech-stack)
- [🚀 Getting Started](#-getting-started)
- [📁 Project Structure](#-project-structure)
- [🔧 Configuration](#-configuration)
- [📚 API Routes](#-api-routes)
- [🎨 Components](#-components)
- [💾 Database](#-database)
- [🤖 Inngest Integration](#-inngest-integration)
- [🌙 Theming](#-theming)
- [📝 License](#-license)



## ✨ Features

🤖 **AI-Powered Resume Builder**
- Generate and optimize your resume with AI assistance
- Multiple resume templates and styles
- Real-time preview and editing

📄 **Cover Letter Generator**
- Create personalized cover letters instantly
- AI-driven content suggestions
- Customizable templates for any job

💼 **Job Finding & Matching**
- Browse and discover job opportunities
- Smart job matching based on your profile
- Save and track applications

🎯 **Mock Interview Simulator**
- Practice interviews with AI feedback
- Performance analytics and charts
- Industry-specific interview questions
- Real-time scoring and suggestions

📊 **Comprehensive Dashboard**
- Track your job search progress
- View application history
- Performance analytics
- Quick access to all tools

🔐 **Secure Authentication**
- Clerk-powered authentication
- Secure user session management
- Privacy-first approach



## 🛠️ Tech Stack

### Frontend
- **Framework**: [Next.js 15](https://nextjs.org/) - React framework
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS
- **UI Components**: Custom components with shadcn/ui patterns
- **State Management**: React Hooks

### Backend
- **Runtime**: Node.js
- **Database**: [Prisma ORM](https://www.prisma.io/)
- **Authentication**: [Clerk](https://clerk.com/)
- **Background Jobs**: [Inngest](https://www.inngest.com/)

### DevTools
- **Linting**: ESLint
- **Build Tool**: Next.js built-in
- **Package Manager**: npm



## 🚀 Getting Started

### Prerequisites

- Node.js 18+ and npm
- Database (PostgreSQL recommended)
- Clerk account for authentication
- Inngest account for background jobs

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/job-genie.git
   cd job-genie
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Setup environment variables**
   ```bash
   cp .env.example .env.local
   ```
   
   Configure the following in `.env.local`:
   ```env
   DATABASE_URL=your_database_url
   CLERK_PUBLISHABLE_KEY=your_clerk_key
   CLERK_SECRET_KEY=your_clerk_secret
   INNGEST_EVENT_KEY=your_inngest_key
   NEXT_PUBLIC_API_URL=http://localhost:3000
   ```

4. **Setup Prisma Database**
   ```bash
   npx prisma migrate dev
   npx prisma generate
   ```

5. **Start development server**
   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) in your browser 🎉



## 📁 Project Structure

```
job-genie/
├── 📄 app/                    # Next.js app directory
│   ├── (auth)/               # Authentication routes
│   │   ├── sign-in/          # Login page
│   │   └── sign-up/          # Registration page
│   ├── (main)/               # Main application routes
│   │   ├── dashboard/        # Dashboard overview
│   │   ├── ai-cover-letter/  # Cover letter generator
│   │   ├── resume/           # Resume builder
│   │   ├── interview/        # Interview simulator
│   │   ├── find-job/         # Job search
│   │   └── onboarding/       # User onboarding
│   ├── api/                  # API routes
│   │   └── inngest/          # Inngest webhook
│   └── layout.js             # Root layout
│
├── 🔧 actions/               # Server actions
│   ├── chatbot-output.js
│   ├── cover-letter.js
│   ├── dashboard.js
│   ├── interview.js
│   ├── job-result.js
│   ├── resume.js
│   └── user.js
│
├── 🎨 components/            # React components
│   ├── ui/                   # Reusable UI components
│   │   ├── button.jsx
│   │   ├── card.jsx
│   │   ├── dialog.jsx
│   │   ├── input.jsx
│   │   ├── select.jsx
│   │   └── ... more UI components
│   ├── chatbot/              # Chat interface
│   ├── header.jsx
│   └── theme-provider.jsx
│
├── 📚 lib/                   # Utility functions
│   ├── prisma.js             # Prisma client
│   ├── checkUser.js          # User validation
│   ├── utils.js              # Helper functions
│   ├── schema.js             # Data schemas
│   └── inngest/              # Background job setup
│
├── 💾 prisma/                # Database schema
│   ├── schema.prisma         # Prisma schema
│   └── migrations/           # Database migrations
│
├── 🎯 hooks/                 # Custom React hooks
│   └── use-fetch.js
│
├── 📊 data/                  # Static data
│   ├── faqs.js
│   ├── features.js
│   ├── industries.js
│   └── testimonial.js
│
├── 📁 public/                # Static assets
│
├── ⚙️ Configuration Files
│   ├── next.config.mjs       # Next.js config
│   ├── tailwind.config.mjs   # Tailwind config
│   ├── postcss.config.mjs    # PostCSS config
│   ├── jsconfig.json         # JS compiler options
│   ├── eslint.config.mjs     # ESLint rules
│   ├── components.json       # Component library config
│   └── middleware.js         # Next.js middleware
│
└── 📦 package.json           # Dependencies & scripts
```



## 🔧 Configuration

### Next.js Configuration
See `next.config.mjs` for Next.js specific settings.

### Tailwind CSS
Customize styles in `tailwind.config.mjs`:
- Custom theme colors
- Spacing scale
- Font families
- Animation configs

### TypeScript/JavaScript
Configuration in `jsconfig.json` with path aliases for cleaner imports.

### ESLint
Code quality rules defined in `eslint.config.mjs`.

---

## 📚 API Routes

### Authentication
- `GET /api/auth` - Check authentication status

### Inngest Integration
- `POST /api/inngest` - Webhook for Inngest background jobs

### Server Actions
- Resume operations via `actions/resume.js`
- Cover letter operations via `actions/cover-letter.js`
- Interview management via `actions/interview.js`
- Job search via `actions/job-result.js`
- Chat operations via `actions/chatbot-output.js`
- Dashboard data via `actions/dashboard.js`
- User management via `actions/user.js`


## 🎨 Components

### UI Component Library
All reusable components are in `components/ui/`:
- **Button** - Primary action button
- **Card** - Content container
- **Dialog** - Modal dialog
- **Input** - Text input field
- **Select** - Dropdown select
- **Tabs** - Tab navigation
- **Accordion** - Collapsible sections
- **Badge** - Labels and tags
- **Progress** - Progress indicators
- **Alert Dialog** - Alert modals
- **Radio Group** - Radio button group
- **Textarea** - Multi-line text input
- **Dropdown Menu** - Dropdown menus

### Special Components
- **Chatbot** - AI chat interface (`components/chatbot/`)
- **Glowing Effect** - Animated glow effect
- **Moving Border** - Animated border animation
- **Sparkles** - Sparkle animation
- **Lamp** - Lamp effect component
- **Text Hover Effect** - Interactive text effect



## 💾 Database

### Prisma ORM
- Schema defined in `prisma/schema.prisma`
- Migrations tracked in `prisma/migrations/`

### Database Migrations
Run migrations with:
```bash
npx prisma migrate dev
```

View your database:
```bash
npx prisma studio
```


## 🤖 Inngest Integration

Background job processing for:
- Resume generation
- Cover letter creation
- Interview evaluation
- Job matching

Configuration in `lib/inngest/`:
- `client.js` - Inngest client setup
- `function.js` - Job function definitions



## 🌙 Theming

### Theme Provider
Centralized theme management in `components/theme-provider.jsx`.

Supports:
- Light/Dark mode
- Custom color schemes
- Font customization


## 📝 Available Scripts

```bash
# Development
npm run dev          # Start dev server on http://localhost:3000

# Production
npm run build        # Build for production
npm run start        # Start production server

# Code Quality
npm run lint         # Run ESLint

# Database
npx prisma migrate  # Run migrations
npx prisma studio   # Open Prisma Studio
npx prisma generate # Generate Prisma client
```



## 🔐 Environment Variables

Create `.env.local` with:

```env
# Database
DATABASE_URL=

# Authentication
CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=

# Background Jobs
INNGEST_EVENT_KEY=
INNGEST_SIGNING_KEY=

# API
NEXT_PUBLIC_API_URL=http://localhost:3000

# Optional: AI/LLM Services
OPENAI_API_KEY=


## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.


## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.


## 🎯 Roadmap

- [ ] Mobile app version
- [ ] LinkedIn integration
- [ ] Job notifications
- [ ] Team collaboration features
- [ ] API documentation
- [ ] Video interview practice

---

**Made with ❤️ by Job Genie *

⭐ If you find this helpful, please star the repository!
