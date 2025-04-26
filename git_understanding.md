Research what causes merge conflicts in Git.

Create a merge conflict in your test repo by:
Creating a branch and editing a file.
Switching back to main, making a conflicting edit in the same file, and committing it.
Merging the branch back into main.

Use your Git desktop client to resolve the conflict.

Write about your experience in git_understanding.md:
What caused the conflict?
Github.

How did you resolve it?
By using Github.

What did you learn?
How to use Github.

Commit and push your changes to GitHub.

Research the difference between staging and committing.

Experiment with adding and committing files in your repo using either:
The terminal (git add / git commit)
A Git desktop client (e.g., GitHub Desktop, VS Code Git integration).

Modify a file and try the following:
Stage it but don’t commit (git add <file> or equivalent in your client).
Check the status (git status).
Unstage the file (git reset HEAD <file> or equivalent).
Commit the file and observe the difference.

Write a summary in git_understanding.md:
What is the difference between staging and committing?
Understanding staging vs committing is key to using Git effectively.

✅ Staging (aka "Indexing")
Think of staging as preparing a list of changes you want to include in your next commit.

When you run:

bash
Copy code
git add file.txt
you're saying, "I want to include changes from file.txt in my next snapshot."

You can stage some files, all files, or even specific lines.

🔍 Why it's useful:
You can control exactly what goes into each commit, even if you've edited a bunch of files.

📸 Committing
A commit is like taking a snapshot of the staged changes and saving it in Git's history.

When you run:

bash
Copy code
git commit -m "Add login form"
you're creating a permanent record of the currently staged changes, with a message describing them.

Commits live in your Git repo’s history and can be pushed to remote repos (like GitHub).

🎯 Summary
Stage	What it Does	Command Example
Staging	Prepares changes for commit	git add file.js
Committing	Records the staged changes	git commit -m "Your message"

Why does Git separate these two steps?
Here’s why it’s designed that way:

🧩 1. Fine-Grained Control Over What You Commit
Sometimes you edit multiple files, but you only want to commit some of those changes right now.
With staging, you can choose exactly what goes into the commit.

💡 Example: You fix a bug in app.js and tweak README.md formatting. You can stage only the bug fix first, commit it, then stage and commit the README change separately.

🔄 2. Clean, Focused Commit History
Staging helps you keep commits organized and meaningful, which is super valuable in team projects or open source.

Instead of:
commit: "misc stuff"
You can have:
commit: "Fix login bug"
commit: "Update documentation formatting"

🎯 3. Partial Commits Are Possible
You can stage part of a file, not just the whole thing.

bash
Copy code
git add -p
This lets you interactively choose which hunks (sections of code) to stage from a file — super handy when you’ve done unrelated edits in one go.

🧪 4. Safety Net
Staging acts like a buffer zone. If you accidentally git commit all changes at once, it's hard to undo. Staging gives you a checkpoint to review before finalizing.

🚀 5. Supports Advanced Workflows
In complex workflows (like rebasing, cherry-picking, or squashing commits), the staging area gives you a way to carefully control and rewrite history when needed.

When would you want to stage changes without committing?
By changing the Code.

Commit and push your changes to GitHub.

Create a new branch in your Git desktop client (e.g., GitHub Desktop, VS Code, SourceTree).

Make a small change in your repo and commit it to the new branch.

Switch back to main and check that your changes are not there.

Reflect on why teams use branches instead of pushing directly to main in git_understanding.md:
Why is pushing directly to main problematic?
Here's why:

🚫 1. No Review Process
When you push directly to main, you're bypassing code reviews.

🧠 Code reviews help catch bugs, improve code quality, and keep everyone on the same page.
Without them, mistakes can sneak in — and in prod, that's dangerous.

🔁 2. No Opportunity for CI/CD Checks
Most teams set up Continuous Integration (CI) to run tests, linters, or builds before code is merged.

🚨 If you push straight to main, you skip those automated safety nets. A typo could break the whole app.

🧨 3. Risk of Breaking Production
In many workflows, main (or master) reflects deployable code.

If you push untested or incomplete code, you might trigger a deployment — and take down production.

👥 4. Harder Collaboration
Direct pushes can lead to:

Merge conflicts that are hard to untangle

Overwritten work

Confusion over what’s changed and why

Pull requests (PRs) offer a clean way to review and merge changes collaboratively.

🕵️‍♂️ 5. Loss of Accountability and Traceability
With pull requests:

