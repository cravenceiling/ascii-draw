## Important

- Run `bun run typecheck` and `bun run lint` after making changes and fix any errors.
- Don't run `bun run build`, `bun run start` or `bun run preview` until you're ready to commit.
- Don't run `bun run dev`, always assume the dev server is already running.


## Code Style Guidelines

### File Naming
- Use **kebab-case** for all filenames: `use-canvas.ts`, `ascii-grid.tsx`
- Components: PascalCase exports, kebab-case files
- Hooks: `use-[name].ts`
- Utils: `[name]-utils.ts`

### TypeScript
- **Strict typing required** - never use `any`
- Use `type` for type imports: `import type { Foo } from "@/types"`
- Export types from `@/types/index.ts`
- Prefer interfaces for object shapes
- Use const assertions for constants: `as const`

### React Patterns
- Use functional components with hooks
- Memoize expensive components with `React.memo`
- Use `useCallback` for event handlers passed to children
- Use `useMemo` for expensive computations
- Use refs for mutable values that shouldn't trigger re-renders
- CSS transforms over absolute positioning for animations

Also, use React Best Practices skill when possible.

### Error Handling
- Prefer early returns over nested conditionals
- Validate array bounds before accessing
- Use functional state updates for race condition safety

## Key Conventions

1. **Performance**: This is a drawing app - optimize for performance
   - Memoize grid rendering
   - Use refs for mouse tracking (not state)
   - Minimize re-renders during drag operations

2. **State Management**:
   - Local state with `useState` for UI
   - Custom hooks for complex logic
   - `useHistory` hook for undo/redo

3. **Canvas Coordinates**:
   - Use `getBoundingClientRect()` for coordinate conversion
   - Account for zoom and pan offsets
   - Grid coordinates are integer-based

4. **ASCII Drawing**:
   - Character dimensions: 9x17 pixels
   - Grid-based rendering (not SVG/Canvas)
   - Support live preview during drag

## Do Not

- Use `any` type
- Use npm/yarn/pnpm (use bun)
- Create files with camelCase or PascalCase names
- Add unnecessary dependencies
- Use CSS-in-JS (use Tailwind)
- Modify shadcn component internals
