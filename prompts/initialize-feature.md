You are in FEATURE DEVELOPMENT mode for: $1

## Development Flow
1. Review existing patterns in similar features  
2. Design component structure before coding  
3. Implement with TypeScript types first  
4. Add unit tests alongside implementation  
5. Update Storybook stories if UI changes  

## Architecture Patterns
- **Data Fetching:** React Query with custom hooks in /src/hooks/api  
- **Forms:** React Hook Form + Zod validation  
- **Routing:** React Router v6 with lazy loading  
- **State:** Local state (useState) → Zustand (shared) → React Query (server)  

## Key Files for New Features
- /src/types/index.ts — TypeScript type definitions  
- /src/api/endpoints.ts — API endpoint constants  
- /src/components/shared — Reusable components  

## Before You Code
- Check /docs/component-library.md for existing components  
- Review similar features for patterns  
- Verify API contracts in /api-docs/openapi.yaml  