You get a discussion thread

Clear commit history

A record of what was approved, when, and by whom

With direct pushes, you lose that audit trail.

✅ Safer Workflow: Pull Requests + Branching
A common Git flow:

bash
Copy code
# Create a feature branch
git checkout -b feature/login-form

# Work, commit, and push
git push origin feature/login-form

# Then open a pull request to main
This allows:

Team review

Automated checks

Cleaner, safer merges

How do branches help with reviewing code?
A branch in Git is like a parallel universe — it lets you make changes without affecting the main branch (usually the production-ready code).

🕵️‍♀️ How Branches Make Code Review Easier
1. Isolated Work = Easier Review
When you make changes on a feature branch (feature/signup-form), reviewers can see only the differences between that branch and main.

🧠 This keeps the review focused on just what's changed, not the whole codebase.

2. Pull Requests (PRs) Come from Branches
To review code, you usually open a pull request from your branch into main.

This allows:

Inline comments on specific lines 💬

General feedback on the whole PR 📝

CI/CD to run tests on the branch before merging ✅

3. Safe Place to Experiment
Branches let you explore ideas, refactor code, or fix bugs without messing with other people’s work.

If your experiment doesn’t work, you can just delete the branch. No harm done.

4. Multiple People, No Conflicts
Team members can work on different branches in parallel, then open separate PRs for review. Git keeps their work isolated until it's ready to merge.

🧩 This avoids the “stepping on each other's toes” problem.

5. Clear History and Context
When you merge a reviewed branch:

You get a clean, atomic commit or squashed history

You preserve the PR conversation

You know why that code exists

This helps future developers understand the change.

✅ TL;DR – Branches Help Reviews by:
Benefit	Why it Matters
🎯 Focused Diff	Only shows relevant changes
👀 Pull Request Reviews	Enables inline comments and approvals
💡 Safe Experimentation	Try things without fear
🤝 Team-Friendly	Prevents stepping on toes
🧾 Historical Context	PR + branch history tells the story

What happens if two people edit the same file on different branches?
Scenario:
You and a teammate both create branches from main

You each edit file.js in different ways

Later, both of you try to merge your branches back into main

🛣️ Two Possible Outcomes:
✅ 1. Non-Conflicting Changes
If you edited different lines in the file:

Git can automatically merge the changes.

You'll see both sets of edits combined.

No drama — Git is smart about line-by-line diffs.

Example:

You added a new function at the bottom.

They fixed a typo in the header. ✅ Both changes get merged cleanly.

⚠️ 2. Merge Conflict
If you edited the same line or nearby lines:

Git will pause the merge and say:

pgsql
Copy code
CONFLICT (content): Merge conflict in file.js
You'll see the conflicting section like this:

js
Copy code
<<<<<<< HEAD
console.log("Your version of the code");
=======
console.log("Their version of the code");
>>>>>>> branch-name
You have to manually choose which version to keep, or combine them.

🛠️ How to Resolve a Merge Conflict
Open the file Git flagged.

Look for <<<<<<<, =======, >>>>>>>

Edit to remove the markers and resolve the conflict.

Stage the file:

bash
Copy code
git add file.js
Complete the merge:

bash
Copy code
git commit
Some editors like VS Code will even help you do this with buttons like "Accept Both" or "Compare Changes."

💡 Pro Tips to Avoid Painful Conflicts
Pull main often into your branch (git pull origin main) to stay up to date.

Keep branches small and short-lived.

Communicate who’s working on what.

Use pull requests so everyone knows what’s being worked on.

Commit and push your changes to GitHub.

Research the following Git commands and test them in your repo:

git checkout main -- <file> – Restore a specific file from main without affecting other changes.
git cherry-pick <commit> – Apply a specific commit from another branch without merging the whole branch.
git log – View commit history and understand how changes evolved.
git blame <file> – See who last modified each line in a file and when.

Experiment with each command in your test repo:

Modify a file, then restore it using checkout.
Commit changes on a branch, then cherry-pick one commit onto main.
Use git log to explore the commit history.
Use git blame to see past changes in a file.

Write reflections in git_understanding.md:

What does each command do?
Getting Started
bash
Copy code
git init
Initialize a new Git repo.

bash
Copy code
git clone <repo-url>
Copy a repo from GitHub (or other remote) to your computer.

📦 Staging and Committing
bash
Copy code
git add <file>         # stage one file
git add .              # stage all changes
bash
Copy code
git commit -m "Your message"
Save the staged changes with a descriptive message.

