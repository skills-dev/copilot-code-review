## Step 3: Customize Your Review

The school's coding standards are crucial for maintaining the activities website. You've noticed that teachers are using different visual styles and coding patterns. With such diverse programming backgrounds and priorities among your teacher-collaborators, let's customize Copilot's review behavior to align with the school's educational programming standards.

### 📖 Theory: Repository Custom Instructions

Repository custom instructions allow you to provide Copilot with context about your project standards and preferences. By creating instruction files, you can ensure Copilot's suggestions consistently follow your team's conventions and focus on your specific requirements. You can even have copilot analyze your project and [generate instructions](https://code.visualstudio.com/docs/copilot/customization/custom-instructions#_generate-an-instructions-file-for-your-workspace) for you!

**Types of Instructions:**

- **Repository-wide instructions**: Applies to all code in the repository. Ex: `.github/copilot-instructions.md`
- **Path-specific instructions**: Applies to specific files to create focused criteria for different parts of your codebase. Ex: `.github/instructions/NAME.instructions.md`.

Instructions are written in natural language with Markdown format and typically include:

- Security requirements and checklists
- Code standards and conventions
- Performance optimization priorities
- Team-specific preferences and style guides
- Language-specific review criteria

Path-specific instruction files include [YAML front matter](https://docs.github.com/en/contributing/writing-for-github-docs/using-yaml-frontmatter) with file [glob patterns](https://code.visualstudio.com/docs/editor/glob-patterns) to target specific files and directories. Examples:

```yaml
---
applyTo: "tests/**/**,docs/*.md"
---
# Testing Guidelines ...
```

```yaml
---
applyTo: "docs/*.md,README.md"
---
# Documentation Guidelines ...
```

> [!TIP]
> Repository [custom instructions](https://docs.github.com/en/copilot/how-tos/custom-instructions/adding-repository-custom-instructions-for-github-copilot) work for both local VS Code code reviews and pull request code reviews, ensuring consistency across your development workflow.

### ⌨️ Activity: Add general instructions

Let's customize Copilot's review considerations by adding custom instructions.

1. In VS Code, ensure you are still on the `add-announcement-banner` branch.

1. Create a file for general repository guidelines.

   File location and name:

   ```txt
   .github/copilot-instructions.md
   ```

   Content:

   ```markdown
   ## Security

   - Validate input sanitization practices.
   - Search for risks that might expose user data.
   - Prefer loading configuration and content from the database instead of hard coded content. If absolutely necessary, load it from environment variables or a non-committed config file.

   ## Code Quality

   - Use consistent naming conventions.
   - Try to reduce code duplication.
   - Prefer maintainability and readability over optimization.
   - If a method is used a lot, try to optimize it for performance.
   - Prefer explicit error handling over silent failures.
   ```

### ⌨️ Activity: Add focused instructions

Let's create specific Copilot's review considerations for the frontend and backend.

1. Create a file for the frontend-specific guidelines.

   > ❗️ **Important**: Make sure to put file-specific instructions in the `.github/instructions/` folder, not the `.github/` folder.

   File location and name:

   ```txt
   .github/instructions/frontend.instructions.md
   ```

   Content:

   ```markdown
   ---
   applyTo: "*.html,*.css,*.js"
   ---

   ## Frontend Guidelines

   - Use accessibility attributes (alt text, aria labels) and color schemes.
   - Use responsive design for compatibility with mobile devices.
   - Validate HTML structure and semantic elements
   ```

1. Create a file for the backend-specific guidelines.

   File location and name:

   ```txt
   .github/instructions/backend.instructions.md
   ```

   Content:

   ```markdown
   ---
   applyTo: "backend/**/*,*.py"
   ---

   ## Backend Guidelines

   - All API endpoints must be defined in the `routers` folder.
   - Load example database content from the `database.py` file.
   - Error handling is only logged on the server. Do not propagate to the frontend.
   - Ensure all APIs are explained in the documentation.
   - Verify changes in the backend are reflected in the frontend (`src/static/**`). If possible breaking changes are found, mention them to the developer.
   ```

1. Commit and push the instruction files.

> [!TIP]
> VS Code has a built-in commands to help manage instructions. Try opening the command pallette and searching for `instructions`.

### ⌨️ Activity: Request another review

With our new instructions defined, Copilot now has a better idea of what is important for our project. Let's ask for another review.

1. In VS Code, Ensure the instructions are indeed committed and push to the repository.

1. In the web browser, return to the recently created pull request.

1. In the top right, find the **Reviewers** menu and **Re-request review** button next to **Copilot**. Click it and wait a moment for Copilot to add comments on the pull request.

   <img width="300" alt="screenshot of re-review button" src="https://github.com/user-attachments/assets/c45aa8de-278d-46e7-bfe2-2dc6b574e11e"/>

   > 🪧 **Note:** If you are too quick after pushing new commits, you may have to wait a moment for the button to appear, or refresh the page.

1. Observe that Copilot's feedback now differs from the previous review.

1. With the review requested, wait a moment for Mona to check your work, provide feedback, and share the next lesson.

<details>
<summary>Having trouble? 🤷</summary><br/>

- If you forgot to add a custom instruction (or made a typo), try fixing the mistake and asking Copilot for another review. This will inform Mona to check your work again.

</details>
