---
theme: seriph
background: default
title: Claude Code - AI-Powered Development
info: |
  ## Claude Code: Revolutionizing Software Development

  A comprehensive guide to Claude Code - Anthropic's AI-powered coding assistant

  Features, setup, best practices, and real-world examples
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Claude Code
## A brief introduction* to the beautiful world of coding agents


<div class="absolute bottom-10 right-10 text-sm opacity-60">
  <em>* These slides where vibe-coded today at 2:00 AM with Claude Code itself + Slidev 🌙</em>
</div>

---
layout: center
transition: slide-up
---

# *Proof


<div class="text-center">

<div class="text-center">
<img src="/images/2am.png" alt="2AM coding session" class="mx-auto rounded-lg shadow-lg" style="max-height: 100px;" />
</div>

<div class="text-center mt-8 ">
<img src="/images/prompt.png" alt="Claude Code prompt" class="mx-auto rounded-lg shadow-lg" style="max-height: 300px;"/>
</div>

</div>

---
layout: two-cols
transition: fade
---

# What is Claude Code?


A **command-line coding assistant** that understands your codebase, remembers your changes and creates plans.

It can work autonomously for hours, if you let it.
Unless you get ratelimited, ofc. Because this thing consumes A LOT of tokens.

But limits reset every 5h, thankfully. Or you can just upgrade to the $200/month max plan.

Remember to treat it like a junior dev: always inspect the diff and make sure it cannot do any real harm.

::right::

<div class="ml-4">

## Core Capabilities

- 📝 **Feature Building** - It creates a plan to gather context and apply code changes
- 🐛 **Debugging** - Runs tests, understands the errors, applies fixes
- 🗺️ **Project Navigation** - Understand and navigates project structure
- 🔧 **Direct Integration** - Works with existing development tools (VSCode)

</div>

<div class="absolute bottom-10 right-10 text-sm opacity-60">
  <em>* </em>
</div>

---
transition: slide-right
---

# Claude Code vs traditional ChatGPT Ctrl+C/V or Copilot

<div class="grid grid-cols-3 gap-8 mt-8">

<div>

## ChatGPT Ctrl+C/Ctrl+V
- Manual copy and paste of the context
- Time-consuming debugging
- Context switching between browser and code
- No agentic mode

</div>

<div>

## Copilot Tab completion
- Limited Context-aware suggestions
- No planning capabilities (search the web, look around the codebase...)
- Often in the way when writing normal code

</div>

<div>

## Claude Code
- Automatic context selection
- Makes coordinated changes across multiple files
- Uses your test suites and build systems
- Asks for permission to run bash commands
- Adapts to your coding standards and patterns

</div>

</div>

<div class="mt-8 text-center">
<span class="text-lg text-blue-500">"Claude works best when given clear context and specific goals"</span>
</div>

---
transition: slide-up
---

# Quick Setup

<div class="grid grid-cols-2 gap-8">

<div>

## Requirements
- Node.js 18 or newer
- Claude.ai account w/ Pro or Max plan

## CLI Installation

```bash
# Install globally
npm install -g @anthropic-ai/claude-code

# Navigate to your project
cd your-awesome-project

# Start Claude Code
claude
```

</div>

<div>

## VS Code Integration

### Extension Features
- **Code selection context** - select code to provide context
- **Diff viewer** - see changes directly in VS Code
- **Keyboard shortcuts** - push code to Claude for review
- **Tab awareness** - knows about your open files

### Installation
1. Install from [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code)
2. Requires separate Claude Code CLI installation
3. VS Code 1.98.0 or higher


</div>

</div>

---
transition: slide-down
---

<div class="mt-8">

# Common Workflows with Subagents
- **Understand new codebases**: Ask broad questions about architecture, then dive into specifics
    - `> give me an overview of this codebase`
    - `> explain the main architecture patterns used here`
- **Code analysis**: Find relevant files, trace execution flows, identify issues
    - `> find the files that handle user authentication`
    - `> trace the login process from front-end to database`
- **Bug fixing**: Let claude help you debug problems
    - `> I'm seeing an error when I run npm test`
    - `> update user.ts to add the null check you suggested`
- **Refactor Code**: apply consistent changes to improve the codebase
    - `> suggest how to refactor utils.js to use modern JavaScript features`
    - `> run tests for the refactored code`
</div>

---
transition: slide-down
---

# Workflow Evolution Patterns

<div class="grid grid-cols-3 gap-6">

<div class="p-4 border rounded">

## Beginner
- Direct task prompting
- Single conversation sessions
- Manual file editing
- Basic debugging requests

</div>

<div class="p-4 border rounded">

