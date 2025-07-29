# 🚀 GitHubCopilot-Test-Generation

**Supercharge your testing workflow with AI-powered test case creation.**

GitHubCopilot-Test-Generation is a lightweight yet powerful tool designed to **automate test case generation** for API, desktop, and web applications — all using natural language prompts and GitHub Copilot. Whether you're a tester, QA engineer, or developer, this tool helps you **save time, boost test coverage, and bring joy back to testing**.

> ✨ No more writer’s block when creating test cases. Let Copilot do the heavy lifting, while you focus on quality.

---

## 🔧 Features

* 🧠 **AI-Powered Test Generation** – Turn acceptance criteria into actionable test cases with GitHub Copilot.
* 🌐 **Supports API, Desktop, and Web Testing** – Works across different tech stacks and platforms.
* 📋 **User Story-Driven** – Just provide your user story or work item, and Copilot takes care of the rest.
* ☁️ **Azure DevOps Compatible** – Generate test cases and upload them directly as CSV for seamless integration.

---

## ⚡ Getting Started

1. **Clone this repository**
   * You may refer to [How to Clone a GitHub Repository](./HowTo-CloneRepo.md) for guidance.

2. **Install the essentials**

   * [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
   * [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat)

---

## 🧪 How to Use It

1. Open **GitHub Copilot Chat**.
2. Make sure you select the `Agent` mode.
3. For a better output, we recommend using `Claude Sonnet 4` model
4. Click on **"Add Context"**.
5. Under **Instructions**, select one of the following based on your preferred format:
   * `azure_testcase_format_steps.instruction.md` – for regular test cases with test steps and expected results.
   * `azure_testcase_format_gherkin.instructions.md` – for Gherkin-style test cases using the Given-When-Then format.
6. Add a second context:
   * Choose `api-test-generation`, `desktop-test-generation`, or `web-test-generation`.
7. Enter your prompt:

   * 📜 Paste acceptance criteria or user story
   * 🔢 Or simply provide the work item number (if using [Azure DevOps MCP](https://github.com/microsoft/azure-devops-mcp))
7. Copilot will auto-generate test cases in the `Output` folder.
8. Review, refine, and upload the `.csv` file to Azure DevOps.

---

## ✅ Your Role as a Tester

* ✍️ Provide **clear** user stories, API specs, or acceptance criteria.
* 👀 **Review and validate** the output to ensure it fits your product’s needs.
* 🛠️ Customize and contribute! Build your own prompts if needed.

---

## 💡 Want Project-Specific Instructions?

Every project is unique. While this repo gives you a solid head start, we **encourage you to fork and tailor it** for your specific testing needs. Build instructions that match your product’s personality and complexity!

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
Feel free to use, modify, and spread the word!

---

Let GitHub Copilot help you **test smarter, not harder.**
🔥 Give it a try today and watch your test cases write themselves.
