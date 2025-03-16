# Technical Context: [Project Name]

## Technology Stack

### Core Technologies
1. [Primary Language/Platform]
   - Version: [X.Y]+
   - Key frameworks/libraries
   - Core functionality provided

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
   - [Purpose in the project]
   - [Specific features used]
   - [Version constraints]
   - [License considerations]

2. [Key Dependency 2]
   - [Purpose in the project]
   - [Specific features used]
   - [Version constraints]
   - [License considerations]

3. [Key Dependency 3]
   - [Purpose in the project]
   - [Specific features used]
   - [Version constraints]
   - [License considerations]

## Development Setup

### Prerequisites
1. Development Tools
   - [Language/Platform] [version]
   - [Tool 1]
   - [Tool 2]
   - [Tool 3]
   - [IDE/Editor of choice]

2. Environment Setup
   ```bash
   # Install required tools
   [Command to install tool 1]
   [Command to install tool 2]
   
   # Setup environment variables
   export [ENV_VAR1]=[value1]
   export [ENV_VAR2]=[value2]
   
   # Clone repository
   git clone [repository URL]
   cd [project directory]
   
   # Initialize dependencies
   [Command to install dependencies]
   ```

### Build Process
1. Building the Application
   ```bash
   [Build command]
   ```

2. Running Tests
   ```bash
   # Run all tests
   [Test command]
   
   # Run specific test suite
   [Specific test command]
   
   # Generate test coverage report
   [Coverage command]
   ```

3. Build Scripts/Automation
   ```bash
   # Build the application
   [Build script command]
   
   # Run tests
   [Test script command]
   
   # Clean build artifacts
   [Clean script command]
   
   # Build and run
   [Run script command]
   
   # Generate documentation
   [Documentation script command]
   ```

## Deployment

### Container Deployment
1. Container Structure
   ```
   project/
   ├── [Container definition file]
   ├── [Container ignore file]
   └── [Container compose file] (if applicable)
   ```

2. Image Building
   ```bash
   # Build container image
   [Command to build container]
   
   # Run container locally
   [Command to run container]
   ```

3. Container Registry
   - Registry: [Registry name/URL]
   - Image naming convention: [convention details]
   - Tag strategy: [tag strategy]

### Cloud Deployment
1. [Cloud Provider]
   - Service: [Service name]
   - Region: [Primary deployment region]
   - Configuration: [Key configuration details]

2. Infrastructure as Code
   - Tool: [IaC tool name]
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
   [Project-specific directory structure]
   ```

2. Logging and Telemetry
   - Logging library/framework: [name]
   - Log format: [format details]
   - Log levels: [debug, info, warn, error, etc.]
   - Telemetry solution: [solution name if applicable]

3. Testing Strategy
   - Unit testing approach
   - Integration testing approach
   - End-to-end testing approach
   - Performance testing approach
   - Testing tools and libraries:
     * [Tool/library 1]
     * [Tool/library 2]

4. Documentation
   - API documentation: [tool/approach]
   - Architecture documentation: [location/format]
   - Operation guides: [location/format]
   - Developer guides: [location/format]

5. Configuration Management
   - Configuration format: [format]
   - Environment variable usage
   - Default configuration values
   - Configuration validation approach
   - Secrets management approach
