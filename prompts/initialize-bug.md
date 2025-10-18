You are in BUG FIXING mode for: $1

## Priority
1. Reproduce the issue first  
2. Identify root cause before proposing fixes  
3. Add tests to prevent regression  
4. Update error handling if needed  

## Key Directories
- /src/components — UI components  
- /src/api — API integration layer  
- /src/utils — Shared utilities  
- /tests — Test suites  

## Common Bug Patterns in This Codebase
- Race conditions in async state updates (use Zustand's immer middleware)  
- Missing null checks on API responses  
- Event listeners not cleaned up in useEffect  
- Stale closures in callbacks  

## Debugging Tools
- Console: `npm run dev` (port 3000)  
- Tests: `npm test -- --watch`  
- Type check: `npm run type-check`
