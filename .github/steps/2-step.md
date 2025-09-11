## Step 2: Get a Pull Request Review

Now that you've tested Copilot's local review capabilities and made some changes to improve the activities website, it's time to create a pull request and get Copilot's feedback on your proposed changes before they're merged into the main branch, just like one of the other teachers would. Let's see how Copilot reviews changes in the pull request process.

### 📖 Theory: Pull Request Code Reviews

GitHub Copilot analyzes your code and provides intelligent feedback with actionable suggestions you can apply instantly. Each code review consumes one [Premium Request Unit (PRU)](https://docs.github.com/en/copilot/concepts/billing/copilot-requests) from the requester.

> [!IMPORTANT]
> Use [code review responsibly](https://docs.github.com/en/copilot/responsible-use/code-review) - Copilot is trained to be familiar with many common security concerns, but it is not meant to replace dedicated security tools, guidelines, and standards. Please use of the correct tools for the job.

**Key Capabilities:**

- **Automated Analysis**: Reviews code for quality, security, and performance issues
- **Actionable Suggestions**: Provides specific recommendations with suggested code changes
- **Integration**: Works seamlessly with GitHub's native pull request flow, the same as regular peer feedback
- **Non-blocking**: Provides "Comment" reviews that don't block merging or count toward required approvals
- **Customizable**: Supports custom instructions to align with team standards
- **Secure**: Operates within GitHub's secure infrastructure

For more information, see the [GitHub Copilot code review documentation](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/request-a-code-review).

### ⌨️ Activity: Request a review

1. If needed, open another web browser tab and navigate to this exercise repository.

1. Start a new pull request. Enter the following details and click the **Create pull request** button.

   - **compare:** `add-announcement-banner`
   - **target:** `main`
   - **title:** `Add announcement banner`

1. In the right-side details area, find the **Reviewers** menu. Click on the **settings icon** to show a list of available reviewers and select **Copilot**.

   <img width="300" alt="screenshot of reviewers menu" src="https://github.com/user-attachments/assets/0f9f2e86-51b7-4542-82a1-afb6a22ab3ca"/>

1. Wait a moment for Copilot to review the changes and add comments to your pull request. Notice an entry was added to the conversation log.

   <img width="300" alt="new log entry - requested review from copilot" src="https://github.com/user-attachments/assets/3e522bda-e68e-4469-93f4-a7ad103cca97"/>

   <img width="500" alt="new log entry - copilot's PR summary" src="https://github.com/user-attachments/assets/0a870950-560e-4df8-80d5-2b93f1be99ab"/>

1. With the review requested, wait a moment for Mona to check your work, provide feedback, and share the next lesson.

<details>
<summary>Having trouble? 🤷</summary><br/>

- If Copilot doesn't appear in the reviewers list, ensure your repository has Copilot enabled
- If Copilot doesn't appear in the reviewers list, check your subscription plan. It is not available for free tier.
- Sometimes reviews take a minute or two to complete.

</details>
