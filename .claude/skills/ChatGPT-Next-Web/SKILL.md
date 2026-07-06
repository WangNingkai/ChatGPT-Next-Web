```markdown
# ChatGPT-Next-Web Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns, coding conventions, and common workflows for contributing to the ChatGPT-Next-Web project. The repository is primarily written in TypeScript, with a strong focus on additive changes, clear documentation, and robust unit testing. The project uses conventional commit messages and emphasizes maintainability and discoverability through consistent file organization and documentation practices.

## Coding Conventions

- **File Naming:**  
  Use kebab-case for all file names.
  ```
  // Good
  user-profile.ts
  chat-history.test.ts

  // Bad
  UserProfile.ts
  chatHistoryTest.ts
  ```

- **Import Style:**  
  Use relative imports for modules within the project.
  ```typescript
  import { fetchUser } from './user-service';
  ```

- **Export Style:**  
  Prefer named exports over default exports.
  ```typescript
  // Good
  export function fetchUser() { ... }

  // Bad
  export default function fetchUser() { ... }
  ```

- **Commit Messages:**  
  Follow the conventional commit format.  
  Prefixes like `test:` and `docs:` are common.
  ```
  test: add unit tests for token parser
  docs: document OPENAI_API_KEY in env template
  ```

## Workflows

### Add Unit Test for Helper
**Trigger:** When you want to add or improve unit test coverage for a helper or utility function.  
**Command:** `/add-unit-test helper-name`

1. Identify a helper or utility function that lacks test coverage.
2. Create a new test file in the `test/` directory, named after the helper (e.g., `test/helper-name.test.ts`).
3. Write focused, additive unit tests covering all relevant branches and cases.
4. Do not modify or remove existing files.
5. Run tests locally (e.g., `yarn test:ci`) to ensure they pass.
6. Commit the new test file with a descriptive message.

**Example:**
```typescript
// test/token-parser.test.ts
import { parseToken } from '../utils/token-parser';

describe('parseToken', () => {
  it('should parse a valid token', () => {
    expect(parseToken('abc.def.ghi')).toBeTruthy();
  });
});
```

### Document Env Var in Template
**Trigger:** When you need to document an environment variable used in the codebase but missing from `.env.template`.  
**Command:** `/document-env-var VAR_NAME`

1. Identify an environment variable in the code (e.g., in `app/config/server.ts`) that is not in `.env.template`.
2. Add the variable to `.env.template` with a descriptive comment.
3. Ensure the comment matches documentation elsewhere (e.g., `README`).
4. Commit the change with a descriptive message.

**Example:**
```env
# OPENAI_API_KEY: Your OpenAI API key for authentication
OPENAI_API_KEY=
```

### Merge Pull Request for Additive Test or Doc
**Trigger:** When merging a PR that adds a new unit test file or documents an environment variable.  
**Command:** `/merge-additive-change PR_NUMBER`

1. Review the PR for a new, focused test or documentation addition.
2. Ensure the PR only adds the new file and does not modify existing files (except `.env.template` for docs).
3. Merge the PR with a summary message referencing the added test or documentation.

## Testing Patterns

- **Testing Framework:**  
  Jest is used for unit testing.

- **Test File Pattern:**  
  Test files are placed in the `test/` directory and named with the pattern `*.test.ts`.
  ```
  test/
    token-parser.test.ts
    api-client.test.ts
  ```

- **Test Example:**
  ```typescript
  // test/math-utils.test.ts
  import { add } from '../utils/math-utils';

  describe('add', () => {
    it('adds two numbers', () => {
      expect(add(2, 3)).toBe(5);
    });
  });
  ```

## Commands

| Command                      | Purpose                                                     |
|------------------------------|-------------------------------------------------------------|
| /add-unit-test helper-name   | Add a focused unit test file for a helper or utility        |
| /document-env-var VAR_NAME   | Document an environment variable in `.env.template`         |
| /merge-additive-change PR_NUMBER | Merge a PR that adds a new test or env var documentation |
```