🔄 Checking Status & Changes
bash
Copy code
git status
See which files are modified, staged, or untracked.

bash
Copy code
git diff               # unstaged changes
git diff --staged      # staged but not committed
🌿 Branches
bash
Copy code
git branch             # list branches
git branch <name>      # create a new branch

git checkout <name>    # switch to a branch
git switch <name>      # (newer version of checkout)

git checkout -b <name> # create and switch to a new branch
📤📥 Pushing and Pulling
bash
Copy code
git push origin <branch>
Send your branch to the remote repo.

bash
Copy code
git pull
Fetch and merge the latest changes from the remote.

🔀 Merging & Conflicts
bash
Copy code
git merge <branch>
Merge another branch into your current one.

bash
Copy code
git merge --abort
Stop a merge if things go wrong.

🕰️ History & Logs
bash
Copy code
git log
View commit history.

bash
Copy code
git log --oneline
Clean summary of commits.

bash
Copy code
git show <commit>
See the changes in a specific commit.

🧹 Undoing Stuff (Carefully!)
bash
Copy code
git restore <file>
Discard changes in a file (not staged).

bash
Copy code
git reset HEAD <file>
Unstage a file.

bash
Copy code
git reset --hard HEAD
⚠️ Revert all changes to last commit (dangerous).

When would you use it in a real project (hint: these are all really important in long running projects with multiple developers)?
To show it to your Workmates.

What surprised you while testing these commands?
History & Logs
bash
Copy code
git log
View commit history.

bash
Copy code
git log --oneline
Clean summary of commits.

bash
Copy code
git show <commit>
See the changes in a specific commit.

Commit and push your changes to GitHub.

Research git bisect and how it helps in debugging.

Create a test scenario:
Make a series of commits in your test repo.
Introduce a bug in one of the commits.
Use git bisect to track down the commit that introduced the issue.

Experiment using your Git desktop client (or CLI if preferred).

Write reflections in git_understanding.md:
What does git bisect do?
It uses binary search to help you quickly track down when a bug was introduced — even in a repo with hundreds (or thousands) of commits.

🕵️‍♂️ When to Use It:
You know the bug exists now (in the latest commit)

You know a commit in the past where it definitely didn’t exist

git bisect walks you through the commits between those two points to find the exact one that caused the issue.

✅ Basic Usage
bash
Copy code
git bisect start
git bisect bad                # current commit is broken
git bisect good <commit>     # known good commit (from before the bug)
Then Git checks out a commit halfway between. You test it.

If it works:

bash
Copy code
git bisect good
If it’s broken:

bash
Copy code
git bisect bad
Repeat until Git finds the culprit commit.

🧪 Optional: Automate with a Test Script
If you have a script that can detect the bug automatically:

bash
Copy code
git bisect run ./test-script.sh
Git will run the script on each commit until it finds the bad one — no manual checking required.

🧼 Done? Clean Up
Once the culprit is found:

bash
Copy code
git bisect reset
This puts you back on your original branch.

📌 Example Workflow
bash
Copy code
git bisect start
git bisect bad                # HEAD has the bug
git bisect good abc123        # last good commit
# Git checks out a middle commit
# You test it manually or automatically
git bisect good/bad           # mark result
# Repeat until Git shows:
# "abc456 is the first bad commit"
git bisect reset              # back to your latest

When would you use it in a real-world debugging situation?
If you forgot something.

How does it compare to manually reviewing commits?
By comparing different Programs.

Commit and push your changes to GitHub.

Research Best practices for writing commit messages.

Explore commit histories in an open-source GitHub project (e.g., React, Node.js) and analyze good vs. bad commit messages.

Make three commits in your repo with different commit message styles:
A vague commit message (e.g., "fixed stuff").
An overly detailed commit message.
A well-structured commit message.

Write reflections in git_understanding.md:
What makes a good commit message?
Anatomy of a Good Commit Message
bash
Copy code
<type>: <short summary in imperative mood>

<body (optional)>
<explains what/why, not how>

<footer (optional)>
<e.g., links to issues, co-authors, breaking changes>
✅ Best Practices
1. Use the imperative mood
🟢 Good: fix login form validation
🔴 Bad: fixed login form validation

💡 Why? It reads like a command:

"If applied, this commit will fix login form validation."

2. Keep the summary under 50 characters
Short and to the point.

Think of it like an email subject line.