## Intermediate
- **Living document** methodology
- Context management with CLAUDE.md
- Multi-session planning
- Visual iteration with screenshots

</div>

<div class="p-4 border rounded">

## Advanced
- **Collaborative design partner** approach
- Parallel subagent workflows
- Custom command development
- Multi-agent system implementations

</div>

</div>

<div class="mt-8 text-center">
<span class="text-lg font-semibold text-purple-600">"AI can serve as a collaborative partner in the design process"</span>
</div>

---
layout: two-cols
transition: slide-up
---

# Best Practices

## 📝 CLAUDE.md
- Include code style guidelines, run scripts/tests
- Structured in bullet points and markdown headers
- Treated as authoritative system rules
`/init` to explore the codebase and create ./CLAUDE.md
- `# Remind this` to add to memory
    - `/memory` to directly edit it with
- Recursive priority:
  1) $CWD/CLAUDE.md
  2) ../$CWD/CLAUDE.md (until root folder)
  3) ~/.claude/CLAUDE.md (general)


::right::

<div class="text-sm">

## 🎯 Misc Tips
<div class="text-s leading-tight space-y-1">

- **Course correct early** `(ESC)` and often
- Use `/clear` to keep context focused
- `shift+tab` to auto accept code changes
- Plan mode for read only operations
- Use git worktrees to avoid catastrophes

</div>

## 🚀 Advanced Techniques
<div class="text-s leading-tight space-y-1">

- MCP integration (e.g. for Drive, Jira...)
- Headless mode for automation
- **Subagents** for parallel processing
- ⚠️ `claude --dangerously-skip-permissions` ⚠️
- `/hooks`
- Unix approach
    - `cat build-error.txt | claude -p 'explain this build error' > output.txt`

</div>

</div>

---
transition: fade
---

# ❌ Common Pitfalls

<div class="grid grid-cols-2 gap-8">

<div>

- Vague or ambiguous requests
- Skipping human code review
- Over-relying without understanding changes
- Poor context management

</div>

<div>

- Ignoring existing project conventions
- Complex multi-agent setups initially
- Assuming AI knows your preferences

</div>

</div>
---
transition: slide-left
---

# Subagents: Specialized AI Assistants

<div class="grid grid-cols-2 gap-8">

<div>

## What are Subagents?
- **Specialized AI assistants** with unique expertise
- **Separate context windows** to preserve main conversation
- **Custom system prompts** and tool permissions
- **Proactive delegation** based on task descriptions

## Creating Subagents
```bash
# List existing subagents
/agents

# Create a new subagent
/agents create code-reviewer
```

</div>

<div>

## Common Subagent Examples

### Code Reviewer
```
Expert code review specialist. Proactively
reviews code for quality, security, and
maintainability.
```

### Debugger
```
Debugging specialist for errors, test
failures, and unexpected behavior.
```

### Data Scientist
```
Data analysis expert for SQL queries,
BigQuery operations, and data insights.
```

</div>

</div>

---
transition: slide-left
---

# Claude Code Router & Model Options
Router requests to other models, rather than Sonnet/Opus

<div class="grid grid-cols-2 gap-8">

<div>

## Claude Code Router
- **Dynamic model routing** across providers
- Support for OpenRouter, DeepSeek, Ollama, Gemini
- **Custom routing logic** via JavaScript
- **GitHub Actions integration**
- On-the-fly model switching

## Setup
```bash
npm install -g @musistudio/claude-code-router
```

</div>

<div>

## GLM-4.5, a cheaper alternative
- **$3/month** GLM Coding Plan
- **355B parameters** (32B active)
- **128k token context**


## vLLM, Qwen3-Coder-480B
- It runs on our infra
- Free (?)
- Need to actually test it to see if it works

</div>
<div>



</div>

</div>

---
transition: slide-right
---

# Let's see how well he does the backend challenge

### Instructions I received ~2 years ago from Angela

<div class="text-xs mt-0 pt-0">
Your company is behind an online forum about cooking. The users need to register into it providing their email, password, some basic profile info, and then perform a safe login. In order to increase the safety of the login process, a user can enable the 2FA at the registration step to receive at the provided email a random OTP needed to complete the flow. To reduce the complexity of the assignment (if you want) you can use as Email Sender component a fake implementation that simply logs on the stdout the OTP rather than send the email for real.
You’re responsible to design a backend service and to actually code it in Python. You must version this project with git and provide a public URL where we can check your solution. Please don’t put any reference to our company inside the repository.

Some constraints:

provide a README.md file with clear instructions about how we can test your service in a local development environment;

the communication protocol will be HTTP. We expect one route to register users, a second route to allow them to log in and a third to use in case the 2FA is enabled. You’re free to design as you like, but you’re asked to provide documentation for all of the endpoints;

