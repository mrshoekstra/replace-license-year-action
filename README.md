# 📅 Replace License Year Action <picture><img alt="Bash" src="https://img.shields.io/badge/Bash-4eaa25"></picture> <picture><img alt="YAML" src="https://img.shields.io/badge/YAML-cb3e35"></picture>

<!-- DESCRIPTION START -->
An automated GitHub Workflow designed for repository templates that instantly updates your license file with the current year upon instantiation. The workflow uses dynamic path resolution to safely delete itself and recursively clean up its parent directories after execution, leaving your new repository production-ready.
<!-- DESCRIPTION END -->

## 📑 Index

- ✨ [Features](#-features)
- 📋 [Prerequisites](#-prerequisites)
- 🛠️ [Installation](#️-installation)
- ⚙️ [Configuration](#️-configuration)
- 🚀 [Usage](#-usage)
- 🤝 [Contributing](#-contributing)
- 🛡️ [Security](#️-security)
- ❤️ [Support](#️-support)
- ⚖️ [License](#️-license)

## ✨ Features

- **Automated Token Replacement**: Dynamically scans and replaces the `{{YEAR}}` placeholder in your license files with the current calendar year.
- **Dynamic File Path Destruction**: Resolves its own location using runtime context (`job.workflow_file_path`), allowing the workflow file to be named arbitrarily.
- **Recursive Directory Purging**: Iteratively traverses and removes nested parent directories up to the root level if they become empty after the file is deleted.
- **Template-Safe Execution**: Employs explicit conditional guards ensuring the script never triggers within the parent template repository itself.
- **Native Git Integration**: Commits and pushes updates seamlessly using the standard GitHub Actions bot profile with a `[skip ci]` flag.

## 📋 Prerequisites

Before deploying this workflow, ensure your development environment satisfies the following conditions:
- The target repository must be configured as a GitHub Repository Template.
- A license file (e.g., `LICENSE`, `LICENSE.md`, or `COPYING`) must exist in the root directory.

## 🛠️ Installation

To integrate this automated action into your repository template, execute the following configuration steps:

1. Create the workflow directory path in your repository: `.github/workflows/`.
2. Define the automation rules by populating your workflow configuration file directly within that folder (e.g., [`.github/workflows/replace-license-year.yml`](.github/workflows/replace-license-year.yml)).
3. Commit and push the file to the default `main` branch of your template repository.

## ⚙️ Configuration

This action requires elevated write privileges to rewrite your license configuration and commit the changes back to your target branch.

> [!IMPORTANT]
> You must explicitly enable write permissions for GitHub Actions workflow tokens within your repository settings. Navigate to **Settings** › **Actions** › **General** › **Workflow permissions**, select the radio button for **Read and write permissions**, and click **Save**.

## 🚀 Usage

### 1. Prepare Your License File
Ensure your root license file references the dynamic `{{YEAR}}` placeholder instead of a static calendar year. For example:

```text
MIT License

Copyright (c) {{YEAR}} Your Name or Organization
```

### 2. Workflow Configuration
The complete GitHub Actions workflow automation matrix is stored and maintained entirely within the production-ready automation file inside your repository's `.github/workflows/` directory. Because the architecture uses dynamic file path tracking, you can organize or name the file according to your project's naming conventions.

> [!NOTE]
> The workflow appends a `[skip ci]` tag to the setup commit, preventing it from accidentally triggering subsequent test matrices or build pipelines.

## 🤝 Contributing

Contributions are welcome! If you locate an edge case with file pattern matching or have optimization suggestions for the self-destruct script, please open an issue or submit a pull request.

## 🛡️ Security

If you discover any security vulnerabilities or permission exploits related to this workflow execution pattern, please report them by opening a confidential security advisory via the repository options tab rather than utilizing a public issue tracker.

## ❤️ Support

If this project saved you some time, please consider giving it a ⭐ **Star** on GitHub; it helps others discover the repository!

If you would like to support my work further, please check out the **Sponsor this project** section on this repository page. Even a small contribution makes a big difference!

## ⚖️ License

Distributed under the [MIT License](LICENSE.md).
