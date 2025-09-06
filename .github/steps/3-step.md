## Step 3: Customize Your Review

The school's coding standards are crucial for maintaining the activities website. You've noticed that teachers are using different visual styles and coding patterns. With such diverse programming backgrounds and priorities among your teacher-collaborators, let's customize Copilot's review behavior to align with the school's educational programming standards.

### 📖 Theory: Repository Custom Instructions

Repository custom instructions allow you to provide Copilot with context about your project standards and preferences. By creating instruction files, you can ensure Copilot's suggestions consistently follow your team's conventions and focus on your specific requirements.

**Types of Instructions:**

- **Repository-wide instructions**: Apply to all code reviews in the repository using `.github/copilot-instructions.md`
- **Path-specific instructions**: Apply to specific files or directories by providing glob patterns in the front matter, e.g., `.github/instructions/NAME.instructions.md`

Instructions are written in natural language with Markdown format and typically include:

- Security requirements and checklists
- Code standards and conventions
- Performance optimization priorities
- Team-specific preferences and style guides
- Language-specific review criteria

> [!TIP]
> Repository [custom instructions](https://docs.github.com/en/copilot/how-tos/custom-instructions/adding-repository-custom-instructions-for-github-copilot) work for both VS Code reviews and pull request reviews, ensuring consistency across your development workflow.

### ⌨️ Activity: Add general instructions

Let's tailor Copilot's review by creating custom instructions.

1. Create a new file called `.github/copilot-instructions.md` in your repository

1. Add repository-wide rules that focus on the school's needs:

   ```markdown
   ## Security Focus

   - Scan for SQL injection vulnerabilities
   - Validate input sanitization practices
   - Check authentication and authorization
   - Ensure student data protection and privacy

   ## Code Quality Standards

   - Enforce consistent naming conventions
   - Identify code duplication opportunities
   - Suggest performance optimizations
   - Require comprehensive error handling

   ## Team Preferences

   - Prefer explicit error handling over silent failures
   - Recommend TypeScript over JavaScript where applicable
   - Focus on maintainability and readability
   - Add educational comments for learning purposes
   ```

### ⌨️ Activity: Add focused instructions

1. Create `.github/instructions/frontend-review.instructions.md` for frontend-specific guidelines:

   - Add front matter that targets UI-related files: `*.html`, `*.css`, `*.js`
   - Include guidelines for accessibility, responsive design, and user experience

1. Create `.github/instructions/backend-review.instructions.md` for server-side guidelines:
   - Add front matter that targets files in the `backend/` directory and `*.py` files
   - Include guidelines for API design, database security, and performance

### ⌨️ Activity: Test the instructions

1. Create a new branch and make changes that affect both backend and frontend components

1. Create a new pull request and request a Copilot review to test the custom instructions

1. Observe how Copilot's feedback differs based on the custom instructions you've provided

1. Merge this pull request to trigger the next step

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure to place instruction files in the correct `.github/` directories
- Front matter in path-specific instructions should use proper YAML format
- Test your instructions with small changes first to see how they affect reviews
- Remember that custom instructions apply to both local VS Code reviews and pull request reviews

</details>
