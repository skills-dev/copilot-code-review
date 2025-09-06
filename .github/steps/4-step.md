## Step 4: Automate Reviews

The tailored reviews seem to be working great, however there's a problem. They aren't technically required. Manually requesting Copilot reviews clearly isn't sustainable when you have multiple teachers contributing to the activities website. You want every pull request to automatically receive Copilot's feedback, especially since there are varying levels of programming experience among your collaborators. Let's set up repository rulesets to require Copilot reviews on all changes.

### 📖 Theory: Repository Rulesets for Automated Reviews

Repository rulesets allow you to enforce automatic code reviews on all pull requests, ensuring consistent quality checks without relying on developers to manually request reviews or remember to follow documentation.

Each code review consumes one Premium Request Unit (PRU) from the author of the pull request.

**Enforcement Options:**

- **Repository-level**: All new pull requests in the specific repository
- **Branch-specific**: Target specific branches by filters and name patterns
- **Organization-level**: Apply rule sets across multiple repositories

**Key Benefits:**

- Consistent code quality across all contributions
- Automatic enforcement without manual intervention
- Configurable based on branch protection needs
- Integration with existing GitHub workflow permissions

For more information, see the [repository rulesets documentation](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets).

### ⌨️ Activity: Create a repository ruleset

1. Navigate to your repository's **Settings** tab on GitHub.com

1. Select **Rules** → **Rulesets** in the left sidebar

1. Click **New ruleset** → **New branch ruleset**

1. Configure the ruleset:

   - Set the **Ruleset name** to "Require Copilot Reviews"
   - Set **Enforcement Status** to **Active**

1. Under **Target branches**, configure branch coverage:

   - Select **Add target** → **Include default branch**
   - This will target your `main` branch

1. Configure pull request requirements:

   - Enable **Require a pull request before merging**
   - Check **Request pull request review from Copilot**
   - Optionally enable **Require conversation resolution before merging** for better workflow

1. Click **Create** to activate the ruleset

### ⌨️ Activity: Test automatic review

1. Create a new branch from main in VS Code or on GitHub

1. Make changes to the codebase - you can add a new feature, fix an issue, or improve existing functionality

1. Push your changes and create a pull request

1. Notice that Copilot is automatically assigned as a reviewer - you should see it in the reviewers section

1. Wait for Copilot's automatic review and examine the feedback provided

1. Address any suggestions from Copilot's review

1. Observe how the automated review process helps maintain code quality without manual intervention

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you have admin permissions on the repository to create rulesets
- If you don't see the Rulesets option, check that you're in the repository Settings (not your account settings)
- The ruleset will only affect new pull requests created after it's activated
- You can edit or disable the ruleset if needed from the same Rules → Rulesets page

</details>
