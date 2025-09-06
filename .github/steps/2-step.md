## Step 2: Get a Pull Request Review

Now that you've tested Copilot's local review capabilities and made some changes to improve the activities website, it's time to create a pull request and get Copilot's feedback on your proposed changes before they're merged into the main branch, just like one of the other teachers would. Let's see how Copilot reviews changes in the pull request process.

### 📖 Theory: GitHub Copilot Pull Request Reviews

GitHub Copilot analyzes your code and provides intelligent feedback with actionable suggestions you can apply instantly. Each code review consumes one Premium Request Unit (PRU) from the requester.

> [!IMPORTANT]
> Use [code review responsibly](https://docs.github.com/en/copilot/responsible-use/code-review) - It is familiar with many common security mistakes, but it is not meant to replace dedicated security analysis tools. Use the right tool for the job.

**Key Capabilities:**

- **Automated Analysis**: Reviews code for quality, security, and performance issues
- **Actionable Suggestions**: Provides specific recommendations with suggested code changes
- **Integration**: Works seamlessly with GitHub's native pull request flow, the same as regular peer feedback
- **Non-blocking**: Provides "Comment" reviews that don't block merging or count toward required approvals
- **Customizable**: Supports custom instructions to align with team standards
- **Secure**: Operates within GitHub's secure infrastructure

For more information, see the [GitHub Copilot code review documentation](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/request-a-code-review).

### ⌨️ Activity: Request a review

1. In VS Code, create a new branch and add another feature to the activities website without doing a local review first
1. Push your changes to GitHub
1. Navigate to your repository on GitHub.com and start a new pull request
1. In the pull request, click on the **Reviewers** menu in the top right
1. Select **Copilot** from the list of available reviewers
1. Wait a moment for Copilot to review the changes
1. Review Copilot's suggestions and comments on your pull request

> [!TIP]
> You can also use the GitHub CLI to assign Copilot as a reviewer!
>
> ```bash
> gh pr edit <PR_NUMBER> --add-reviewer "@copilot"
> ```

### ⌨️ Activity: Request another review

1. Based on the existing sample project, make some intentional changes that might trigger feedback:
   - Add some typos or unconventional variable naming
   - Introduce some grammar mistakes in comments
   - Add a coding pattern that could be improved
1. Push these changes to your branch
1. In the pull request reviewers menu, click the refresh icon next to Copilot's name to request a new review
1. Wait for Copilot to share additional comments on the pull request
1. Compare the new feedback with previous suggestions to see how Copilot adapts

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you have a GitHub Copilot subscription - code reviews require a paid plan
- If Copilot doesn't appear in the reviewers list, ensure your repository has Copilot enabled
- Sometimes reviews take a minute or two to complete - be patient
- You can request multiple reviews on the same pull request by clicking the refresh icon

</details>
