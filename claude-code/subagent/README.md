# Claude Code Subagents Guide

## Overview

Claude Code provides specialized subagents that can handle complex, multi-step tasks autonomously. These subagents are designed to work with specific tool sets and excel at particular types of operations, allowing you to delegate specialized work while maintaining efficiency and accuracy.

## Available Subagents

### General-Purpose Agent
- **Type**: `general-purpose`
- **Tools**: Full access to all available tools (*)
- **Best for**: 
  - Complex research tasks
  - Multi-step code searches
  - Autonomous task execution
  - When you need multiple rounds of searching and analysis

### Statusline Setup Agent
- **Type**: `statusline-setup`
- **Tools**: Read, Edit
- **Best for**: 
  - Configuring Claude Code status line settings
  - Status bar customization

### Output Style Setup Agent
- **Type**: `output-style-setup`
- **Tools**: Read, Write, Edit, Glob, LS, Grep
- **Best for**: 
  - Creating Claude Code output styles
  - Formatting and presentation customization

## When to Use Subagents

### Use Subagents When:
- **Complex multi-step tasks**: Tasks requiring 3+ distinct steps or operations
- **Extensive searching**: When you're not confident you'll find the right match in the first few tries
- **Autonomous execution**: Tasks that benefit from independent problem-solving
- **Specialized operations**: Tasks that match a specific subagent's expertise

### Don't Use Subagents When:
- **Simple file reads**: Use Read or Glob tools directly for specific file paths
- **Known code searches**: Use Glob for specific class definitions like "class Foo"
- **Small file sets**: Use Read tool for searching within 2-3 specific files
- **Non-matching tasks**: Tasks unrelated to available subagent descriptions

## How to Launch Subagents

Use the Task tool to launch subagents with these required parameters:

```javascript
{
  "description": "Brief 3-5 word description",
  "prompt": "Detailed task description for autonomous execution", 
  "subagent_type": "agent-type-name"
}
```

### Example Usage

```javascript
// Launch general-purpose agent for complex search
{
  "description": "Search authentication patterns",
  "prompt": "Search through the codebase to find all authentication-related patterns, including login flows, token validation, and user session management. Provide a comprehensive analysis of the current authentication architecture.",
  "subagent_type": "general-purpose"
}

// Launch statusline setup agent
{
  "description": "Configure status line",
  "prompt": "Configure the Claude Code status line to show current git branch, file modification status, and line/column information",
  "subagent_type": "statusline-setup"  
}
```

## Best Practices

### 1. Detailed Task Descriptions
- Provide highly detailed task descriptions in the prompt
- Specify exactly what information you want returned
- Include context about the codebase or project when relevant

### 2. Concurrent Execution
- Launch multiple subagents simultaneously when possible
- Use a single message with multiple tool uses for maximum performance
- Each subagent runs independently and reports back

### 3. Clear Expectations
- Specify whether you expect code writing or just research
- Define the scope and boundaries of the task
- Indicate the desired format for results

### 4. Stateless Operations
- Each subagent invocation is completely stateless
- You cannot send follow-up messages to a running subagent
- Include all necessary context in the initial prompt

## Advanced Tips

### Research vs. Implementation
Always clearly specify the task type:
- **Research tasks**: "Search, analyze, and report on..."
- **Implementation tasks**: "Write code to implement..."

### Result Handling
- Subagent outputs should generally be trusted
- Results are returned in a single final message
- Process and present results to the user as needed

### Error Recovery
- If a subagent doesn't find what you're looking for, try refining the search terms
- Consider breaking complex tasks into smaller, more focused subtasks
- Use different subagent types for different aspects of the same project

## Common Patterns

### Code Discovery
```javascript
{
  "description": "Find API endpoints", 
  "prompt": "Search the entire codebase for API endpoint definitions, including REST routes, GraphQL resolvers, and any custom API handlers. Document the endpoint patterns, authentication requirements, and request/response formats.",
  "subagent_type": "general-purpose"
}
```

### Architecture Analysis  
```javascript
{
  "description": "Analyze component structure",
  "prompt": "Analyze the React component architecture in this project. Identify component hierarchies, prop flow patterns, state management approaches, and any architectural patterns or anti-patterns. Provide recommendations for improvements.",
  "subagent_type": "general-purpose"  
}
```

### Configuration Tasks
```javascript
{
  "description": "Setup output formatting",
  "prompt": "Create a custom output style for Claude Code that emphasizes readability with proper syntax highlighting, clear section separators, and consistent indentation for code blocks.",
  "subagent_type": "output-style-setup"
}
```

Remember: Subagents are powerful tools for complex tasks, but simple operations are often better handled with direct tool usage. Choose the right approach based on task complexity and requirements.