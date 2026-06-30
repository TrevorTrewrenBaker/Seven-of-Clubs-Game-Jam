# Seven of Clubs Game Jam Portfolio: High-Performance Web Application

> A scalable, server-side rendered (SSR) web application engineered for the Seven of Clubs game jam, demonstrating mastery of the modern Vue 3 ecosystem and enterprise-grade architecture.

![Tech Stack](https://img.shields.io/badge/Vue-3.5-4FC08D?logo=vue.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?logo=typescript)
![Build Tool](https://img.shields.io/badge/Vite-5.0-646CFF?logo=vite)
![Testing](https://img.shields.io/badge/Test-Vitest+-32CD32?logo=vitest)

## Project Overview
This submission is a high-performance web application built to demonstrate architectural proficiency in the Vue 3 ecosystem. The project leverages an **NX monorepo** to enforce strict type safety, modularity, and scalability across complex game logic and UI components. Designed for speed and reliability, the application ensures sub-second load times and optimal SEO performance for a global audience.

## Architecture & Technical Stack
*   **Core Framework**: Vue 3 with **Server-Side Rendering (SSR)** for optimized initial page loads and search engine visibility.
*   **Language**: **TypeScript** with `strict: true` configuration, eliminating `any` types and enforcing compile-time safety.
*   **Build System**: **Vite** configured for rapid hot-module replacement (HMR) and optimized production bundling.
*   **State Management**: **Pinia** for reactive local state, ensuring predictable data flow and easy debugging.
*   **Data Fetching**: **TanStack Query** for efficient server-state caching, automatic refetching, and type-safe asynchronous data handling.
*   **Styling**: **Tailwind CSS** for utility-first, responsive, and accessible UI design.
*   **Monorepo Structure**: **NX** used to manage shared libraries, enforce architectural boundaries, and streamline CI/CD pipelines.

## Key Features & Implementation
*   **Scalable Monorepo Architecture**: Designed an **NX monorepo** structure to unify frontend logic, shared utilities, and testing configurations, reducing build times and ensuring type consistency across the codebase.
*   **Robust Data Layer**: Integrated **Pinia** for local state and **TanStack Query** for server-state synchronization, reducing redundant API calls and ensuring real-time data accuracy.
*   **Type-Safe Game Logic**: 
    *   Implemented **Discriminated Unions** for all game events (e.g., `PlayerDamage`, `LevelComplete`), ensuring exhaustive handling of state transitions and eliminating runtime logic errors.
    *   Engineered **Generic Components** for reusable UI elements (e.g., `InventorySlot<T>`, `Card<T>`), allowing a single component to safely handle diverse data types without `any`.
*   **Comprehensive Testing Suite**:
    *   **Unit & Integration**: **Vitest** for rapid, isolated logic testing with full TypeScript inference.
    *   **End-to-End (E2E)**: **Playwright** for full browser automation, validating critical user flows and cross-device compatibility.
*   **Responsive & Accessible UI**: Built a mobile-first interface using **Tailwind CSS**, adhering to **WCAG** accessibility standards to ensure intuitive interaction across all devices.

## Testing Strategy
The project follows a "shift-left" testing philosophy to catch issues early:
1.  **Vitest**: Used for unit testing business logic and integration testing of Pinia stores and composables.
2.  **Playwright**: Employed for E2E browser automation to simulate real-world user journeys (e.g., game submission, dashboard navigation).
3.  **Coverage**: Maintained >90% code coverage to guarantee a bug-free deployment.

## CI/CD & Automation
Engineered a **GitHub Actions** workflow to automate the build, test, and deployment lifecycle, ensuring code quality and rapid iteration during the 5-day game jam sprint.

### Pipeline Strategy
*   **Automated Quality Gates**: Configured the workflow to run **Vitest** (unit) and **Playwright** (E2E) tests on every pull request, automatically blocking merges if tests fail.
*   **Monorepo Optimization**: Leveraged **Nx**'s `affected` commands to build and test **only changed projects**, significantly reducing feedback loops compared to full repository builds.
*   **Instant Deployment**: Set up automated deployment to **GitHub Pages** upon merging to `main`, enabling real-time stakeholder feedback and demo sharing.
*   **Secure Configuration**: Managed API keys and environment variables using **GitHub Secrets**, ensuring sensitive data never entered the codebase.

### Workflow Flow
`Push/PR` → `Run Tests` → `Build Affected Apps` → `Deploy to Production`

> **Impact**: This automation eliminated manual deployment steps, allowing the team to focus entirely on game mechanics and UI polish while maintaining a stable, production-ready build at all times.
