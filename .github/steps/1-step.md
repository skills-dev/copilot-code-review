## Step 1: Ask for a Review in VS Code

Mergington High School has an Extracurricular Activities website. In the last months, you have added lots of features and it has become increasingly well used by your fellow staff and students.

Now, multiple teachers want to help develop new features. This is great, but your energy is limited and if you don't have time to review changes, you fear the application will become messy. To scale your "review" availability, let's implement **GitHub Copilot code review**!

Before we implement automated code reviews with Copilot, it makes sense to try reviews locally in VS Code. This will help us better understand it, build our review criteria, and ensure all teacher-collaborators receive consistent feedback when they start contributing.

### 📖 Theory: GitHub Copilot Local Code Review

GitHub Copilot can review your code directly in VS Code, providing immediate feedback on uncommitted changes. It even adds comments similar to the feedback in a pull request! This local review capability allows developers to catch issues before they even reach version control, improving code quality from the start. And maybe catch those embarrassing typos! 😅

Key features:

- **Local analysis** of uncommitted changes
- **Code quality and style** recommendations
- **Detection** of common security vulnerabilities
- **Performance optimization** suggestions

This immediate feedback helps you identify and fix issues early in your development process, making your code more robust before it even reaches a pull request.

## ⌨️ Activity: Get to know the extracurricular activities site

Before we start developing and reviewing, let's take a moment to understand the current site.

1. Right-click the below button to open the **Create Codespace** page in a new tab. Use the default configuration.

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. Wait some time for the environment to be prepared. It will automatically install all requirements and services.

1. Validate the **GitHub Copilot** and **Python** extensions are installed and enabled.

   <img width="300" alt="copilot extension for VS Code" src="https://github.com/user-attachments/assets/ef1ef984-17fc-4b20-a9a6-65a866def468" /><br/>
   <img width="300" alt="python extension for VS Code" src="https://github.com/user-attachments/assets/3040c0f5-1658-47e2-a439-20504a384f77" />

1. Try running the application. In the left sidebar, select the **Run and Debug** tab and then press the **Start Debugging** icon.

   <img width="300" alt="run and debug" src="https://github.com/user-attachments/assets/50b27f2a-5eab-4827-9343-ab5bce62357e" />

   <details>
   <summary>🤷 Having trouble?</summary><br/>

   If the **Run and Debug** area is empty, try reloading VS Code: Open the command palette (`Ctrl`+`Shift`+`P`) and search for `Developer: Reload Window`.

   <img width="300" alt="empty run and debug panel" src="https://github.com/user-attachments/assets/0dbf1407-3a97-401a-a630-f462697082d6" />

   </details>

1. Use the **Ports** tab to find the webpage address, open it, and verify it is running.

   <img width="350" alt="ports tab" src="https://github.com/user-attachments/assets/8d24d6b5-202d-4109-8174-2f0d1e4d8d44" />

   ![Screenshot of Mergington High School WebApp](https://github.com/user-attachments/assets/5e1e7c1e-1b0e-4378-a5af-a266763e6544)

### ⌨️ Activity: Ask Copilot for a review

Let's add a simple banner feature for teachers to make announcements and then ask Copilot for feedback.

1. In VS Code, create a new branch with the following name.

   ```txt
   add-announcement-banner
   ```

1. Open the `src/static/index.html` file. Add the following after the `<body>` tag.

   ```html
   <div class="announcement-banner">
     📢 Activity registration is open until the end of the month. Don't lose your spot!
   </div>
   ```

1. Open the `src/static/styles.css` file. Add the following to the end.

   ```css
   .announcement-banner {
     background-color: #4caf50;
     color: white;
     text-align: center;
     padding: 15px;
     font-weight: bold;
   }
   ```

1. (optional) Refresh the running app to see the change.

   <img width="400" alt="screenshot of site with announcement banner" src="https://github.com/user-attachments/assets/39de7fe0-58f2-4eba-a163-d3037b2b3b06"/>

1. In VS Code, open the source control panel and ensure there are uncommitted changes.

1. Hover over the **Changes** section to show various icons. Click the **Code Review** button and wait a moment for Copilot to add comments.

   <img width="300" alt="screenshot of site with announcement banner" src="https://github.com/user-attachments/assets/6c52d550-d67b-4af9-99dd-e181695a4933"/>

   > 💡 **TIP:** There are 3 levels of review available: `unstaged changes` and `staged changes` and `uncommitted changes`

1. Expand the **Comments** panel to find a list of review feedback from Copilot.

   <img width="300" alt="screenshot of problems control panel with comments from Copilot" src="https://github.com/user-attachments/assets/64c5efb6-9071-4511-b2a2-2dc85c9e929b"/>

1. Use the **Apply** or **Discard** buttons to address Copilot's feedback.

   <img width="300" alt="screenshot of inline comment with buttons to address feedback" src="https://github.com/user-attachments/assets/aef73097-acaf-4f5b-a52f-52a142bb413f"/>

1. Commit and push the Announcement related changes to the `add-announcement-banner` branch.

1. With your changes pushed, wait a moment for Mona to check your work, provide feedback, and share the next lesson.

<details>
<summary>Having trouble? 🤷</summary><br/>

- Copilot Review in VS Code only considers uncommitted changes. Don't commit before asking for the review.
- If Copilot doesn't provide review feedback, make sure to click the correct review button for the grouping (unstaged, staged, uncommitted).
- If Copilot doesn't see your changes, make sure to save the files first.

</details>
