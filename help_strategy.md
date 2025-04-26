Tasks

Research best practices for troubleshooting coding problems.
Spend 30 minutes talking with Chat GPT to understand different perspectives on using AI in coding. When is it helpful and when is it not?

Develop a decision-making framework:
Create a flowchart or decision tree in Miro outlining scenarios where each resource (Google, AI tools, colleagues) would be most appropriate.
Consider factors such as:
The complexity of the problem.
The sensitivity of the information.
The urgency of the task.

Export the flowchart and add it to your GitHub repo.

Write a reflection in help_strategy.md:
When do you prefer using AI vs. searching Google?
I prefer using AI when:
I need a summary or explanation fast (like “explain flaky tests” or “summarize E2E vs unit testing”).

I want step-by-step guidance or code examples without clicking through 10 blogs.

I’m exploring ideas and need a brainstorming buddy (e.g., “suggest ways to speed up flaky tests”).

I’m asking a how-to that might need tailoring to my specific situation (like “how to set up retry logic in Playwright for Windows apps”).

I want to talk through something interactively, not just find a static answer.

🌎 I prefer Google when:
I need official documentation or a trusted source (like Microsoft's WinAppDriver docs or Appium’s official site).

I’m looking for latest news or real-world troubleshooting posts (like Stack Overflow, GitHub issues, or recent blog posts).

I need to compare tools (e.g., “best test frameworks 2025” or “WinAppDriver vs Winium updated review”).

I’m looking for downloads, plugins, or setup guides (like installing Appium Inspector, SDKs, etc.).

Quick way to think of it:

"Explain it to me or help me figure it out" → AI

"Show me a source I can quote or install from" → Google

How do you decide when to ask a colleague instead?
I ask a colleague when:
Context matters:
If the question depends on how our team, our project, or our tech stack works (like “how do we set up Windows app tests in Focus Bear?”), a colleague will know the specifics way better than a general answer online.

It’s faster:
If it’ll take 2 minutes for someone to explain and 20 minutes to dig through docs — I just ask.

There might be a better internal way:
Maybe we already have a shortcut, a library, a script, or a standard we should follow that’s not public. (Especially true for things like CI/CD setups, internal tools, test environments, etc.)

I’m unsure what I’m even looking for:
Sometimes I don't even know the right search terms yet. Talking it out can help me figure out what to even ask Google or AI.

Team communication matters:
If it’s part of building good collaboration — like checking if someone already solved a problem — asking can prevent duplicate work.

🔥 Quick gut check:
"Is this about our project/team setup?" → Ask a teammate.

"Is this a general technical concept?" → Try AI or Google first.

🚨 One thing though:
I always try to make my question clear and respectful of their time — like:

“Hey, I tried looking this up but I’m stuck — can you help me with X for a minute?”

Or even stack a few quick questions together if possible so I’m not interrupting them constantly.

What challenges do developers face when troubleshooting alone?
Troubleshooting alone can be really tough — even for experienced devs. Here are the biggest challenges they usually run into:

🧩 1. Tunnel vision
When you stare at the same code, logs, or test for too long, you can miss obvious mistakes.

You get "stuck in your own head," assuming things are working that aren't.

(Ever spent an hour debugging... then realized you were on the wrong branch? Yep, that.)

🕵️ 2. Limited perspective
When you're solo, you’re limited to your current knowledge.

A teammate might spot patterns or solutions you don't even know exist yet (e.g., a known flaky test, a server config quirk, etc.).

⏳ 3. Wasted time
You can burn hours trying to find a bug that someone else could have pointed out in 5 minutes.

It's especially painful if the fix is something small (like a missing dependency or an environment setup mistake).

😖 4. Frustration and burnout
Feeling stuck without progress can be mentally exhausting.

Frustration makes it harder to think clearly, which makes solving the problem even slower — a nasty spiral.

🔍 5. Overcomplicating the solution
Alone, it's easy to assume the problem must be complex ("it must be some weird Windows internals issue!") when actually it's simple (like "oh, wrong driver version installed").

🛠️ 6. Missing tools or shortcuts
Someone else might know tools, scripts, or debug techniques you don't — saving tons of time.

Example: knowing to use WinAppDriver’s Inspector to quickly locate elements vs. manually guessing IDs.

🎯 Bottom line:
Working alone = slower diagnosis + higher stress.
Pairing or asking for help = faster, smarter troubleshooting.
