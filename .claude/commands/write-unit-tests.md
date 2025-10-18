---
allowed-tools: Grep, Read, byterover-retrieve-knowledge, byterover-store-knowledge, Bash, Vitest, TodoWrite, Glob
---

# Write Unit Tests Command

Automate and accelerate the process of writing comprehensive unit tests, adhering to the project's structure, naming conventions, and test best practices.

## Instructions

### 1. **Preparation**
  - Identify target file(s) or modules for which unit tests are to be written (`--target <files|dirs>`, wildcards supported).
  - Ensure any dependencies or related interfaces are accessible.
  - Optionally, specify testing focus (e.g., coverage for edge cases, error handling, interface compliance).

### 2. **Context Gathering**
  - Use `byterover-retrieve-knowledge` to reference:
    - Existing unit tests and naming conventions
    - Common patterns for test mocks/stubs or fixtures
    - Project standards for colocating tests (`__test__` folders, filename pattern: `<feature>.test.ts`)
    - Any reusable test utilities or setup logic
  - Summarize important prior findings or reusable code applicable to tests.

### 3. **Unit Test Generation**
  - For each target:
    - Analyze all exported classes/functions.
    - For each, outline happy path and at least one error/edge condition.
    - Write new test(s) in a colocated `__test__` directory, using Vitest as the test runner and TypeScript as the language.
    - Use explicit, descriptive test names. Favor small, isolated tests over monolithic cases.
    - Adhere to the two-space indentation standard.
  - If corresponding test files already exist, add only missing coverage and avoid overwriting existing logic.

### 4. **Validation**
  - After generating tests:
    - Run `pnpm test` to ensure all generated tests pass (or are properly skipped if requiring external dependencies).
    - Collate Vitest output for reporting.

### 5. **Knowledge Storage**
  - Use `byterover-store-knowledge` to save:
    - New reusable test strategies, common mock setups, or utilities created
    - Edge cases and proven error-handling patterns
    - Solutions to challenging test coverage gaps

### 6. **Reporting**
  - Generate a summary of generated tests and coverage (which modules covered, which gaps remain).
  - Share actionable next steps or clarification requests if coverage was incomplete.

## Example Usage

```
.write-unit-tests --target src/core/tools/agent-tool.ts
.write-unit-tests --target "src/app/**/*.ts" --focus "error handling"
.write-unit-tests --target src/core/memory --update-only
```

## Notes

- Always prefer colocated `__test__` directories, matching `<feature>.test.ts` filenames.
- All new code should be committed before mass test generation.
- Consult previous test review findings using `byterover-retrieve-knowledge` for known gaps/pitfalls.
- Generated tests should be clear, isolated, and minimal; use comments sparingly.
- Follow two-space indentation, camelCase for functions/variables, PascalCase for test classes.


