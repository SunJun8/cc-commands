Implement a complete Python application feature using specialized agents with explicit Task tool invocations:

[Extended thinking: This workflow orchestrates multiple Python development agents to implement a complete Python application feature from design to deployment. Each agent receives context from previous agents to ensure coherent implementation throughout the Python development lifecycle.]

Use the Task tool to delegate to specialized agents in sequence:

1. **Requirements Analysis**
   - Use Task tool with subagent_type="python-requirements-analyst"
   - Prompt: "Analyze and refine requirements for: $ARGUMENTS. Identify functional requirements, non-functional requirements, user stories, acceptance criteria, and edge cases. Ensure comprehensive requirements coverage."
   - Save the requirements analysis for next agents

2. **System Architecture Design**
   - Use Task tool with subagent_type="python-solution-designer"
   - Prompt: "Design Python system architecture for: $ARGUMENTS. Use the requirements analysis from python-requirements-analyst: [include requirements from step 1]. Include technology stack selection, project structure, module organization, dependency management, and technical specifications."
   - Save the architecture design and specifications for next agents

3. **Python Development**
   - Use Task tool with subagent_type="python-developer"
   - Prompt: "Implement Python code for: $ARGUMENTS. Use the requirements analysis from python-requirements-analyst: [include requirements from step 1] and architecture design from python-solution-designer: [include architecture, specifications from step 2]. Focus on clean, efficient, and maintainable code with proper error handling and type hints."
   - Ensure implementation follows the design specifications

4. **Code Review and Static Analysis**
   - Use Task tool with subagent_type="python-code-reviewer"
   - Prompt: "Perform comprehensive code review and static analysis for: $ARGUMENTS. Review the implementation from python-developer: [include code from step 3]. Check for security vulnerabilities, performance issues, code quality, and standards compliance."
   - Provide detailed findings and improvement suggestions

5. **Testing and Quality Assurance**
   - Use Task tool with subagent_type="python-testing-agent"
   - Prompt: "Create comprehensive tests for: $ARGUMENTS. Review the implementation from python-developer: [include code from step 3] and issues identified by python-code-reviewer: [include findings from step 4]. Implement unit tests, integration tests, and performance tests."
   - Ensure high test coverage and reliable code

6. **Bug Fixing and Optimization**
   - Use Task tool with subagent_type="python-bug-fixer"
   - Prompt: "Analyze and fix issues in the Python application for: $ARGUMENTS. Review the implementation from python-developer: [include code from step 3], test results from python-testing-agent: [include test results from step 5], and issues from python-code-reviewer: [include findings from step 4]. Implement fixes and optimizations."
   - Ensure robust error handling and performance

7. **Release Management**
   - Use Task tool with subagent_type="python-release-agent"
   - Prompt: "Prepare the Python application for release: $ARGUMENTS. Review the implementation: [include code from step 3], test results: [include test results from step 5], and bug fixes: [include fixes from step 6]. Ensure proper packaging, documentation, and deployment readiness."
   - Optimize for production deployment and maintenance

Aggregate results from all agents and present a unified Python application implementation with comprehensive documentation, tested code, and deployment-ready package.

Feature description: $ARGUMENTS