bash
Copy code
feat: add password strength meter
3. Wrap the body at 72 characters
Optional, but helpful for readability in terminals, logs, and Git tools.

4. Explain the "why," not just the "what"
Instead of:

matlab
Copy code
fix bug in dashboard
Write:

vbnet
Copy code
fix: correct off-by-one error in chart rendering

Chart would misalign labels due to index shift after sort().
5. Use conventional commit prefixes (optional but great for automation)
Type	Meaning
feat	New feature
fix	Bug fix
docs	Documentation only
refactor	Code change (no feature/bug)
test	Adding or fixing tests
chore	Build process, tooling, etc.
These make it easier to:

Generate changelogs automatically

Trigger actions (e.g. CI on feat)

Group commits meaningfully

6. Use git commit --verbose or a template
To help remember the format and include details when necessary.

7. Squash commits before merging
If your PR has tons of "WIP" or "oops" commits, squash them into logical units before merging to keep history clean.

🛠 Example Commit
bash
Copy code
feat: add search input to navbar

Implements a new search input in the top navbar using Tailwind.
Currently filters local state; backend filtering will come later.

Related to #42.

How does a clear commit message help in team collaboration?
Here’s how clear commit messages make collaboration way smoother:

👀 1. Quickly Understand the History
When commits are clear, you can:

Skim git log and know what happened at a glance

Identify which commit added a feature or fixed a bug

Spot changes relevant to a current issue you're working on

Compare:

❌ commit: changed stuff

✅ fix: correct redirect logic for unauthenticated users

🔍 2. Simplifies Code Reviews
If the reviewer can read your commit message and know:

What the change does

Why it was made

If it’s related to a bug or ticket

...they’ll spend less time guessing and more time giving meaningful feedback.

Bonus: It’s easier to leave comments per commit when the commits are clean and focused.

🧑‍🏭 3. Better Collaboration in Tools
In tools like GitHub, GitLab, or Bitbucket:

Good messages become automatic changelog entries

