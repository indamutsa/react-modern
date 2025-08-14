# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Build and Development
- `npm run dev` - Start development server with Vite and HMR
- `npm run build` - Build for production (runs TypeScript compiler then Vite build)
- `npm run preview` - Preview production build locally
- `npm run lint` - Run ESLint for code linting

### Testing
Note: Testing configuration files exist (jest.config.js, vitest.config.ts) but appear to be empty placeholders. Verify testing setup before running tests.

## Project Architecture

This is a React + TypeScript + Vite application with a feature-based architecture:

### Core Structure
- **Feature-based organization**: Code is organized by features in `src/features/` with each feature containing its own components, hooks, services, and store
- **Context-based state management**: Uses React Context for state management (located in `src/contexts/`)
- **Shared utilities**: Common hooks, components, and utilities in respective directories

### Key Directories
- `src/features/` - Feature modules (todos, analytics, collaboration, notifications)
  - Each feature contains: components/, hooks/, services/, store/, types.ts
- `src/contexts/` - React Context providers for global state
- `src/components/` - Reusable UI components organized by category (ui/, forms/, layout/, charts/)
- `src/hooks/` - Custom React hooks for common functionality
- `src/services/` - External service integrations (API, WebSocket, analytics, etc.)
- `src/store/` - Redux/state management setup with middleware
- `src/utils/` - Utility functions and constants

### State Management Pattern
The app uses a hybrid approach:
- React Context for global state management
- Individual feature stores for complex state logic
- Custom hooks for feature-specific logic encapsulation

### Component Architecture
- UI components are organized in `src/components/ui/` with a barrel export pattern
- Form components are separated in `src/components/forms/`
- Layout components provide structure in `src/components/layout/`
- Feature-specific components live within their respective feature directories

## Development Notes

- Uses Vite for fast development and building
- TypeScript configuration uses project references (tsconfig.app.json, tsconfig.node.json)
- ESLint configured with TypeScript, React hooks, and React refresh plugins
- No custom development rules or Cursor/Copilot configurations found