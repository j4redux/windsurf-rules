# Windsurf Rules - Quick Start Guide

This guide explains how to quickly integrate Windsurf rules into any codebase, whether you're starting a new project or working with an existing one.

## 1. Installation

### Using the Bootstrap Script (Recommended)

```bash
# Download the bootstrap script
curl -o windsurf-bootstrap.sh https://gist.github.com/j4redux/55fb8f9973c9d0adc56070c8f868cb79/raw/4acfe55d74b365097542a10f3f2531ce7e2f6f02/windsurf-bootstrap.sh

# Make it executable
chmod +x windsurf-bootstrap.sh

# Run the script
./windsurf-bootstrap.sh

# Remove the script (optional)
rm windsurf-bootstrap.sh
```

## 2. Project-Specific Customization

After installing the base rules, customize them for your project:

### Create Project-Specific Rules

Create a file `.windsurf/rules/project-specifics.wind`:

```yaml
---
description: Project-Specific Rules
globs: *
---
# Project-Specific Rules

<rule>
name: project_technology_stack
description: Define technology stack for this project
filters:
  - type: intent
    pattern: "technology_recommendation"

actions:
  - type: suggest
    message: |
      Our project technology stack:

      1. Frontend: [Your frontend framework]
      2. Backend: [Your backend framework]
      3. Database: [Your database]
      4. Testing: [Your testing tools]

      Please follow these technologies when making recommendations.

metadata:
  priority: high
  version: 1.0
</rule>
```

### Customize Coding Standards

Edit `.windsurf/rules/coding-style.wind` to match your project's coding standards.

## 3. Using Windsurf Rules

Once set up, you can use the following commands in your editor:

- `help:windsurf` - Show available commands
- `learn:windsurf [description]` - Create a rule from what you just learned
- `update:windsurf [rule_name]` - Update an existing rule

## 4. Learning Loop

The key to effective use of Windsurf is the learning loop:

1. When the AI makes a mistake or misunderstands something, correct it
2. When the AI gets it right after correction, type `learn:windsurf [what it learned]`
3. The AI will create or update rules to remember this pattern
4. Over time, the AI becomes more aligned with your project's needs

## 5. Rule Categories to Consider

As your project grows, consider adding rules for:

1. **Architecture patterns** - How components should interact
2. **API design** - Standards for API endpoints and responses
3. **Testing practices** - How tests should be written
4. **Performance guidelines** - Standards for performance
5. **Security practices** - Required security measures
6. **Documentation** - Standards for code documentation

## 6. Integrating with CI/CD (Advanced)

For team settings, consider:

1. Creating a central repository of rules
2. Adding a CI step to validate rule syntax
3. Automating rule updates across projects

## 7. Sharing Rules Across Projects

To reuse rules across projects:

1. Create a central repository for your rules
2. Update the bootstrap script to pull from your repository
3. Tag versions for stability

## Example: Teaching Windsurf About Your Codebase

Here's an example workflow:

1. Ask Windsurf to analyze a core file: "Analyze src/core/auth.js and explain its purpose"
2. Correct any misunderstandings: "Actually, we use JWT tokens stored in cookies, not localStorage"
3. Tell Windsurf to learn: "learn:windsurf We use JWT tokens in HTTP-only cookies for authentication"
4. Windsurf creates/updates a rule to remember this pattern
5. Next time you discuss authentication, Windsurf already knows your approach

## Quick Reference Card

```
🌊 Windsurf Commands 🌊

help:windsurf              - Show help
learn:windsurf [details]   - Create rule from lesson
update:windsurf [rule]     - Update rule
list:rules                 - List all rules
show:rule [name]           - Show rule details

📂 Directory Structure:
.windsurf/
├── rules/      - Active rules
└── templates/  - Rule templates
```
