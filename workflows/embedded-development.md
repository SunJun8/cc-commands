Implement a complete embedded system feature using specialized agents with explicit Task tool invocations:

[Extended thinking: This workflow orchestrates multiple embedded development agents to implement a complete embedded system feature from design to deployment. Each agent receives context from previous agents to ensure coherent implementation throughout the embedded development lifecycle.]

Use the Task tool to delegate to specialized agents in sequence:

1. **System Architecture Design**
   - Use Task tool with subagent_type="embedded-solution-designer"
   - Prompt: "Design embedded system architecture for: $ARGUMENTS. Include hardware-software partitioning, resource budgeting, interface definitions, and technical specifications."
   - Save the architecture design and specifications for next agents

2. **Firmware Development**
   - Use Task tool with subagent_type="embedded-c-developer"
   - Prompt: "Implement embedded C firmware for: $ARGUMENTS. Use the architecture design from embedded-solution-designer: [include architecture, interfaces, and specifications from step 1]. Focus on clean, efficient code with proper hardware abstraction."
   - Ensure implementation follows the design specifications

3. **Code Review and Static Analysis**
   - Use Task tool with subagent_type="embedded-code-reviewer"
   - Prompt: "Perform comprehensive code review and static analysis for: $ARGUMENTS. Review the firmware implementation from embedded-c-developer: [include code from step 2]. Check for security vulnerabilities, performance issues, and standards compliance."
   - Provide detailed findings and improvement suggestions

4. **Debugging and Testing**
   - Use Task tool with subagent_type="embedded-debugger"
   - Prompt: "Analyze and debug the embedded system for: $ARGUMENTS. Review the firmware from embedded-c-developer: [include code from step 2] and issues identified by embedded-code-reviewer: [include findings from step 3]. Implement debugging strategies and test plans."
   - Ensure robust error handling and recovery mechanisms

5. **NutX/Vela Integration (if applicable)**
   - Use Task tool with subagent_type="nuttx-embedded"
   - Prompt: "Integrate the embedded feature with NuttX/Vela RTOS for: $ARGUMENTS. Use the firmware implementation: [include code from step 2] and debugging results: [include findings from step 4]. Ensure proper RTOS integration, task management, and hardware abstraction."
   - Optimize for real-time performance and resource usage

Aggregate results from all agents and present a unified embedded system implementation with comprehensive documentation, tested code, and deployment-ready firmware.

Feature description: $ARGUMENTS