```markdown
# usecomputer Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and operational workflows for contributing to the `usecomputer` repository. The project is written in TypeScript (with Zig and C interop layers) and is designed for cross-platform, low-level system interaction. You’ll learn how to maintain code style, manage releases, update CI, extend platform support, and more.

## Coding Conventions

- **File Naming:** Use camelCase for file names.
  - Example: `nativeLib.ts`, `bridgeContract.test.ts`
- **Import Style:** Use relative imports.
  - Example:
    ```typescript
    import { doThing } from './lib'
    ```
- **Export Style:** Use named exports.
  - Example:
    ```typescript
    export function doThing() { /* ... */ }
    ```
- **Commit Messages:**  
  - Freeform, but commonly prefixed with `release:`, `fix:`, or `feat:`.
  - Example: `feat: add Linux ARM64 support`
- **Test Files:**  
  - Use `*.test.ts` naming.
  - Example: `bridgeContract.test.ts`

## Workflows

### Release Version Bump
**Trigger:** When releasing a new version of `usecomputer`  
**Command:** `/release-version-bump`

1. Update `CHANGELOG.md` with new release notes.
2. Update the version in `package.json`.
3. Commit changes with a message like:  
   ```
   release: usecomputer@X.Y.Z
   ```
4. Push to the repository to trigger CI and publish.

---

### CI Workflow Update
**Trigger:** When changing how CI builds, tests, or releases the project  
**Command:** `/ci-workflow-update`

1. Edit `.github/workflows/ci.yml` with the required changes.
2. Commit with a message describing the CI fix or enhancement, e.g.:  
   ```
   fix: update CI to run tests on Windows
   ```
3. Push to the repository to apply the new CI behavior.

---

### Feature Add C API
**Trigger:** When adding or enhancing C API support  
**Command:** `/feature-add-c-api`

1. Edit or create `zig/src/c_api.zig` for C API logic.
2. Edit or create `zig/include/usecomputer.h` for the C header.
3. Update `build.zig` to add/modify build targets for the C API.
4. Optionally, add or update `examples/screenshot.c` for usage examples.
5. Update `package.json` scripts if needed.
6. Update CI workflow (`.github/workflows/ci.yml`) to build and release C API artifacts.

---

### Remove Feature Across Stack
**Trigger:** When fully deprecating and removing a feature  
**Command:** `/remove-feature-across-stack`

1. Remove feature implementation from Zig source files (e.g., `zig/src/lib.zig`, `zig/src/main.zig`).
2. Remove related TypeScript bridge, types, and API code (e.g., `src/bridge.ts`, `src/lib.ts`, `src/native-lib.ts`, `src/types.ts`).
3. Remove or update related tests (e.g., `src/bridge-contract.test.ts`).
4. Update `package.json` if necessary.

---

### Add Platform Support
**Trigger:** When adding support for a new OS/architecture  
**Command:** `/add-platform-support`

1. Update `.github/workflows/ci.yml` to build/test the new platform.
2. Update `build.zig` and `scripts/build.ts` for new platform targets.
3. Update documentation (`README.md`, `AGENTS.md`) to mention new support.
4. Update `package.json` if needed.
5. Update Zig source files (`zig/src/lib.zig`) if platform-specific logic is required.

---

## Testing Patterns

- **Framework:** [vitest](https://vitest.dev/)
- **File Naming:** Tests are placed in files ending with `.test.ts`.
- **Example Test:**
  ```typescript
  import { describe, it, expect } from 'vitest'
  import { doThing } from './lib'

  describe('doThing', () => {
    it('should work correctly', () => {
      expect(doThing()).toBe(true)
    })
  })
  ```

## Commands

| Command                    | Purpose                                                      |
|----------------------------|--------------------------------------------------------------|
| /release-version-bump      | Prepare and publish a new release                            |
| /ci-workflow-update        | Modify GitHub Actions CI workflow                            |
| /feature-add-c-api         | Implement or update C API bindings and related artifacts     |
| /remove-feature-across-stack | Remove a feature from all layers of the stack               |
| /add-platform-support      | Add support for a new OS/architecture platform               |
```