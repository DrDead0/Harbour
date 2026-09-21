# Harbor

**Harbor is a desktop developer workspace and project-management application built for managing software projects, development tasks, repositories, and local development workflows from one place.**

Built with C++, Harbor combines project organization with direct awareness of the developer's local workspace, Git repositories, development commands, tasks, and project activity.

## Overview

Developers commonly use separate tools for project tracking, task management, repository inspection, terminal commands, builds, and local project organization.

Harbor brings these workflows together into a single desktop application.

It allows developers to organize software projects while remaining connected to the actual projects stored on their machine.

```text
                    Harbor
                      │
        ┌─────────────┼─────────────┐
        │             │             │
     Projects       Tasks       Development
        │             │           Workflow
        │             │             │
   Filesystem      Planning      Git / Build
   Repository      Progress      Test / Run
   Metadata        Assignment    Processes
```

## Features

### Project Management

Harbor provides a centralized workspace for managing software projects.

Projects can contain information such as:

- Project name
- Description
- Programming language
- Project type
- Status
- Local project path
- Repository information
- Associated tasks
- Development activity

Projects can be created, updated, searched, filtered, organized, and removed directly from the application.

### Local Project Discovery

Harbor understands projects stored on the local filesystem.

It can inspect project directories and recognize common project structures and development files.

Examples include:

```text
CMakeLists.txt
package.json
go.mod
Cargo.toml
pyproject.toml
.git/
```

This allows Harbor to connect project-management information with the actual source code and development environment.

### Task Management

Tasks can be created and associated directly with software projects.

Tasks support information such as:

- Title
- Description
- Status
- Priority
- Assignee
- Project association
- Creation and update information

Tasks can be searched, filtered, updated, completed, and organized by project.

### Git Integration

Harbor integrates with Git repositories associated with projects.

Repository information includes:

- Repository detection
- Current branch
- Available branches
- Working-tree status
- Changed files
- Recent commits
- Repository activity

This provides useful repository context without requiring developers to constantly switch between different tools.

### Build, Test and Run

Harbor can execute development commands directly against managed projects.

Supported workflows include:

```text
Build
Test
Run
Custom Commands
```

Harbor tracks process information including:

- Running state
- Standard output
- Standard error
- Exit codes
- Successful completion
- Failed execution

This allows project-management information and development execution to exist inside the same workspace.

### Activity

Harbor maintains useful development activity associated with projects.

Activity can include events such as:

- Project creation
- Project updates
- Task creation
- Task completion
- Branch changes
- Repository changes
- Build execution
- Build success or failure
- Process execution

The activity view provides historical context for work performed across the workspace.

### Search

Harbor provides centralized search across workspace information.

Search can include:

- Projects
- Tasks
- Team members
- Development activity
- Repository information

This makes it easier to navigate large development workspaces containing multiple projects.

### Team Management

Harbor supports development teams as well as individual developers.

Team functionality includes:

- Team members
- Project assignments
- Task assignments
- Project progress
- Member activity
- Repository information
- Branch visibility

This allows managers and developers to understand who is working on a project, what work is assigned, and how development is progressing.

### Notifications

Harbor can surface useful workspace events such as:

- Task assignments
- Task updates
- Build failures
- Build completion
- Repository changes
- Project activity
- Team activity

Notifications remain connected to actual development and project-management information.

### Local Persistence

Harbor stores workspace information locally using SQLite.

Persistent information includes project data, tasks, settings, activity, repository metadata, and team-related information.

Projects and workspace state remain available between application sessions.

## Application Structure

Harbor separates the desktop interface from the application's core functionality.

```text
                         HARBOR
                            │
                  ┌─────────┴─────────┐
                  │                   │
              Qt Desktop          Harbor Core
                                      │
                 ┌────────────────────┼────────────────────┐
                 │                    │                    │
              Projects             Tasks               Teams
                 │                    │                    │
                 └────────────────────┼────────────────────┘
                                      │
             ┌──────────────┬─────────┼─────────┬──────────────┐
             │              │         │         │              │
         Filesystem       Storage    Git     Processes      Activity
                           SQLite
```

The core manages application data and behavior while specialized components handle filesystem access, persistence, Git repositories, development processes, and other system-level functionality.

The Qt desktop interface provides the user-facing workspace while remaining separate from Harbor's underlying project-management and development logic.

## Technology

Harbor is built around native C++ technologies and desktop development tools.

```text
C++23
Qt
CMake
SQLite
std::filesystem
Git
Native process management
```

## Workspace

Harbor provides dedicated areas for:

```text
Dashboard
Projects
Project Details
Tasks
Teams
Activity
Search
Settings
```

Together, these areas create a unified workspace for managing both the organizational and technical sides of software development.

## Purpose

Harbor is designed around a simple idea:

> Software project management should remain connected to the software being developed.

Instead of treating tasks, repositories, local projects, builds, commands, and development activity as completely separate systems, Harbor brings them together into one desktop workspace.

It provides developers and development teams with a single place to organize projects, manage work, inspect repositories, interact with local development environments, and understand ongoing project activity.