You can link commits to issues or pull requests (fixes #42)

CI/CD systems can trigger actions based on commit prefixes (e.g., feat, fix)

🧹 4. Easier Debugging & Blame
When tracking down bugs with git log or git blame, a clear commit message helps you know:

Whether a change is relevant to the bug

Whether to revert it

Who to talk to for context

If you see a commit that just says update, you're in for a long day.

🧠 5. Encourages Better Thinking
Writing a thoughtful message forces you to reflect on what your commit really does. That often leads to better-organized commits and fewer "oops" moments.

TL;DR — Why It Matters in Teams
💬 Clear Commit Messages Help You...	👥 And Help Your Team...
Know what each commit does	Understand your work faster
Trace bugs and features	Debug without guesswork
Communicate through the codebase	Review more efficiently
Automate workflows (changelogs, CI)	Build a reliable process
Stay consistent and professional	Ship faster and with more trust

How can poor commit messages cause issues later?
Here’s how poor commit messages can cause issues:

🚧 1. Difficult to Trace Bugs
When you’re debugging, a lack of context in commit messages makes it hard to know:

When a bug was introduced

What specific change caused it

Why a decision was made in the code

Example: If you’re using git bisect and the commit message just says "fixed a bug," you’ll waste a lot of time digging through the code to figure out what actually changed.

📉 2. Time-Consuming Code Reviews
Poor commit messages mean the reviewer has to:

Guess what the change does

Understand the intention behind it

Look at every line of the commit to make sure everything is right

Example: If a commit message says “fixed stuff,” the reviewer has to check every line to figure out the context, wasting valuable time that could be spent on higher-level feedback.

🛑 3. Hard to Roll Back or Revert Changes
When you want to revert a commit or undo a problematic change, unclear commit messages can make it hard to decide what’s safe to revert.

Example: Imagine you need to roll back a bug introduced in a commit but the message just says “made changes,” making it unclear what those changes were.

🧳 4. Lost Context Over Time
As projects grow and evolve, developers change, and more features are added. A poor commit message lacks historical context, making it hard for new team members (or even future-you) to:

Understand why a particular change was made

Know if a fix is still relevant today

Example: A commit that just says “update” doesn’t explain whether the update was critical or just an arbitrary change, and its relevance may not be clear months or years later.

🧩 5. Merge Conflicts Are Harder to Resolve
In teams, conflicting commits can happen. When you have a poor commit history, understanding what happened in each commit becomes harder, making it more difficult to:

Understand the root cause of a conflict

Decide how to merge the changes

Example: If commit messages are vague, you might struggle to figure out which changes should be kept in case of conflicting updates to the same functionality.

🔄 6. Inconsistent Changelog Generation
If you're relying on automated tools or scripts to generate changelogs or release notes, vague or inconsistent commit messages can lead to:

Inaccurate changelogs

Missing important details about what changes were made in a release

Example: If commit messages are inconsistent or don't follow a standard format (e.g., feat:, fix:), automated changelog generation will produce a less useful or misleading changelog.

⏳ 7. Increased Onboarding Time for New Developers
New team members depend on clear commit messages to understand the history of the codebase quickly. If they have to spend extra time figuring out what each commit does, onboarding is slower and more frustrating.

Example: A new developer might not know if a change was made to address a bug, implement a new feature, or refactor existing code — slowing down their learning process.

🚀 8. Decreased Team Efficiency
When the team has to spend extra time understanding poor commit messages or re-doing work because they weren’t clear on previous changes, overall efficiency drops.

Example: If a commit message says "fixed issue," and it turns out the bug wasn’t fixed correctly, someone may have to spend extra time doing the fix again.

📝 TL;DR: Problems Caused by Poor Commit Messages
Issue	Impact
Debugging is harder	Takes longer to find bugs and regressions
Code reviews slow down	More time spent guessing and checking
Reverts become risky	Harder to safely undo problematic changes
Context is lost over time	New team members struggle to understand decisions
Merge conflicts are harder to resolve	Conflicts take longer to understand and fix
Changelog generation is inaccurate	Missing or incorrect changelogs
Onboarding slows down	New developers spend more time deciphering code history
Team efficiency decreases	More rework and frustration

Commit and push your changes to GitHub.

Research what a Pull Request (PR) is and why it’s used.

Create a new branch in your Git desktop client.

Make a small change and push the branch to GitHub.

Open a Pull Request on GitHub:
Add a meaningful PR title and description.
Link to a related issue (if applicable).

Review an existing PR in a public open-source repo (e.g., React PRs):
Read through comments and discussions.
Observe how changes are requested and approved.

Write reflections in git_understanding.md:
Why are PRs important in a team workflow?
Because A Pull Request (PR) is a way to propose changes you've made in a separate branch of a codebase to be merged into another branch, typically the main one (like main or develop). It’s most commonly used in collaborative development workflows on platforms like GitHub, GitLab, and Bitbucket.

Here's a quick breakdown of what happens in a PR:

Create a branch: You make changes in a dedicated branch.

Push the branch: You push it to a remote repository.

Open a PR: You open a pull request asking to merge your changes into the main branch.

Review: Teammates review the code, suggest or request changes.

Merge: Once approved, the code gets merged into the target branch.

What makes a well-structured PR?
A well-structured Pull Request (PR) makes it easy for reviewers to understand, test, and approve your changes. Here’s what makes a PR strong and reviewer-friendly:

✅ 1. Clear Title
Be specific and concise.

Example: Fix bug in login redirect for expired sessions

✅ 2. Descriptive Summary
Include the what, why, and optionally how:

What: What does this PR change?

Why: Why was this change needed?

How: How was the change implemented (only if not obvious)?

Example:

shell
Copy code
### What
Adds client-side validation to the signup form.

### Why
Users were submitting incomplete forms, causing server errors.

### How
Introduced a `validateForm()` function that checks required fields before submission.
✅ 3. Screenshots or GIFs (for UI changes)
Helps reviewers visualize changes.

Bonus: add before/after comparisons.

✅ 4. Linked Issues
Reference related issues using Closes #123 or Fixes #456 to automatically close them when merged.

✅ 5. Small, Focused Changes
Keep your PR focused on a single task/feature.

Avoid combining unrelated changes in one PR.

✅ 6. Test Coverage
List any new or updated tests.

Mention how you manually tested the change, if relevant.

✅ 7. Checklist (optional but helpful)
A standard checklist shows readiness:

css
Copy code
- [x] Tested on multiple screen sizes
- [x] Added/updated unit tests
- [x] Linted and formatted
- [x] No console errors
✅ 8. Tag Reviewers
Add relevant team members who should review the code.

Assign labels (e.g., bug, enhancement, needs review) for clarity.

What did you learn from reviewing an open-source PR?
Making a Branch.

Request feedback on your PR from a peer or mentor.

Merge the PR (if approved) and delete the branch.
