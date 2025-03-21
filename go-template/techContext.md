# Technical Context: [Project Name]

## Technology Stack

### Core Technologies
1. Go (version [X.Y]+)
   - Primary implementation language
   - Standard library utilization
   - Go modules for dependency management

2. [Secondary Technology]
   - [Purpose in the project]
   - [Key features used]
   - [Version requirements]

3. [Tertiary Technology]
   - [Purpose in the project]
   - [Key features used]
   - [Version requirements]

### Dependencies

1. [Key Dependency 1]
   ```go
   [import path]
   ```
   - [Purpose in the project]
   - [Specific features used]
   - [Version constraints]

2. [Key Dependency 2]
   ```go
   [import path]
   ```
   - [Purpose in the project]
   - [Specific features used]
   - [Version constraints]

3. [Key Dependency 3]
   ```go
   [import path]
   ```
   - [Purpose in the project]
   - [Specific features used]
   - [Version constraints]

## Development Setup

### Prerequisites
1. Development Tools
   - Go [version]
   - [Tool 1]
   - [Tool 2]
   - [Tool 3]
   - [IDE/Editor of choice]

2. Environment Setup
   ```bash
   # Install required tools
   go install [tool1]@[version]
   go install [tool2]@[version]
   
   # Setup environment variables
   export [ENV_VAR1]=[value1]
   export [ENV_VAR2]=[value2]
   
   # Clone repository
   git clone [repository URL]
   cd [project directory]
   
   # Initialize dependencies
   go mod download
   ```

### Build Process
1. Building the Application
   ```bash
   go build -o [output name] [main file path]
   ```

2. Running Tests
   ```bash
   # Run tests with default verbosity
   go test ./...
   
   # Run tests with verbose output
   go test -v ./...
   
   # Run tests with coverage
   go test -cover ./...
   
   # Generate coverage report
   go test -coverprofile=coverage.out ./...
   go tool cover -html=coverage.out
   ```

3. Makefile Options (if applicable)
   ```bash
   # Build the application
   make build
   
   # Run tests
   make test
   
   # Clean build artifacts
   make clean
   
   # Build and run
   make run
   
   # Generate documentation
   make docs
   ```

## Deployment

### Container Deployment
1. Dockerfile Structure
   ```
   project/
   ├── Dockerfile
   ├── .dockerignore
   └── docker-compose.yml (if applicable)
   ```

2. Image Building
   ```bash
   # Build container image
   docker build -t [image name]:[tag] .
   
   # Run container locally
   docker run -p [host port]:[container port] [image name]:[tag]
   ```

3. Container Registry
   - Registry: [Registry name/URL]
   - Image naming convention: [convention details]
   - Tag strategy: [tag strategy]

### Cloud Deployment
1. [Cloud Provider]
   - Service: [Service name (e.g., GKE, ECS, App Engine)]
   - Region: [Primary deployment region]
   - Configuration: [Key configuration details]

2. Infrastructure as Code
   - Tool: [e.g., Terraform, Pulumi, CloudFormation]
   - Repository: [Repository location]
   - Apply process: [Process details]

### CI/CD Pipeline
1. [CI/CD Platform]
   - Repository: [Repository location]
   - Triggers: [When pipelines run]
   - Stages:
     * Build
     * Test
     * Deploy to Staging
     * Approval Gate
     * Deploy to Production

## Technical Constraints

1. Resource Limitations
   - Memory usage requirements
   - CPU usage expectations
   - Storage constraints
   - Network bandwidth considerations

2. Security Constraints
   - Authentication requirements
   - Authorization model
   - Data protection needs
   - Compliance requirements (if applicable)

3. Operational Constraints
   - Availability requirements
   - Backup and recovery needs
   - Monitoring requirements
   - Performance expectations

## Development Patterns

1. Code Organization
   ```
   ├── cmd/                   # Command-line applications
   │   └── [app name]/        # Main application entry point
   │       └── main.go        # Application entrypoint
   ├── pkg/                   # Public library packages
   │   ├── [component 1]/     # Component 1 implementation
   │   └── [component 2]/     # Component 2 implementation
   ├── internal/              # Private implementation packages
   │   ├── [component 3]/     # Internal component 1
   │   └── [component 4]/     # Internal component 2
   ├── api/                   # API definitions (proto files, OpenAPI specs)
   ├── web/                   # Web assets (if applicable)
   ├── configs/               # Configuration files
   ├── scripts/               # Helper scripts
   └── test/                  # Integration and end-to-end tests
   ```

2. Logging and Telemetry
   - Logging library: [library name]
   - Log format: [format details]
   - Log levels: [debug, info, warn, error, etc.]
   - Telemetry solution: [solution name if applicable]

3. Testing Strategy
   - Unit tests for all packages
   - Integration tests for component interaction
   - End-to-end tests for critical flows
   - Performance testing for key operations
   - Testing tools and libraries:
     * [Tool/library 1]
     * [Tool/library 2]

4. Documentation
   - API documentation: [godoc, custom solution, etc.]
   - Architecture documentation: [location/format]
   - Operation guides: [location/format]
   - Developer guides: [location/format]

5. Configuration Management
   - Configuration format: [YAML, JSON, TOML, etc.]
   - Environment variable usage
   - Default configuration values
   - Configuration validation approach
   - Secrets management
