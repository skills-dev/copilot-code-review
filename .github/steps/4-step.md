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

1. In the top navigation, select the **Settings** tab.

1. In the left navigation, expand **Rules** and select **Rulesets**.

1. Click **New ruleset** and select **New branch ruleset**.

1. Set the ruleset name and status:

   - **Ruleset Name**: `Require Copilot Reviews`
   - **Enforcement Status**: `Active`

1. Under **Target branches**, add protections for the `main` branch:

   1. Click **Add target** and **Include default branch**.
   1. Click **Add target** and **Include by pattern**.
   1. Enter `main` and click the **Add inclusion pattern** button.

   > 💡 **Tip**: Make sure you are triggering reviews at the right times in development. Both too early and too later will provide unhelpful results.

1. Under **Rules**, enable the following options:

   - **Require a pull request before merging**: ☑️
   - **Automatically request Copilot code review**: ☑️
   - **Require conversation resolution before merging**: ☑️

1. Scroll to the bottom and click the **Create** button.

### ⌨️ Activity: Verify required review

1. Navigate back to the pull request.

1. Notice that the merge button is now disabled.

1. Resolve the remaining feedback from Copilot.

1. Merge the pull request.

### ⌨️ Activity: (optional) Test required review

1. Create a new branch with the following name.

   ```txt
   enable-editing-announcements
   ```

1. Ask copilot to upgrade our new Announcements feature.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > The Announcement feature should not be hard coded.
   >
   > - Make it driven from the database.
   > - Allow signed in teachers to create and modify announcements.
   > - Announcements require an expiration date. Start date is optional.
   > - Add an example message to the database initialization.
   > ```

1. (optional) Run the application to test the changes.

1. (optional) Before committing the changes, ask for a local review in VS Code.

1. Commit and push the changes.

1. Create a new Pull Request with the following details.

   - **compare:** `enable-editing-announcements`
   - **target:** `main`
   - **title:** `Enable Editing Announcements`

1. Notice that Copilot was automatically added as a reviewer. Wait a moment for feedback.

1. (optional) Address any comments from Copilot.

1. Merge the pull request.

<!--
<details>
<summary>Having trouble? 🤷</summary><br/>

- ???

</details>
-->
