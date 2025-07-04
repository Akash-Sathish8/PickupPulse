# PickupPulse - Real-time Sports Court Finder

## Overview

PickupPulse is a modern web application that helps users find and check into nearby sports courts (basketball and soccer) in real-time. The app features live player tracking, geolocation services, and real-time updates via WebSocket connections.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management
- **UI Framework**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables
- **Map Integration**: Leaflet for interactive maps
- **Build Tool**: Vite with hot module replacement

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ES modules
- **Real-time Communication**: WebSocket server for live updates
- **Development**: tsx for TypeScript execution in development

### Database Architecture
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Database**: PostgreSQL (configured for Neon serverless)
- **Schema**: Shared between client and server via `shared/schema.ts`
- **Migrations**: Drizzle Kit for database migrations

## Key Components

### Core Entities
1. **Users**: Anonymous user management with unique IDs
2. **Courts**: Sports venues with geolocation data
3. **Checkins**: Real-time player check-ins/check-outs
4. **Notifications**: User alerts for game formation

### Frontend Components
- **MapView**: Interactive Leaflet map with court markers
- **CourtList**: Sortable list of nearby courts
- **SportFilter**: Filter courts by sport type (all/basketball/soccer)
- **CheckInModal**: Modal for checking into courts
- **StatsPanel**: Real-time activity statistics
- **NotificationPanel**: User notification management

### Backend Services
- **Storage Layer**: Abstracted storage interface with memory implementation
- **WebSocket Handler**: Real-time client communication
- **REST API**: Standard HTTP endpoints for CRUD operations

## Data Flow

1. **User Initialization**: Anonymous user created on first visit
2. **Location Services**: Browser geolocation API for user positioning
3. **Real-time Updates**: WebSocket connection for live court data
4. **Check-in Process**: Modal-based check-in with sport selection
5. **Map Visualization**: Dynamic markers showing player counts
6. **Notifications**: Alert system for game formation

## External Dependencies

### Core Libraries
- **React Ecosystem**: React, React DOM, TanStack Query
- **UI Components**: Radix UI primitives, Lucide React icons
- **Maps**: Leaflet with TypeScript definitions
- **Validation**: Zod for schema validation
- **Styling**: Tailwind CSS, class-variance-authority
- **Forms**: React Hook Form with resolvers

### Development Tools
- **Build**: Vite with React plugin
- **TypeScript**: Full-stack type safety
- **Linting**: TSC for type checking
- **Hot Reload**: Vite HMR and runtime error overlay

### Database Stack
- **Drizzle ORM**: Type-safe database operations
- **Neon Database**: Serverless PostgreSQL
- **Connection Pooling**: Built-in with Neon serverless

## Deployment Strategy

### Development Environment
- **Command**: `npm run dev` - Starts development server with tsx
- **Hot Reload**: Vite development server with React HMR
- **Port**: 5000 (configured in .replit)
- **Database**: Connected via DATABASE_URL environment variable

### Production Build
- **Frontend**: `vite build` - Optimized client bundle
- **Backend**: `esbuild` - Bundled server with external packages
- **Static Assets**: Served from `dist/public`
- **Start Command**: `npm start` - Production server

### Replit Configuration
- **Modules**: Node.js 20, Web, PostgreSQL 16
- **Deployment**: Autoscale deployment target
- **Port Mapping**: Internal 5000 → External 80
- **Environment**: DATABASE_URL required for PostgreSQL connection

## Changelog
```
Changelog:
- June 20, 2025. Initial setup
- June 20, 2025. Added three major features:
  * Address search functionality for finding courts by location
  * Bookmark system for users to save favorite courts
  * Admin court creation tool for adding new basketball/soccer courts
- June 20, 2025. Implemented GPS-based auto check-in/out system:
  * Continuous location monitoring (30-60 second intervals)
  * Automatic check-in when within 30 meters of registered courts
  * Auto check-out after 45 minutes of inactivity or leaving area
  * Background mode support with notification permissions
  * Real-time location accuracy display and status tracking
```

## User Preferences
```
Preferred communication style: Simple, everyday language.
```