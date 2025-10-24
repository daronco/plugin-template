# BigBlueButton Plugin Template

TypeScript/React plugin for BigBlueButton using the HTML Plugin SDK. This template provides a foundation for building interactive plugins that extend BigBlueButton's functionality.

## Do

- Use TypeScript strict mode with React 18 functional components
- Use styled-components for styling (already configured)
- Keep components small and focused in `src/components/`
- Use the BBB SDK hooks and components from `bigbluebutton-html-plugin-sdk`
- Follow the plugin registration pattern in `src/index.tsx`
- Use relative imports within the plugin
- Write tests for new components and functionality
- Check existing directory structure before creating new directories
- The boilerplate already has src/, src/components/, src/main/, src/types/, src/utils/ - use them

## Don't

- Do not use class-based React components (legacy pattern)
- Do not hardcode colors or spacing values (use design tokens)
- Do not add heavy dependencies without approval
- Do not modify the webpack config unless necessary
- Do not change the build output structure (`dist/` folder)
- Do not commit `node_modules/` or `dist/` folders

## Core Commands

### File-Scoped (Prefer These)
- Type check: `npx tsc --noEmit src/path/to/file.tsx`
- Lint: `npm run lint src/path/to/file.tsx`
- Lint fix: `npm run lint:fix src/path/to/file.tsx`

### Project-Wide (Use Sparingly)
- Install: `npm install`
- Build: `npm run build-bundle`
- Dev server: `npm start`
- Lint all: `npm run lint`
- Lint fix all: `npm run lint:fix`

## Project Structure

- `src/index.tsx` — Main plugin entry point (registers with BBB SDK)
- `src/components/` — React components (PascalCase naming)
- `src/main/` — Core plugin logic and utilities
- `src/types/` — TypeScript type definitions
- `src/utils/` — Helper functions
- `manifest.json` — Plugin metadata and configuration
- `webpack.config.js` — Build configuration
- `tsconfig.json` — TypeScript configuration

## Examples

### Good Patterns
- Plugin registration: `src/index.tsx`
- Component structure: `src/components/`
- Type definitions: `src/types/`
- Utility functions: `src/utils/`

### Avoid
- Large monolithic components
- Direct DOM manipulation (use React)
- Hardcoded styling values

## Testing

- Framework: Jest + React Testing Library (to be added)
- Run: `npm test` (when implemented)
- Coverage: 80% minimum target
- Always add tests for new components

## Git Workflow

- Branch: `feature/<description>` or `bugfix/<ticket-id>`
- Commits: `type(scope): description` (Conventional Commits)
- PR checklist:
  - [ ] TypeScript compiles without errors
  - [ ] Lint passes
  - [ ] Build succeeds
  - [ ] Small, focused diff

## BBB Plugin Development

### Key Concepts
- **Plugin Registration**: Use `PluginApi.register()` in `src/index.tsx`
- **UI Components**: Access BBB UI via SDK hooks and components
- **Event Handling**: Listen to BBB events and user interactions
- **State Management**: Use React hooks for component state
- **Styling**: Use styled-components for component-specific styles

### SDK Integration
- Import from `bigbluebutton-html-plugin-sdk`
- Use provided hooks: `usePluginApi`, `usePluginData`
- Access BBB context through plugin API
- Follow SDK patterns for component integration

## Safety Rules

### Allowed
- Read files, type check, lint single files
- Create new components in `src/components/`
- Add utility functions to `src/utils/`
- Update type definitions in `src/types/`

### Ask First
- Adding new dependencies to `package.json`
- Modifying webpack configuration
- Changing the plugin registration pattern
- Modifying the build output structure

## When Stuck
- Check the BBB Plugin SDK documentation
- Look at existing components for patterns
- Ask clarifying questions about requirements
- Propose a plan before large changes
- Keep changes minimal and reversible
