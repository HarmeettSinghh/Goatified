

[![GitHub license](https://img.shields.io/github/license/HarmeettSinghh/Goatified---Leetcode-to-Github)](LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/HarmeettSinghh/Goatified---Leetcode-to-Github)](https://github.com/HarmeettSinghh/Goatified---Leetcode-to-Github/issues)
[![GitHub stars](https://img.shields.io/github/stars/HarmeettSinghh/Goatified---Leetcode-to-Github)](https://github.com/HarmeettSinghh/Goatified---Leetcode-to-Github/stargazers)


# 🐐 Goatified — LeetCode to GitHub

Save your **Accepted** LeetCode solutions to GitHub with one click — directly from your browser.

Goatified detects accepted submissions on **LeetCode.com** and **LeetCode.cn**, lets you review your solution, and commits it to your selected GitHub repository.

> **Nothing is uploaded automatically. You are always in control.**

## ✨ Features

- LeetCode.com and LeetCode.cn support
- Detects `Accepted` / `通过` submissions
- Manual **Save to GitHub** workflow
- Solution preview before upload
- Duplicate detection
- Force Update for existing solutions
- Organized problem folders
- Automatic `README.md` generation
- `metadata.json` for submission metadata
- GitHub repository selection
- Chromium Manifest V3 support

## 🧠 How It Works

```text
Solve a LeetCode Problem
          ↓
       Submit
          ↓
       Accepted
          ↓
Goatified Detects Submission
          ↓
  "Save to GitHub" Button
          ↓
     Review Solution
          ↓
    Confirm Upload
          ↓
       GitHub
```

Goatified does not automatically upload every accepted solution. You choose when a solution is saved.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| React 18 | User interface |
| TypeScript | Application development |
| Vite 5 | Build system |
| Manifest V3 | Browser extension platform |
| `@crxjs/vite-plugin` | Chrome extension integration |
| Tailwind CSS | Styling |
| Lucide React | Icons |
| GitHub REST API | GitHub operations |
| LeetCode APIs | LeetCode data and submissions |

## 📁 Project Structure

```text
Goatified/
│
├── public/
│   └── icons/
│
├── src/
│   ├── background/
│   │   └── serviceWorker.ts
│   ├── content/
│   │   ├── main.tsx
│   │   ├── App.tsx
│   │   ├── content.css
│   │   └── components/
│   │       ├── FloatingButton.tsx
│   │       ├── PreviewModal.tsx
│   │       └── Toast.tsx
│   ├── popup/
│   │   ├── index.html
│   │   ├── Popup.tsx
│   │   └── main.tsx
│   └── lib/
│       ├── types.ts
│       ├── storage.ts
│       ├── github.ts
│       ├── leetcodeDetector.ts
│       └── messaging.ts
│
├── manifest.json
├── package.json
├── package-lock.json
├── vite.config.ts
├── tailwind.config.js
├── tsconfig.json
├── README.md
└── LICENSE
```

# 🚀 Installation

There are two ways to install Goatified:

### Option 1 — Pre-Built Release

Recommended for normal users.

Download the latest release ZIP, extract it, and load the folder containing `manifest.json` into your Chromium-based browser.

You do **not** need Node.js, npm, Git, or VS Code.

### Option 2 — Build From Source

Recommended for developers and contributors.

Clone the repository, install dependencies, build the project, and load the generated `dist/` directory.

# 📦 Installing a Pre-Built Release

1. Download the latest release ZIP from the GitHub Releases page.
2. Extract the ZIP.
3. Find the folder containing `manifest.json`.
4. Load that folder as an unpacked extension.

If the release contains:

```text
Goatified/
└── dist/
    └── manifest.json
```

select the `dist/` directory.

## 🌐 Google Chrome

Open:

```text
chrome://extensions/
```

Then:

1. Enable **Developer mode**.
2. Click **Load unpacked**.
3. Select the folder containing `manifest.json`.
4. Pin Goatified from the Extensions menu if desired.

## 🌊 Microsoft Edge

Open:

```text
edge://extensions/
```

Then enable **Developer mode**, click **Load unpacked**, and select the folder containing `manifest.json`.

## 🦁 Brave Browser

Open:

```text
brave://extensions/
```

Then enable **Developer mode**, click **Load unpacked**, and select the folder containing `manifest.json`.

## 🌐 Other Chromium Browsers

Compatible Chromium-based browsers that support Manifest V3 and unpacked extensions can generally install Goatified using:

```text
Extensions
    ↓
Developer Mode
    ↓
Load Unpacked
    ↓
Select folder containing manifest.json
```

# 💻 Building From Source

## Prerequisites

- Node.js
- npm
- Git

## Clone the Repository

```bash
git clone https://github.com/HarmeettSinghh/Goatified.git
cd Goatified
```

## Install Dependencies

```bash
npm install
```

## Build

```bash
npm run build
```

The production extension will be generated inside:

```text
dist/
```

Load `dist/` through your browser's **Load unpacked** option.

# 🔐 GitHub Setup

Goatified uses a GitHub Personal Access Token (PAT) to communicate with GitHub.

A **Fine-Grained Personal Access Token** is recommended because it allows access to be limited to specific repositories and permissions.

## 🔑 Creating a Fine-Grained Personal Access Token

1. Sign in to GitHub.
2. Open **Settings**.
3. Go to **Developer settings**.
4. Open **Personal access tokens**.
5. Select **Fine-grained tokens**.
6. Click **Generate new token**.

### Token Name

Use a recognizable name such as:

```text
Goatified
```

### Description

For example:

```text
Used by Goatified to save LeetCode solutions to GitHub.
```

### Resource Owner

Select the account or organization that owns your target repository.

### Expiration

Choose an appropriate expiration period, such as 30 or 90 days.

Using an expiration is preferable to unnecessarily long-lived credentials.

### Repository Access

Select:

```text
Only select repositories
```

Then select the repository where your LeetCode solutions will be stored.

For example:

```text
LeetCode-Solutions
```

Avoid **All repositories** when it is not required.

### Repository Permissions

Under **Repository permissions**, set:

```text
Contents → Read and write
```

GitHub may also provide:

```text
Metadata → Read-only
```

Leave Metadata as read-only where applicable.

### Recommended Configuration

```text
Token name:
Goatified

Repository access:
Only select repositories

Selected repository:
Your LeetCode repository

Repository permissions:

Contents:
Read and write

Metadata:
Read-only
```

Do not grant unrelated permissions unless a specific Goatified feature requires them.

### Permissions Not Needed for Normal File Uploads

For the normal solution-saving workflow, Goatified does not need unrelated permissions such as:

```text
Administration
Actions
Deployments
Discussions
Issues
Pages
Pull requests
Secrets
Security events
Webhooks
Codespaces
```

## ⚠️ Repository Creation

Creating a repository is different from creating or updating files inside an existing repository.

If you use repository-creation functionality and GitHub reports a permission error, review the permissions required for that specific GitHub operation.

For saving solutions into an existing repository, the important permission is:

```text
Contents → Read and write
```

## Generate the Token

Click **Generate token** and copy the token immediately.

Treat it like a password.

Never:

- Share it
- Publish it
- Commit it to Git
- Put it in source code
- Put it in the README
- Include it in screenshots
- Post it in issues or pull requests

If a token is accidentally exposed, revoke it immediately and create a new one.

# 🔗 Connecting Goatified to GitHub

1. Open the Goatified extension.
2. Enter your GitHub Personal Access Token.
3. Click **Connect GitHub**.
4. Select the repository where your solutions should be stored.

# 🧑‍💻 Using Goatified

1. Open LeetCode.
2. Open a problem.
3. Write your solution.
4. Submit it.
5. Wait for `Accepted` or `通过`.
6. Goatified displays **Save to GitHub**.
7. Review the solution in the preview.
8. Confirm the upload.
9. Check your GitHub repository.

# 📂 Repository Structure

Each problem is stored in its own folder.

Example:

```text
LeetCode-Solutions/
│
├── 1_TwoSum/
│   ├── README.md
│   └── metadata.json
│
├── 20_ValidParentheses/
│   ├── README.md
│   └── metadata.json
│
├── 121_BestTimeToBuyAndSellStock/
│   ├── README.md
│   └── metadata.json
│
└── 704_BinarySearch/
    ├── README.md
    └── metadata.json
```

## 📄 README.md

Each problem README contains relevant information such as:

- Problem name
- Problem number
- Difficulty
- Problem statement
- Examples
- Constraints
- Programming language
- Runtime
- Memory
- Solution code

## 🧾 metadata.json

Each problem also receives a `metadata.json` file containing submission-related metadata.

# 🔁 Duplicate Detection

Before saving a solution, Goatified checks whether the problem already exists in the selected repository.

If it already exists, you can choose:

```text
Cancel
```

or:

```text
Force Update
```

Goatified does not silently overwrite existing solutions.

# 🔄 Force Update

Use **Force Update** when you intentionally want to update an existing solution.

Useful when you:

- Find a more efficient algorithm
- Improve time complexity
- Improve space complexity
- Rewrite a solution
- Fix an implementation

# 🧩 Code Extraction

LeetCode uses the Monaco Editor.

Because Monaco uses a virtualized DOM, directly reading visible editor elements can sometimes produce incomplete or incorrectly ordered code.

Goatified attempts to retrieve the code from the underlying Monaco editor model and uses a fallback extraction mechanism when necessary.

This helps avoid:

```text
Missing lines
```

and:

```text
Scrambled lines
```

especially for longer solutions.

# 🔒 Privacy & Security

Goatified is designed around user-controlled GitHub access.

## No Automatic Uploads

Accepted submissions are not automatically pushed to GitHub.

The workflow is:

```text
Accepted
   ↓
Review
   ↓
Save to GitHub
```

You decide which solutions are uploaded.

## Local Storage

Extension settings and credentials are stored using Chrome extension storage.

## GitHub API

GitHub requests use the Personal Access Token provided by the user.

The token's permissions are determined by the configuration selected on GitHub.

Use the smallest practical permissions and restrict the token to the repository you need.

# 🔄 Updating Goatified

For a release installation:

1. Download the latest release.
2. Extract it.
3. Open your browser's extensions page.
4. Enable Developer Mode.
5. Load the new folder containing `manifest.json`.

If the release contains `dist/`, select the `dist/` directory.

For a source installation:

```bash
git pull
npm install
npm run build
```

Then reload the unpacked `dist/` extension.

# 🧪 Testing Locally

After building:

```bash
npm run build
```

Load:

```text
dist/
```

into your browser.

Test the complete workflow:

1. Open LeetCode.
2. Open a problem.
3. Submit a solution.
4. Wait for `Accepted`.
5. Verify the Goatified button appears.
6. Review the solution.
7. Save it to GitHub.
8. Verify `README.md`.
9. Verify `metadata.json`.
10. Test duplicate detection and Force Update.

# 📜 Available Scripts

```bash
npm install
```

Install dependencies.

```bash
npm run build
```

Build the production extension.

```bash
npm run dev
```

Run the development build/watch workflow.

```bash
npm run preview
```

Preview the Vite build when applicable.

# 🐛 Troubleshooting

## Goatified Does Not Appear

Make sure:

- You are on LeetCode.com or LeetCode.cn.
- The extension is enabled.
- The correct folder was loaded.
- The selected folder contains `manifest.json`.
- You refreshed LeetCode after installing or updating.

## Load Unpacked Error

If building from source:

```bash
npm install
npm run build
```

Then load:

```text
dist/
```

## GitHub Connection Fails

Check:

- Token is correct.
- Token has not expired.
- Repository is included in the token.
- `Contents` is `Read and write`.
- Token belongs to the correct GitHub account.

## Resource Not Accessible by Personal Access Token

Check:

```text
Repository access
        ↓
Only select repositories
        ↓
Your selected repository
```

and:

```text
Repository permissions
        ↓
Contents
        ↓
Read and write
```

## Save to GitHub Button Does Not Appear

Check:

1. You are using LeetCode.com or LeetCode.cn.
2. Your solution was accepted.
3. Goatified is enabled.
4. The extension is loaded correctly.
5. You refreshed LeetCode after installing or updating.

## Uploaded Code Is Incorrect

Try:

1. Refreshing the LeetCode page.
2. Opening the problem again.
3. Confirming the complete solution is visible.
4. Submitting again.
5. Waiting for `Accepted`.
6. Saving again.

## Upload Fails

Verify the token has access to the selected repository and:

```text
Contents → Read and write
```

## Token Expired

Create a new Fine-Grained Personal Access Token with the required permissions and reconnect Goatified.

# 🤝 Contributing

Contributions are welcome.

## Fork and Clone

```bash
git clone https://github.com/YOUR_USERNAME/Goatified.git
cd Goatified
```

## Install

```bash
npm install
```

## Create a Branch

```bash
git checkout -b feature/your-feature
```

## Build and Test

```bash
npm run build
```

## Commit

```bash
git add .
git commit -m "feat: describe your change"
```

## Push

```bash
git push origin feature/your-feature
```

Then open a Pull Request.

Please provide a clear description of the change and testing performed.

# 🐛 Bug Reports

Open an issue if you discover a bug.

Useful information includes:

- Browser and version
- Operating system
- LeetCode.com or LeetCode.cn
- Problem number
- Programming language
- Steps to reproduce
- Error message
- Expected behavior
- Actual behavior

Never include GitHub tokens, passwords, API keys, or other sensitive information.

# 💡 Feature Requests

Feature requests are welcome.

Open an issue describing:

- What you want to add
- Why it would be useful
- How you expect it to work

# 🔐 Security Issues

Do not publicly expose credentials or sensitive security information.

If you discover a security vulnerability, report it responsibly.

If a GitHub token is exposed, revoke it immediately and create a replacement.

# 📦 Releases

Goatified releases contain pre-built browser extension files.

Regular users can download the release ZIP, extract it, and load the folder containing `manifest.json`.

Developers can clone the repository and build the extension from source.

# 🏷️ Versioning

Goatified uses version tags such as:

```text
v1.0.0
v1.0.1
v1.1.0
```

A typical release workflow is:

```bash
npm run build
git add .
git commit -m "release: prepare v1.0.1"
git push origin main

git tag v1.0.1
git push origin v1.0.1
```

Then create the GitHub Release and attach the built extension ZIP.

# 📄 License

Goatified is released under the **MIT License**.

See the `LICENSE` file for the complete license text.

# 👨‍💻 Author

**Harmeet Singh**

GitHub:  
https://github.com/HarmeettSinghh

Project:  
https://github.com/HarmeettSinghh/Goatified

# ⭐ Support the Project

If Goatified helps you organize your LeetCode journey, consider giving the repository a ⭐ on GitHub.

Contributions, bug reports, and feature requests are welcome.

---

# 🐐 Goatified

**Solve it. Review it. Save it.**

Keep your LeetCode journey organized in your own GitHub repository.

