## Step 1: Ask for a Review in VS Code

Word has spread about the activities website, and now multiple teachers want to help develop new features. This is great, but your time is limited and if you don't have time to review changes, you fear the application will become messy. To scale your feedback availability, let's implement GitHub Copilot Code Review!

Before you start implementing Copilot Code Review across the entire school project, you want to understand how it works locally in VS Code. This will help you understand how to set it up and ensure all teacher-collaborators receive consistent feedback when they start contributing.

### 📖 Theory: GitHub Copilot Local Code Review

GitHub Copilot can review your code directly in VS Code, providing immediate feedback on uncommitted changes. This local review capability allows developers to catch issues before they even reach version control, improving code quality from the start.

Key features:

- **Local analysis** of uncommitted changes
- **Code quality and style** recommendations
- **Detection** of common security vulnerabilities
- **Performance optimization** suggestions

This immediate feedback helps you identify and fix issues early in your development process, making your code more robust before it even reaches a pull request.

### ⌨️ Activity: Get to know our extracurricular activities site

1. Start the codespace if it's not already running
1. Explore the project structure and familiarize yourself with the files in the `src/` directory
1. Open the terminal and run the web application to see the current functionality:

   ```bash
   cd src
   python app.py
   ```

1. Open the simple browser to view the running application
1. Take note of the current features and functionality

### ⌨️ Activity: Ask Copilot for a review

1. Make some changes to the code - you can add a new feature or modify existing functionality (for example, update some text in the HTML or add a new route to the Flask app)
1. Open Copilot Chat in VS Code (use the chat icon in the Activity Bar or press `Ctrl+Shift+I`)
1. Ask Copilot to review your uncommitted changes by typing something like: `@workspace Please review my uncommitted changes`
1. Review Copilot's suggestions and feedback
1. Address any suggestions that make sense for your changes
1. Commit and push your changes to trigger the next step

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you have GitHub Copilot enabled in VS Code
- Ensure you've made actual changes to files before asking for a review
- If Copilot doesn't see your changes, try saving the files first
- Remember that Copilot reviews uncommitted changes, so don't commit before asking for the review

</details>