this service will operate inside a micro-services architecture and must be shipped inside a docker image, in order to be deployable in the cloud;

we expect you to write automated tests for your project.

Avoid using a library to generate the otp

the session must be managed via stateless authentication with JWT
</div>

---
transition: slide-down
---

# Demo: Live Development

<div class="grid grid-cols-2 gap-8">

<div>

## Commands to Try

```bash
# Planning mode
/think hard

# Execution modes
claude --auto-edit
claude yolo

# Context management
@filename.py
/clear

# Subagents
!subagent product-manager
!subagent senior-engineer
```

</div>

<div>

## Expected Output
- **Comprehensive planning** document
- **Step-by-step implementation**
- **Test coverage** creation
- **Error handling** implementation
- **Documentation** updates

<div class="mt-4 p-4 bg-yellow-100 dark:bg-yellow-900 rounded">
⚡ Demo: Claude Code building a feature from requirements to implementation
</div>

</div>

</div>

---
layout: center
class: text-center
transition: fade
---

# Questions ???

<div class="mt-8">

```bash
npm install -g @anthropic-ai/claude-code
cd your-project
claude
```

</div>

<div class="mt-12 grid grid-cols-3 gap-8">

<div>

## 📚 Learn More
- [Official Documentation](https://docs.claude.com/en/docs/claude-code)
- [Best Practices Guide](https://www.anthropic.com/engineering/claude-code-best-practices)
- [Design Partner Approach](https://betweentheprompts.com/design-partner/)
- [How Anthropic Teams Use Claude Code](https://www.anthropic.com/news/how-anthropic-teams-use-claude-code)

</div>

<div>

## ✍️ Blog Posts
- The best out of CC [PT-1](https://tokenbender.com/post.html?id=how-i-bring-the-best-out-of-claude-code), [PT-2](https://tokenbender.com/post.html?id=how-i-bring-the-best-out-of-claude-code-part-2)
- [Getting Good Results](https://www.dzombak.com/blog/2025/08/getting-good-results-from-claude-code/)
- [Parallel Subagents](https://zachwills.net/how-to-use-claude-code-subagents-to-parallelize-development/)
- [Six Weeks with Claude Code](https://blog.puzzmo.com/posts/2025/07/30/six-weeks-of-claude-code/)
- [Decoding Claude Code](https://minusx.ai/blog/decoding-claude-code/)
- [Claude Code Is All You Need](https://dwyer.co.za/static/claude-code-is-all-you-need.html)
- [Modernizing a 25 y/o Driver](https://dmitrybrant.com/2025/09/07/using-claude-code-to-modernize-a-25-year-old-kernel-driver)
- [1st Try Will Be 95% Garbage](https://www.sanity.io/blog/first-attempt-will-be-95-garbage)


</div>

<div>

## 🛠️ Tools
- [Terminal Benchmark Leaderboard](https://www.tbench.ai/leaderboard)
- [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code)
- [Usage Monitor](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor)
- [Claudia - Desktop App](https://claudia.so/)
- [Claude Code Router](https://github.com/musistudio/claude-code-router)

</div>

</div>

<div class="mt-4">
<span class="text-xl">Try Claude Code in your next project! <--- Cringe generated by Claude Code itself</span>
</div>

---
# Link to the slides

<div class="text-center">
<span class="text-xs">Slides will be available at:</span><br>
<a class="text-xs">https://cheap-bitcoin.online/var/log/journal/remote/commit_hash/etc/opt/chrome/policies/callback/opt/libreoffice/program/synchronous/etc/opt/chrome/policies/exception/usr/include/krb5/driver/usr/libexec/polkit-1/virtual_machine/etc/lightdm/lightdm.conf.d/callback/var/lib/dpkg/info/graph/etc/ppp/ip-down.d/binary_tree/etc/systemd/logind.conf.d/while/etc/security/faillock.conf.d/public_key/usr/local/etc/rc.d/semaphore/opt/vmware/lib/orchestration/usr/local/lib/python3.11/dist-packages/normalization/fake_flash_update.exe?auth=bypass&certificate=revoke&cookie=sniff&dns=spoof&endpoint=exploit&file=overwrite&form=spoof&header=spoof&id=4b2ea23fbde2acfd2b37394d95ba2554903e8a6b9070e17a93139c38&method=spoof&password=inject&payload=%28function%28%29%7B+return+%27xy%27%5B0%5D%3B+%7D%29%28%29%3B&portscan=exploit&proxy=tamper&redirect=spoof&redirecturi=spoof&referer=tamper&request=forge&ssl=sniff&token=steal&url=poison&user=steal&useragent=inject</a>
</div>