# AIinTest.TestCaseGeneration

AIinTest.TestCaseGeneration is a tool that automates the creation of test cases for API, desktop, and web user stories. By leveraging GitHub Copilot, it enables testers and developers to quickly generate comprehensive test scenarios, improving both test coverage and efficiency.

## Features

- Automatically generate test cases for API, desktop, and web applications
- User story-driven test case generation
- Compatible with Azure DevOps

## Getting Started

1. **Clone the Repository**

2. **Install Dependencies**
    - [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
    - [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat)

## Usage Instructions

1. Open GitHub Copilot Chat.

2. Click on *Add Context*.

3. Select *Instructions...*, then select `azure_testcse_format`.

4. Click on *Add Context*.

5. Select *Instructions...*, then choose either `api-test-generation`, `desktop-test-generation`, or `web-test-generation`.

6.a Provide your prompt, including acceptance criteria or API details, for GitHub Copilot to use when generating test cases.

6.b If your [Azure DevOps MCP](https://github.com/microsoft/azure-devops-mcp) is configured, provide the workitem number.

7. GitHub Copilot will generate test cases under `Output` folder.

8. Once the generated test cases are verified, upload the csv to Azure DevOps.

## User/Testers Responsibilities

- Provide clear and detailed user stories, acceptance criteria, or API specifications.
- Review the generated test cases for accuracy and completeness.

## Need Project Specific Instruction?

We encourage you to fork from this repo and build your own instruction design for your product/projects. This is already great, but in some cases you want to adjust the instruction based on your special needs, feel free to fork and add or adjust the instructions as needed.

## License

This project is licensed under the MIT License.
