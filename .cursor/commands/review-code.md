---
allowed-tools: Read, Grep, Glob, byterover-retrieve-knowledge, byterover-store-knowledge
---

# Code Review Command

Facilitate comprehensive code reviews and improve code quality using both intelligent automation and human guidance.

## Instructions

### 1. **Preparation**
  - Specify the target file(s) or directories for review (wildcards supported).
  - Optionally provide review focus areas (e.g. bugs, security, style, performance, documentation, requirements).
  - Ensure all code is pushed/committed, and local changes are saved.

### 2. **Context Retrieval**
  - Use `byterover-retrieve-knowledge` to gather any prior reviews, common patterns, coding standards, or relevant architectural decisions for the target files.
  - Summarize related historical issues if available.

### 3. **Automated Analysis**
  - Analyze code for:
    - Style and formatting deviations (enforce lint and Prettier rules)
    - Common bugs or anti-patterns
    - Security vulnerabilities or unsafe practices
    - Use of deprecated or discouraged APIs
    - Test coverage gaps (identify untested logic)
    - Compliance with project/module boundaries and naming conventions
  - Collate diagnosis and highlight lines/snippets needing attention.

### 4. **Knowledge Storage**
  - Utilize `byterover-store-knowledge` to save reusable review patterns, custom checks added, and resolutions to non-trivial findings.

### 5. **Reporting**
  - Generate a review report including:
    - Summary of findings (categorized: bugs, style, etc.)
    - Inline example suggestions or corrections
    - References to documentation or previous solutions in the knowledge base
    - List of action items (with file/line references)
  - Optionally request clarification or further changes from the author.

### 6. **Manual & Collaborative Review (optional)**
  - If requested, facilitate a shared review session using suggested questions/prompts.
  - Support reviewer assignment and checklist validation for merges.

## Example Usage

```
.review-code --target src/core/memory --focus bugs,performance
.review-code --target "*.ts" --focus style,security
.review-code --target src/app/ui
```

## Notes

- This command is designed to accelerate and structure the code review process.
- Always leverage ByteRover MCP's knowledge base for guidance and knowledge transfer.
- All findings, suggestions, and improvements should be clearly actionable.
- Default to reviewing all new/modified files if targets are not specified.


