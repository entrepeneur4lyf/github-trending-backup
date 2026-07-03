```markdown
# github-trending-backup Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development conventions and workflows used in the `github-trending-backup` Go repository. You'll learn about file naming, import/export styles, commit message patterns, and how to structure and run tests. This guide is ideal for contributors aiming for consistency and maintainability in Go projects.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `githubBackup.go`, `trendingFetcher.go`

### Import Style
- Use **relative imports** within the module.
  - Example:
    ```go
    import (
        "github-trending-backup/utils"
        "github-trending-backup/models"
    )
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In trendingFetcher.go
    package trending

    func FetchTrendingRepos() ([]Repo, error) {
        // implementation
    }
    ```

### Commit Messages
- Use **conventional commit** style.
- Prefix with `build` for build-related changes.
- Keep commit messages concise (average ~55 characters).
  - Example:  
    ```
    build: update Go version in CI workflow
    ```

## Workflows

### Build the Project
**Trigger:** When you want to compile the codebase.
**Command:** `/build`

1. Open your terminal in the project root.
2. Run:
    ```sh
    go build ./...
    ```
3. The compiled binaries will be available in the current directory.

### Run Tests
**Trigger:** Before pushing changes or verifying functionality.
**Command:** `/test`

1. Open your terminal in the project root.
2. Run:
    ```sh
    go test ./...
    ```
3. Review the output for any failed tests.

### Add a New Feature or Fix
**Trigger:** When implementing a new feature or fixing a bug.
**Command:** `/feature`

1. Create a new branch for your work.
2. Follow file naming and export conventions.
3. Write or update tests in corresponding `*.test.*` files.
4. Commit changes using the conventional commit style.
5. Push your branch and open a pull request.

## Testing Patterns

- Test files follow the pattern: `*.test.*`
  - Example: `githubBackup.test.go`
- Testing framework is not explicitly specified; use Go's built-in `testing` package.
  - Example:
    ```go
    // githubBackup.test.go
    package githubbackup

    import "testing"

    func TestBackup(t *testing.T) {
        // test implementation
    }
    ```

## Commands
| Command   | Purpose                                      |
|-----------|----------------------------------------------|
| /build    | Compile the project                          |
| /test     | Run all tests                                |
| /feature  | Start a new feature or bugfix workflow       |
```
