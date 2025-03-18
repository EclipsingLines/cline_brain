# System Patterns: [Project Name]

## Architecture Overview

### Core Components
1. [Component 1]
   - [Description and responsibility]
   - [Relationship to other components]
   - [Key design decisions]

2. [Component 2]
   - [Description and responsibility]
   - [Relationship to other components]
   - [Key design decisions]

3. [Component 3]
   - [Description and responsibility]
   - [Relationship to other components]
   - [Key design decisions]

### Data Flow
- [High-level description of how data flows through the system]
- [Key data transformation points]
- [Critical path description]

## Design Patterns

1. [Pattern 1]
   - [Description and purpose]
   - [Where it's applied]
   - [Benefits]

2. [Pattern 2]
   - [Description and purpose]
   - [Where it's applied]
   - [Benefits]

3. [Pattern 3]
   - [Description and purpose]
   - [Where it's applied]
   - [Benefits]

## Component Relationships

1. [Component 1] → [Component 2]
   - [Description of relationship]
   - [API/interface details]
   - [Error handling expectations]

2. [Component 2] → [Component 3]
   - [Description of relationship]
   - [API/interface details]
   - [Error handling expectations]

## Go Code Styling

### Project Organization

1. Project Structure
   - `main.go` should be kept as small as possible, serving only as the application entrypoint
   - All packages should be placed under the `./pkg/` directory
   - Command-line tools should be in `./cmd/`
   - Use `./internal/` for packages that should not be imported by other projects
   - Configuration in `./config/`
   - Tests should be in the same package as the code they test (e.g., `foo_test.go` alongside `foo.go`)

2. File Organization
   - Break up package files into multiple smaller files, keeping each under 300 lines
   - Group small utility, helper, and setup functions in a `util.go` file within each package
   - Name files according to their primary responsibility (e.g., `server.go`, `handler.go`, `client.go`)
   - Example package structure:
     ```
     pkg/service/
     ├── client.go      // Client setup and operations
     ├── handler.go     // Request handling logic
     ├── server.go      // Server initialization and configuration
     ├── model.go       // Data models and types
     └── util.go        // Small utility and helper functions
     ```

3. Function Organization
   - Each exported function must have a detailed comment explaining what it does
   - Example function documentation:
     ```go
     // ProcessRequest handles incoming requests by validating the input,
     // performing the required business logic, and returning a response.
     // It includes error handling for invalid inputs and processing failures.
     //
     // Parameters:
     //   - ctx: Context for the operation
     //   - req: The request to process
     //
     // Returns:
     //   - Response: The processed result
     //   - error: Any error encountered during processing
     func ProcessRequest(ctx context.Context, req *Request) (*Response, error) {
         // Implementation
     }
     ```

### Source Control Practices

1. Git Commit Strategy
   - Make frequent, small commits while coding to create recovery points
   - Each commit should represent a logical unit of work
   - Use descriptive commit messages with a clear structure:
     ```
     [Component] Brief description of change
     
     More detailed explanation if needed
     ```
   - Example commit messages:
     ```
     [API] Add pagination support to list endpoint
     
     Adds query parameters for page size and number with
     appropriate validation and documentation.
     ```
     ```
     [CLI] Fix error handling in config command
     
     Improves error messages when config file is invalid and adds
     validation for required fields.
     ```

2. Code Recovery with Git
   - Use git to recover accidentally deleted code:
     ```bash
     # Find the commit where code was deleted
     git log -p -- path/to/file.go
     
     # Recover specific file from a previous commit without affecting other files
     git checkout [commit-hash] -- path/to/file.go
     
     # For recovering just part of a file, use git blame to find the right commit
     git blame path/to/file.go
     
     # Then checkout that specific file and manually extract the needed parts
     git checkout [commit-hash] -- path/to/file.go
     ```
   - Consider using `git stash` to temporarily save changes when switching tasks:
     ```bash
     # Save current changes
     git stash save "description of changes"
     
     # List saved stashes
     git stash list
     
     # Apply a specific stash (keeping it in the stash list)
     git stash apply stash@{0}
     
     # Remove stash after applying it
     git stash pop
     ```

3. Branching Strategy
   - Use feature branches for new features or significant changes
   - Keep feature branches short-lived (1-5 days)
   - Regularly rebase feature branches on the main branch
   - Use pull requests for code review
   - Clean up branches after merging

### Formatting and Organization

1. Code Formatting
   - Use `go fmt` or `gofmt` for automatic formatting
   - Maintain 80-100 character line length where reasonable
   - Follow standard Go indentation (tabs, not spaces)
   - Run formatting before committing: `go fmt ./...`

2. Import Organization
   - Group imports in three distinct blocks:
     * Standard library
     * External dependencies
     * Internal project packages
   ```go
   import (
       "context"
       "fmt"
       "time"

       "github.com/example/external/package"
       "github.com/another/dependency"
       
       "github.com/your-org/your-project/pkg/logging"
   )
   ```
   - Use explicit import names when necessary to avoid collisions
   - Avoid dot imports (e.g., `import . "fmt"`)

3. Package Organization
   - Organize packages by functional domain, not by type
   - Keep package names short, clear, and descriptive
   - Avoid package name collisions with common libraries
   - Follow established package patterns:
     * cmd/[executable] - Command-line executables
     * pkg/[component] - Public library packages
     * internal/[component] - Private implementation packages

### Naming Conventions

1. General Naming
   - Use camelCase for private identifiers
   - Use PascalCase for exported identifiers
   - Avoid abbreviations except for common ones (e.g., HTTP, API, URL)
   - Be explicit and descriptive in naming

2. Package-Specific Naming
   - Types should have descriptive names that reflect their purpose
   - Methods should start with verbs that describe what they do
   - Constants should be ALL_CAPS with underscores
   - Interfaces should end with 'er' if they describe behavior (e.g., `Reader`, `Writer`, `Formatter`)

3. Variable Naming
   - Contextual variables: `ctx` for context.Context
   - Loop indices: `i`, `j`, etc., or descriptive names for complex loops
   - Error returns: `err`
   - Short-lived variables: short names are acceptable
   - Long-lived variables: descriptive names that explain purpose

### Error Handling Patterns

1. Standard Error Handling
   ```go
   if err != nil {
       // Log the error with context
       log.WithError(err).WithField("input", input).Error("operation failed")
       
       // Return with error
       return nil, fmt.Errorf("failed to process request: %w", err)
   }
   ```

2. Error Wrapping
   - Wrap errors with context using `fmt.Errorf("context: %w", err)`
   - Include relevant details when wrapping errors
   - Use error wrapping for operation context, not just message

3. Error Logging
   - Use structured logging with error fields:
     ```go
     log.WithError(err).WithField("requestID", req.ID).Error("failed to process request")
     ```
   - Include appropriate context in error logs
   - Use consistent verbosity levels

### Documentation Standards

1. Package Documentation
   - Add package documentation comments at the top of each package's primary file:
     ```go
     // Package handler implements HTTP handlers for the API endpoints.
     // It processes incoming requests, performs necessary validations,
     // and delegates to the appropriate service components.
     package handler
     ```

2. Type and Function Documentation
   - Document all exported types and functions with detailed comments
   - Include usage examples for complex functions
   - Document all parameters and return values
   ```go
   // ProcessItem processes an item according to the provided configuration.
   //
   // It validates the item, applies processing rules, and returns the
   // processed result. If validation fails or processing encounters an error,
   // it returns an appropriate error.
   //
   // Parameters:
   //   - ctx: Context for the operation
   //   - item: The item to process
   //   - config: Processing configuration options
   //
   // Returns:
   //   - result: The processed item result
   //   - error: Any error encountered during processing
   func ProcessItem(ctx context.Context, item *Item, config Config) (*Result, error) {
       // Implementation
   }
   ```

3. Implementation Comments
   - Add comments for complex or non-obvious code sections
   - Explain algorithm choices and design decisions
   - Document known limitations or edge cases

### Testing Patterns

1. Test Organization
   - Use table-driven tests for multiple test cases
   - Group related test cases
   - Name tests clearly: `TestFunctionName_Scenario`

2. Test Helpers
   - Create shared test fixtures and helpers
   - Use testing.T helpers for common assertions
   - Isolate test dependencies

3. Test Coverage
   - Aim for high test coverage on core business logic
   - Test error cases and edge conditions
   - Include integration tests for component interaction

## Best Practices

1. Resource Management
   - Use defer for cleanup operations
   - Close resources in the reverse order of acquisition
   - Implement io.Closer interface where appropriate
   - Consider using sync.Pool for frequently allocated resources

2. Security
   - Validate all user inputs
   - Use prepared statements for database queries
   - Implement proper authentication and authorization
   - Follow the principle of least privilege
   - Keep dependencies updated and scan for vulnerabilities

3. Performance
   - Profile before optimizing
   - Use buffered I/O operations
   - Consider connection pooling for external services
   - Implement caching where appropriate
   - Use concurrency with care and proper synchronization

4. Monitoring
   - Implement health checks
   - Expose metrics for monitoring
   - Use structured logging
   - Add tracingfor complex operations

5. Logging Pattern
   - Package-level logger initialization via logger.go
   - Shared logging setup across packages
   - Consistent logging interface
   - Example logging setup:
   ```go
   // logger.go in each package
   package mypackage

   import "github.com/project/pkg/logging"

   var log = logging.GetLogger("mypackage")
   ```
   - Usage pattern in package files:
   ```go
   log.Info("message")
   log.WithError(err).Error("error message")
   ```
   - Benefits:
     * Centralized logging configuration
     * Consistent logging format
     * Package-level logging control
     * Clean separation of concerns
     * Easy logging level management
