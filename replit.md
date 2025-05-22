# CodeQuest - Interactive Coding Challenge Platform

## Overview

CodeQuest is a gamified coding education platform that presents programming challenges as an interactive space adventure. Users progress through different mission categories, solve coding problems, earn XP, and unlock new challenges in a visually engaging cyberpunk-themed interface.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Routing**: Wouter for client-side routing
- **Styling**: Tailwind CSS with custom cyberpunk theme
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Animations**: Framer Motion for smooth transitions and interactive elements
- **3D Graphics**: Three.js for particle effects and visual enhancements
- **State Management**: TanStack Query for server state and local React state for UI

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database ORM**: Drizzle ORM
- **Database**: PostgreSQL (configured for Neon serverless)
- **Session Management**: Express sessions with PostgreSQL store
- **API Design**: RESTful endpoints for missions, user progress, and code execution

### Build System
- **Development**: Vite for fast development server and HMR
- **Production Build**: Vite for frontend, esbuild for backend bundling
- **TypeScript**: Strict type checking across full stack

## Key Components

### Frontend Components
1. **WelcomeScreen**: Landing page with animated logo and space theme
2. **UniverseMap**: Mission selection interface showing different categories as space locations
3. **MissionChamber**: Code editor and challenge interface for solving problems
4. **TopNavBar**: User stats display (XP, energy) and navigation
5. **ThreeScene**: Particle effects and 3D visual elements
6. **NotificationSystem**: Toast notifications for user feedback

### Backend Components
1. **Mission System**: CRUD operations for coding challenges
2. **Progress Tracking**: User completion status and attempt history
3. **Code Execution**: API endpoints for running and validating user code
4. **User Management**: Basic user stats and preferences

### Database Schema
- **users**: User profiles with XP, energy, completed missions, and badges
- **missions**: Challenge definitions with instructions, tests, and metadata
- **userMissionProgress**: Individual progress tracking per user/mission

## Data Flow

1. **Mission Loading**: Frontend fetches available missions grouped by category
2. **Code Execution**: User submits code → Backend validates → Returns results with test outcomes
3. **Progress Updates**: Successful completion updates user stats and mission progress
4. **State Synchronization**: TanStack Query manages server state caching and updates

### Mission Categories
- **Arrays**: Basic data structure manipulation
- **Recursion**: Recursive problem solving
- **Algorithms**: Advanced algorithmic challenges

## External Dependencies

### Frontend Libraries
- **UI Framework**: React, Wouter for routing
- **Styling**: Tailwind CSS, Radix UI components
- **Animations**: Framer Motion
- **3D Graphics**: Three.js
- **HTTP Client**: TanStack Query with fetch API
- **Form Handling**: React Hook Form with Zod validation

### Backend Libraries
- **Server**: Express.js
- **Database**: Drizzle ORM with PostgreSQL driver (@neondatabase/serverless)
- **Session**: connect-pg-simple for PostgreSQL session store
- **Validation**: Zod for runtime type checking

### Development Tools
- **Build**: Vite, esbuild
- **TypeScript**: Full stack type safety
- **Database Migrations**: Drizzle Kit

## Deployment Strategy

### Development Environment
- **Local Server**: Runs on port 5000 with Vite dev server
- **Database**: PostgreSQL via environment variable DATABASE_URL
- **Hot Reload**: Vite HMR for frontend, tsx for backend development

### Production Build
- **Frontend**: Vite builds to `dist/public`
- **Backend**: esbuild bundles server to `dist/index.js`
- **Database**: Drizzle migrations via `npm run db:push`
- **Static Serving**: Express serves built frontend assets

### Replit Configuration
- **Modules**: Node.js 20, PostgreSQL 16, web environment
- **Build Command**: `npm run build`
- **Start Command**: `npm run start`
- **Port Mapping**: Internal 5000 → External 80

### Key Architectural Decisions

1. **Monorepo Structure**: Single repository with `client/`, `server/`, and `shared/` directories for type sharing
2. **TypeScript First**: Strict typing across all layers with shared schema definitions
3. **Component-Driven UI**: Modular React components with consistent design system
4. **Database-First**: Drizzle schema as source of truth with type generation
5. **Gamification**: XP system, energy mechanics, and visual progression to enhance engagement
6. **Code Execution Security**: Server-side validation of user code submissions
7. **Responsive Design**: Mobile-first approach with Tailwind breakpoints
8. **Performance**: Client-side caching with TanStack Query and optimized bundle sizes