# Technical Context: [Project Name]

## Technology Stack

### Core Technologies

1. Godot Engine (version 4.x)
   - Primary game development engine
   - Built-in GDScript language
   - Scene-based architecture
   - Node system for game objects

2. GDScript
   - Primary scripting language
   - Static typing support
   - Object-oriented programming
   - Built-in integration with Godot Engine

3. [Additional Technology, if applicable]
   - [Purpose in the project]
   - [Key features used]
   - [Version requirements]

### Dependencies

1. Godot Addons
   - [Addon 1]
     - Purpose: [What it's used for]
     - Version: [Version number]
     - Source: [GitHub/Asset Library link]

   - [Addon 2]
     - Purpose: [What it's used for]
     - Version: [Version number]
     - Source: [GitHub/Asset Library link]

2. External Assets
   - [Asset Pack 1]
     - Purpose: [What it's used for]
     - License: [License type]
     - Source: [Where it was obtained]

   - [Asset Pack 2]
     - Purpose: [What it's used for]
     - License: [License type]
     - Source: [Where it was obtained]

## Development Setup

### Prerequisites

1. Development Tools
   - Godot Engine 4.x
   - Git for version control
   - [Additional tools if needed]
   - Text editor or IDE with GDScript support (VSCode with Godot Tools, etc.)

2. Environment Setup

   ```bash
   # Clone repository
   git clone [repository URL]
   cd [project directory]
   
   # Open project in Godot
   godot -e
   ```

### Project Structure

```
project/
├── .git/                  # Git repository
├── .gitignore             # Git ignore file
├── project.godot          # Godot project file
├── export_presets.cfg     # Export configurations
├── default_env.tres       # Default environment
├── icon.png               # Project icon
├── scenes/                # All game scenes
│   ├── main/              # Main game scenes
│   ├── ui/                # UI scenes
│   ├── levels/            # Level scenes
│   └── characters/        # Character scenes
├── scripts/               # GDScript files
│   ├── autoloads/         # Singleton scripts
│   ├── resources/         # Custom resources
│   └── classes/           # Reusable classes
├── resources/             # Resource files
│   ├── themes/            # UI themes
│   └── materials/         # Materials
├── assets/                # Game assets
│   ├── textures/          # Texture files
│   ├── models/            # 3D models
│   ├── audio/             # Sound and music
│   └── fonts/             # Font files
├── addons/                # Third-party addons
└── tests/                 # Test scenes and scripts
```

### Build Process

1. Running the Project

   ```bash
   # Open project in Godot Editor
   godot -e
   
   # Run project directly
   godot --path /path/to/project
   ```

2. Testing

   ```bash
   # Run tests using GUT or custom test framework
   godot --path /path/to/project --script res://tests/run_tests.gd
   ```

## Deployment

### Export Configuration

1. Export Presets
   - Windows (Desktop)
   - macOS (Desktop)
   - Linux (Desktop)
   - Android (Mobile)
   - iOS (Mobile)
   - HTML5 (Web)

2. Platform-Specific Settings
   - Windows:
     - Architecture: x86_64
     - Features: [specific features]

   - Android:
     - Minimum SDK: [version]
     - Target SDK: [version]
     - Permissions: [list of permissions]

3. Export Process

   ```bash
   # Export using Godot Editor
   godot --export "Windows Desktop" /path/to/output.exe
   
   # Export using Godot Editor (headless)
   godot --headless --export "Windows Desktop" /path/to/output.exe
   ```

### Distribution Platforms

1. PC Distribution
   - Steam
   - Epic Games Store
   - itch.io
   - GOG

2. Mobile Distribution
   - Google Play Store
   - Apple App Store

3. Web Distribution
   - itch.io
   - Newgrounds
   - Own website

### CI/CD Pipeline

1. GitHub Actions
   - Triggers: [When pipelines run]
   - Stages:
     - Build
     - Test
     - Export
     - Deploy to Staging
     - Deploy to Production

## Technical Constraints

1. Performance Targets
   - Minimum FPS: [target]
   - Target platforms: [platforms]
   - Minimum specifications: [specs]
   - Resolution support: [resolutions]

2. Asset Constraints
   - Texture size limits
   - Polygon count guidelines
   - Audio quality/compression settings
   - Memory usage targets

3. Platform-Specific Constraints
   - Mobile:
     - Touch controls
     - Battery usage
     - File size limits

   - Web:
     - Loading times
     - Browser compatibility
     - WebGL limitations

## Development Patterns

1. Scene Management
   - Scene switching approach
   - Scene preloading strategy
   - Scene instancing patterns

2. State Management
   - Game state handling
   - Save/load system
   - Persistent data approach

3. Input Handling
   - Input mapping system
   - Controller support
   - Touch input handling

4. Optimization Techniques
   - Object pooling
   - Level of detail (LOD) system
   - Occlusion culling
   - Background loading

5. Testing Strategy
   - Unit tests for critical systems
   - Integration tests for game mechanics
   - Playtesting methodology
   - Performance profiling approach

6. Asset Pipeline
   - Asset creation workflow
   - Import settings standardization
   - Asset versioning approach
   - Quality assurance process

7. Localization Strategy
   - Text translation system
   - Audio localization approach
   - Cultural adaptation considerations
   - Testing for different locales
