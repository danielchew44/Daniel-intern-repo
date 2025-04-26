Research common code smells and how they impact code quality.


Find or write code examples that demonstrate the following code smells:

Magic Numbers & Strings – Using hardcoded values instead of constants.
Long Functions – Functions that do too much and should be broken into smaller parts.
Duplicate Code – Copy-pasting logic instead of reusing functions.
Large Classes (God Objects) – Classes that handle too many responsibilities.
Deeply Nested Conditionals – Complex if/else trees that make code harder to follow.
Commented-Out Code – Unused code that clutters the codebase.
Inconsistent Naming – Variable names that don't clearly describe their purpose.

Refactor the code to eliminate these code smells.


Write reflections in code_smells.md:

What code smells did you find in your code?
Code smells are signs that something in your code might be off—not necessarily broken, but potentially leading to bugs, poor maintainability, or unnecessary complexity. Here’s a list of common ones and how they hurt your code quality:

🚨 1. Duplicated Code
Same logic scattered in multiple places.

Why it’s bad: Increases chances of bugs and inconsistencies. Fixing one copy but forgetting the others = chaos.

Fix: Apply the DRY principle—extract to functions or modules.

🧱 2. Large Functions / Classes
Functions that do too much or classes that have too many responsibilities.

Why it’s bad: Hard to read, test, and reuse. Breaks the Single Responsibility Principle.

Fix: Break into smaller, single-purpose functions or classes.

📛 3. Poor Naming
Vague or misleading variable, function, or class names.

Why it’s bad: Makes code hard to understand without deep reading.

Fix: Use clear, descriptive names that express purpose.

🔁 4. Long Parameter Lists
Functions that take too many parameters.

Why it’s bad: Hard to use and easy to mess up.

Fix: Use parameter objects or refactor into multiple functions.

🧪 5. Too Many Conditionals
Nesting if/else, switch, and ternaries deeply.

Why it’s bad: Becomes unreadable and hard to follow logic.

Fix: Use guard clauses, polymorphism, or break into smaller functions.

♻️ 6. Repetitive Comments Explaining Code
Comments that explain what code does rather than why.

Why it’s bad: Often means the code isn’t self-explanatory.

Fix: Improve naming and structure instead of relying on comments.

🔀 7. Switch or If Chains
Long chains of conditionals handling type-based logic.

Why it’s bad: Hard to extend or modify.

Fix: Use maps/objects or polymorphic design (e.g. strategy pattern).

🧪 8. Hardcoded Values (Magic Numbers/Strings)
Literal values without context.

Why it’s bad: Unclear meaning and harder to update.

Fix: Use named constants or enums.

🧩 9. Shotgun Surgery
Making a small change requires edits in many files or places.

Why it’s bad: Increases risk and effort of every change.

Fix: Group related logic together; improve cohesion.

🔄 10. Feature Envy
One class frequently accesses the internals of another.

Why it’s bad: Indicates a potential misplacement of logic.

Fix: Move the logic closer to where the data lives.

🚫 11. Dead Code
Unused functions, variables, or branches.

Why it’s bad: Clutters codebase, confuses developers.

Fix: Delete it!

⚠️ 12. Overengineering
Code is more complex than needed (e.g. patterns for simple problems).

Why it’s bad: Wastes time and makes code harder to follow.

Fix: Solve today's problems—not imaginary future ones.

🧠 Summary Table
Smell	Impact	Fix
Duplicated code	Harder to maintain	Extract functions/modules
Large functions	Hard to read & test	Split into smaller parts
Poor naming	Confusing for devs	Use meaningful names
Too many conditionals	Complex logic	Use guard clauses or refactor
Hardcoded values	Confusing, brittle	Use constants or config
Dead code	Adds noise	Delete it
Overengineering	Wastes effort, adds complexity	Keep it simple

How did refactoring improve the readability and maintainability of the code?
Refactoring improved both readability and maintainability of the code in several key ways:

🧠 1. Clearer Structure = Easier to Read
Logic is now broken into smaller, single-purpose functions.

Each block of code does one thing, and does it clearly.

You can skim function names to understand the flow, rather than reading every line.

🧼 2. Cleaner Naming = Self-Documenting Code
Renamed variables and functions now describe their purpose.

Less need for comments to explain what’s happening—names do the heavy lifting.

♻️ 3. DRY Principle = Less Repetition
Repeated logic was extracted into reusable functions.

Makes the codebase shorter and more consistent, reducing the chance of bugs.

🔍 4. Easier Debugging and Testing
Smaller functions are easier to test in isolation.

When a bug shows up, it's easier to pinpoint where it's coming from.

🔄 5. Future-Proof and Easier to Change
With a modular structure, new features or logic changes require less rewriting.

You can update one part without breaking the rest.

In short:

🛠️ Refactoring transformed cluttered, fragile code into a clean, understandable foundation that's easier to work with and grow.

How can avoiding code smells make future debugging easier?
Avoiding code smells makes future debugging faster, clearer, and less painful by reducing complexity and improving code quality. Here's how:

🧭 1. Clearer Intent = Easier to Understand
When functions, variables, and structures are well-named and purpose-driven, you spend less time figuring out what the code is supposed to do.

This helps you focus on what’s broken, not what’s confusing.

🧱 2. Smaller, Focused Functions = Narrower Scope
When bugs occur, you can trace them to a specific, small function instead of digging through a huge block of code.

This makes isolating and fixing bugs much faster.

♻️ 3. Less Duplication = Fewer Fixes
If logic is repeated in multiple places, you might fix a bug in one spot and miss others.

Refactored, DRY code means one fix updates everything consistently.

🧹 4. Fewer Dependencies = Fewer Surprises
Code smells like tight coupling or feature envy create hidden dependencies.

Clean code is more modular, so changes in one part don’t unexpectedly break another.

🪤 5. Less Nesting = Fewer Traps
Deeply nested code is harder to trace, and missing a condition can break logic silently.

Guard clauses and flattened structures reduce that risk.

🧪 6. Better Testability
Clean, smell-free code is easier to unit test, which helps you catch bugs early.

Smaller, focused components are easier to mock and test in isolation.

🧠 Summary
Code Smell Avoided	Debugging Benefit
Long functions	Easier to pinpoint errors
Duplicated logic	One fix instead of many
Poor naming	Quicker to understand what’s broken
Deep nesting	Logic paths easier to trace
Tight coupling	Fewer side effects from changes
🛠️ Clean code is like clean wiring—you can find and fix shorts without tearing the whole system apart.

Commit and push your changes to GitHub.
