## Step 4: Automate Reviews

The tailored reviews seem to be working great, however there's a problem. They aren't technically required. Manually requesting Copilot reviews clearly isn't sustainable when you have multiple teachers contributing to the activities website. You want every pull request to automatically receive Copilot's feedback, especially since there are varying levels of programming experience among your collaborators. Let's set up repository rulesets to require Copilot reviews on all changes.

### 📖 Theory: Repository Rulesets for Automated Reviews

Repository rulesets allow you to enforce automatic code reviews on all pull requests, ensuring consistent quality checks without relying on developers to manually request reviews or remember to follow documentation.

Each code review consumes one [Premium Request Unit (PRU)](https://docs.github.com/en/copilot/concepts/billing/copilot-requests) from the author of the pull request.

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

1. Click the **New ruleset** button and select the **New branch ruleset** option.

1. Set the ruleset name and status:

   - **Ruleset Name**: `Require Copilot Reviews`
   - **Enforcement Status**: `Active`

1. Under **Target branches**, add protections for the `main` branch.

   1. Click **Add target** and **Include default branch**.
   1. Click **Add target** and **Include by pattern**.
   1. Enter `main` and click the **Add inclusion pattern** button.

   <img width="300" alt="screenshot of target branches" src="https://github.com/user-attachments/assets/217f205c-7a61-4ffa-a0a6-7e76ff8d7906"/>

1. Under **Rules**, enable the following options:

   - **Require a pull request before merging**: ☑️
   - **Require conversation resolution before merging**: ☑️
   - **Automatically request Copilot code review**: ☑️

1. Scroll to the bottom and click the **Create** button.

1. Return to the open pull request.

1. Notice that the merge button is now disabled.

   <img width="300" alt="screenshot of disabled merge button" src="https://github.com/user-attachments/assets/28e4cb05-f09d-423d-8c77-8f0ec61c73ad"/>

1. Click **Resolve conversation** for all current and outdated feedback from Copilot. It is not necessary to implement anything.

1. Merge the pull request.

   > 🪧 **Note**: If the **Merge pull request** button doesn't activate, check for unresolved conversations in the outdated comments.

1. With the pull request merged, wait a moment for Mona to check your work, provide feedback, and provide a final review. Nice work! You are all done! 🎉

### ⌨️ Activity: (optional) Test automatic reviews

Not ready to finish yet? Are you concerned by the hard coded announcement banner? Us too!

So... let's fix it! 🧑‍🚀🚀

> [!NOTE]
> You don't need "fix" the new Announcement feature. If you just want to test automatic reviews, you can just make a quick small change and start a new pull request.

1. In VS Code, switch back to the `main` branch, pull the merged changes, and delete the `add-announcement-banner` branch.

1. Create a new branch from `main` with the following name.

   ```txt
   enable-editing-announcements
   ```

1. Open the Copilot Chat panel and ensure it is in **Agent mode**. Use the following prompt to ask Copilot to upgrade our new Announcements feature.

   > 💡 **Tip**: The premium models (that use PRUs) are typically more robust and will require less, or no, followup prompts for refinement.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > The Announcement feature should not be hard coded.
   >
   > - Make it driven from the database.
   > - Add a button in the header that opens a dialog window. It lists all existing announcements and has controls to add/modify/delete them.
   > - Only signed in users have access to manage announcements.
   > - Announcements require an expiration date. Start date is optional.
   > - Add an example message to the database initialization.
   > - Don't worry about unit testing.
   > - Make it pretty with a good UI/UX experience.
   > ```

1. (optional) Run the application to test the changes and provide followup prompts to Copilot for further refinement.

1. (optional) Before committing the changes, ask for a local review in VS Code.

1. Commit and push the changes.

1. Create a new Pull Request with the following details.

   - **compare:** `enable-editing-announcements`
   - **target:** `main`
   - **title:** `Enable Editing Announcements`

1. Notice that Copilot was automatically added as a reviewer. Wait a moment for feedback.

1. (optional) Address any comments from Copilot.

1. Merge the pull request.

1. Nice work! You are all done, again! 🎉
