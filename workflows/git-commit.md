Complete Git workflow for committing code using specialized agents:

1. **Repository Validation**
   - Verify the provided path is a valid git repository
   - Check if the repository has proper user configuration
   - Ensure the repository has a configured remote

2. **Staged Changes Analysis**
   - Prompt: "Review staged changes in the git repository at path: $ARGUMENTS. Analyze the code changes for quality, security, and best practices. Provide a summary of changes and suggest appropriate commit message categories."
   - Extract key changes for commit message generation
   - Based on the primary language of this modification, choose the appropriate agent tool yourself.

3. **Commit Message Generation**
   - Prompt: "Generate a scientific and规范的 commit message for the staged changes in repository at: $ARGUMENTS. The commit message should follow conventional commit format and include: type(scope): description. Based on the code review from step 2, provide a comprehensive commit message that accurately describes the changes."
   - Do not include information such as AI or Claude in commit messages.
   - Enforce that each line in commit messages does not exceed 50 characters.

4. **User Confirmation**
   - Present the generated commit message to user
   - Show summary of changes to be committed
   - Wait for user confirmation before proceeding

5. **Create Commit**
   - Use git commit -s command with the generated message
   - Force sign-off using the repository's configured user
   - Ensure no claude user information is used, use global git config user.name and user.email
   - Do not include information such as AI or Claude in commit messages.

Target repository path: $ARGUMENTS
