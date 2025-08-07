# Claude Code Slash Commands

Production-ready slash commands for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) that accelerate development through intelligent automation.

## Available Commands

### 🤖 Workflows

Multi-subagent orchestration for complex tasks:

- **[embedded-development](workflows/embedded-development.md)** - Complete embedded system implementation with architecture design, firmware development, code review, debugging, and RTOS integration

## Installation

```bash
cd ~/.claude
git clone https://github.com/wshobson/commands.git
git clone https://github.com/wshobson/agents.git  # Required for subagent orchestration
```

## Usage

```bash
/embedded-development Implement a real-time sensor monitoring system with NuttX RTOS
```

Claude Code automatically suggests relevant commands based on context.

## Features

- Production-ready implementations
- Framework auto-detection
- Security best practices
- Built-in monitoring and testing
- Commands work together seamlessly

## Workflows Overview

### Embedded Development Workflow

The `embedded-development` workflow orchestrates multiple specialized agents for complete embedded system implementation:

1. **System Architecture Design** - Hardware-software partitioning and specifications
2. **Firmware Development** - Embedded C implementation with hardware abstraction
3. **Code Review** - Static analysis and security validation
4. **Debugging & Testing** - System validation and error handling
5. **RTOS Integration** - NuttX/Vela integration when applicable

## Usage Examples

### Embedded Development

```bash
# Complete embedded system implementation
/embedded-development Design and implement a real-time environmental monitoring system with temperature, humidity, and pressure sensors using STM32 microcontroller and NuttX RTOS

# Motor control system
/embedded-development Create a brushless DC motor control system with PID feedback, CAN bus communication, and safety interlocks for automotive applications

# IoT device development
/embedded-development Develop a battery-powered IoT sensor node with LoRaWAN connectivity, sleep optimization, and OTA update capabilities
```

## Command Format

Slash commands are simple markdown files where:
- The filename becomes the command name (e.g., `embedded-development.md` → `/embedded-development`)
- The file content is the prompt/instructions executed when invoked
- Use `$ARGUMENTS` placeholder for user input

## Best Practices

### Command Selection
- **Let Claude Code suggest automatically** - Analyzes context and selects optimal commands
- **Use workflows for complex tasks** - Subagents coordinate multi-domain implementations
- **Provide comprehensive context** - Include tech stack, constraints, and requirements

### Effective Usage
- **Be specific about requirements** - Include hardware, protocols, and constraints
- **Include technical details** - Specify microcontrollers, sensors, and RTOS requirements
- **Define success criteria** - Outline performance and reliability expectations

## Contributing

1. Create `.md` file in `workflows/` or `tools/`
2. Use lowercase-hyphen-names
3. Include `$ARGUMENTS` for user input

## Troubleshooting

**Command not found**: Check files are in `~/.claude/commands/`

**Workflows slow**: Normal - they coordinate multiple subagents

**Generic output**: Add more specific context about your tech stack

**Integration issues**: Verify file paths and command sequence

## Performance Tips

**Command Selection:**
- **Workflows**: Multi-subagent coordination for complex features
- **Simple edits**: Stay with main agent

**Optimization:**
- Provide detailed requirements upfront
- Include hardware specifications and constraints
- Define real-time requirements and performance goals
- Let workflows complete before modifications

### Adding a New Workflow:
- Focus on subagent orchestration and delegation logic
- Specify which specialized subagents to use and in what order
- Define coordination patterns between subagents

## Learn More

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Slash Commands Documentation](https://docs.anthropic.com/en/docs/claude-code/slash-commands)
- [Subagents Documentation](https://docs.anthropic.com/en/docs/claude-code/sub-agents)
- [Claude Code GitHub](https://github.com/anthropics/claude-code)
- [Claude Code Subagents Collection](https://github.com/wshobson/agents) - Specialized subagents used by these commands