```markdown
# adk-integrator-frontend Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill documents the core development conventions and workflows for the `adk-integrator-frontend` TypeScript codebase. It covers file structure, code style, commit patterns, and testing approaches to ensure consistency and maintainability across the project.

## Coding Conventions

### File Naming
- Use **kebab-case** for all file names.
  - Example: `user-profile.ts`, `data-fetcher.test.ts`

### Import Style
- Use **relative imports** for modules within the codebase.
  - Example:
    ```typescript
    import { fetchData } from './utils/data-fetcher';
    ```

### Export Style
- Use **named exports** for all modules.
  - Example:
    ```typescript
    // In data-fetcher.ts
    export function fetchData() { ... }
    ```

### Commit Messages
- Follow **Conventional Commits** with the `feat` prefix for features.
  - Example:
    ```
    feat: add user profile page
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature or module  
**Command:** `/feature-development`

1. Create a new file using kebab-case naming.
2. Implement the feature using TypeScript.
3. Use relative imports to include dependencies.
4. Export functions or components using named exports.
5. Write or update corresponding test files (`*.test.ts`).
6. Commit changes using the conventional commit format:
   ```
   feat: <short description>
   ```

### Testing
**Trigger:** When validating code changes  
**Command:** `/run-tests`

1. Ensure test files follow the `*.test.*` naming pattern.
2. Run the test suite using the project's test runner (framework not specified).
3. Review test results and fix any failing tests.

## Testing Patterns

- Test files are named with the `*.test.*` pattern, e.g., `user-profile.test.ts`.
- The specific testing framework is not detected; refer to project documentation or package.json for details.
- Place tests alongside the modules they cover, using relative imports.

  Example:
  ```typescript
  // user-profile.test.ts
  import { getUserProfile } from './user-profile';

  test('returns correct user profile', () => {
    // test implementation
  });
  ```

## Commands
| Command              | Purpose                                   |
|----------------------|-------------------------------------------|
| /feature-development | Start a new feature following conventions |
| /run-tests           | Run the test suite                        |
```
