# AI Development Rules

This document provides guidelines for the AI assistant to follow when developing and modifying this web application.

## Tech Stack

This is a video editor application built with the following technologies:

-   **Framework**: React with Vite for a fast development experience.
-   **Language**: TypeScript for type safety and improved developer experience.
-   **Styling**: Tailwind CSS for utility-first styling, configured with a custom theme.
-   **UI Components**: A combination of custom components and UI primitives from `shadcn/ui` and Radix UI.
-   **State Management**: Zustand is used for global state management, complemented by a custom event-driven state manager (`@designcombo/state`).
-   **Routing**: `react-router-dom` is used for all client-side routing.
-   **Video & Animation**: The core video editing and playback functionality is powered by Remotion. UI animations are handled by Framer Motion.
-   **Icons**: `lucide-react` is the designated library for all icons.
-   **Forms**: `react-hook-form` and `zod` are used for building and validating forms.

## Library Usage Rules

To maintain consistency and code quality, please adhere to the following rules:

1.  **UI Components**:
    -   When building UI, prioritize using existing components from `src/components/ui`.
    -   For new components, follow the established pattern of using Radix UI primitives styled with Tailwind CSS. Do not introduce new UI libraries.

2.  **Styling**:
    -   All styling **must** be done using Tailwind CSS utility classes.
    -   Use the `cn` utility function from `src/lib/utils.ts` to conditionally apply classes.
    -   Do not write custom CSS files unless absolutely necessary for complex, global styles.

3.  **State Management**:
    -   For global application state, use the existing Zustand stores (e.g., `useStore`, `useLayoutStore`).
    -   For component-level state, use React's built-in `useState` and `useReducer` hooks.

4.  **Icons**:
    -   All icons must be imported from the `lucide-react` package.
    -   Use the pre-configured `Icons` object in `src/components/shared/icons.tsx` for consistency.

5.  **Forms**:
    -   Use `react-hook-form` for handling form state and submissions.
    -   Use `zod` for all schema definition and validation.

6.  **Routing**:
    -   Define all application routes in `src/main.tsx` using the `createBrowserRouter` function from `react-router-dom`.

7.  **File Structure**:
    -   **Features**: Place all major features (like the editor) in the `src/features` directory.
    -   **Components**: Reusable components should be placed in `src/components`. UI primitives are in `src/components/ui`.
    -   **Utilities**: General utility functions are located in `src/lib/utils.ts`.

By following these rules, we can ensure the codebase remains clean, consistent, and easy to maintain.