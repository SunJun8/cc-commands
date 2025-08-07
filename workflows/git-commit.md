Complete Git workflow for committing code using specialized agents:

1. **Repository Validation**
   - Verify the provided path is a valid git repository
   - Check if the repository has proper user configuration
   - Ensure the repository has a configured remote

2. **Staged Changes Analysis**
   - Prompt: "Review staged changes in the git repository at path: $ARGUMENTS. Analyze the code changes for quality, security, and best practices. Provide a summary of changes and suggest appropriate commit message categories."
   - Extract key changes for commit message generation

3. **Commit Message Generation**
   - Prompt: "Generate a scientific and规范的 commit message for the staged changes in repository at: $ARGUMENTS. The commit message should follow conventional commit format and include: type(scope): description. Based on the code review from step 2, provide a comprehensive commit message that accurately describes the changes."
   - Ensure commit message uses repository's configured user (not claude)

4. **User Confirmation**
   - Present the generated commit message to user
   - Show summary of changes to be committed
   - Wait for user confirmation before proceeding

5. **Create Commit**
   - Use git commit -s command with the generated message
   - Force sign-off using the repository's configured user
   - Ensure no claude user information is used

6. **Branch Selection and Push Confirmation**
   - List available branches and current branch
   - Ask user to confirm target branch for push
   - Show the remote that will be pushed to

7. **Push Changes**
   - Push to the confirmed remote branch
   - Provide push status and any relevant information

Target repository path: $ARGUMENTS
