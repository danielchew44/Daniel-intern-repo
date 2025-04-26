Research what CI/CD is and why it’s used in software development.

Set up a CI workflow that runs Markdown linting and spell checks on PRs in your repo.

Experiment with Git Hooks (e.g., Husky) to enforce linting before commits.

Open a test PR in your repository and review the automated checks.

Push your CI/CD configuration to your repo.

Write reflections in ci_cd_reflection.md:
What is the purpose of CI/CD?
CI/CD stands for Continuous Integration and Continuous Delivery (or Continuous Deployment). It’s a set of practices in software development that automate the building, testing, and deploying of code. Here’s what each part means:

Continuous Integration (CI):
Developers frequently (often multiple times a day) merge their code changes into a shared repository. Every time they do, automated builds and tests are run to quickly catch bugs or integration issues.
➔ Goal: Find and fix problems early, improve software quality, and reduce integration headaches.

Continuous Delivery (CD):
After code passes tests, it’s automatically prepared for release to production — but a human might still manually trigger the actual deployment.
➔ Goal: Make sure the software is always in a releasable state.

Continuous Deployment (CD, too):
(If you go a step further!) Every successful change is automatically deployed straight to users without manual approval.
➔ Goal: Release new features, fixes, and updates very quickly and reliably.

Why is CI/CD used?

Speed: It makes releasing new features and bug fixes much faster.

Reliability: Automated testing reduces human error.

Consistency: Every deployment follows the same steps, so fewer surprises.

Feedback: Developers get quick feedback on their code.

Confidence: Teams can release updates more often without worrying about breaking things.

How does automating style checks improve project quality?
Automating style checks improves project quality in a few big ways:

Consistency:
It ensures that all code looks and feels the same, no matter who writes it. Consistent code is easier to read, understand, and maintain.

Catch Small Issues Early:
Style checkers can catch things like missing semicolons, bad indentation, or poor naming practices before code is merged — preventing small mistakes from piling up.

Save Time:
Developers and reviewers don't have to waste time nitpicking code formatting during reviews. They can focus on important stuff like logic and architecture instead.

Reduce Bugs:
Some style rules (like warning about unused variables or confusing code structures) can actually prevent bugs before they happen.

Improve Collaboration:
New team members can jump in more easily when the codebase has a clear, uniform style.

What are some challenges with enforcing checks in CI/CD?
Good question — enforcing checks in CI/CD definitely has a few challenges:

Slower Pipelines:
If checks (like tests, style checks, security scans) take too long, developers might get frustrated waiting for builds to finish.

False Positives:
Sometimes tools flag harmless code, which can annoy developers and cause them to ignore or rush through real issues.

Complex Configurations:
Setting up and maintaining all the automated checks properly (especially across different environments) can get complicated.

Developer Resistance:
If checks feel too strict or petty, developers might see them as a burden instead of a help.

Keeping Tools Updated:
Style rules, security rules, and testing tools evolve. If a team doesn’t update their checks regularly, they might miss new best practices — or accidentally block good code.

Overloading the Pipeline:
Adding too many checks at once can overwhelm the system (and the developers), making it harder to diagnose why a build fails.

How do CI/CD pipelines differ between small projects and large teams?
In Small Projects:

Simple Pipelines:
A basic setup usually works — maybe just build, test, and deploy steps.

Faster Pipelines:
Less code and fewer tests mean builds run quickly.

Fewer Checks:
Might skip things like heavy security scans or multi-environment testing at first.

Light Process:
One or two developers can easily fix pipeline issues themselves without a lot of coordination.

In Large Teams or Projects:

Complex Pipelines:
Multiple stages (build, unit tests, integration tests, security scans, performance tests, deploy to staging, deploy to production).

Longer Build Times:
More code and more tests slow things down — so teams often parallelize jobs or use build caching to speed things up.

Strict Quality Gates:
Code must pass many checks before merging (style, security, code coverage, approval workflows).

Multiple Environments:
Code gets deployed to dev, QA, staging, and then production environments — with approvals between steps.

Team Roles:
Specialized roles (like DevOps engineers) maintain the pipeline; developers often can’t modify it directly without approvals.

In short:
Small projects need simple and fast pipelines. Large teams need powerful, scalable pipelines with lots of quality control built in.
