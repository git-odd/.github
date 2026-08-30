<div align="center">

# 🐙 git-odd

A suite of native Git subcommand extensions for specific engineering workflows.

[![Organization](https://img.shields.io/badge/Org-git--odd-blue?style=flat-square&logo=github)](https://github.com/git-odd)
[![Ecosystem](https://img.shields.io/badge/Ecosystem-Git%20Extensions-green?style=flat-square&logo=git)](https://github.com/git-odd)
[![License](https://img.shields.io/badge/License-MIT%20%2F%20Apache--2.0-orange?style=flat-square)](LICENSE)

</div>

### Motivation

Standard Git workflows cover most common scenarios, but developers often face efficiency bottlenecks in specific situations:

*   Relying on cloud-based LLMs to generate commit messages introduces issues with latency, privacy, and accuracy.
*   A project might contain private assets (like notes or local configurations) that need to be synchronized within a team but are not suitable for public repositories.
*   There's a frequent need to save temporary snapshots during development without polluting the main branch's history with commits like `wip` or `temp`.

`git-odd` aims to provide a suite of standalone solutions for these scenarios, designed to feel like native Git commands.

### The Suite

| Tool | Core Purpose | Use Case | Key Features |
| :--- | :--- | :--- | :--- |
| [**`git-msg`**](https://github.com/git-odd/git-msg) | A local-first, AI-assisted commit message generator. | Automating the generation of conventional commit messages while prioritizing privacy and speed. | ⚡ Optimized for small, local models (<1s generation)<br>🛡️ Automatic redaction of sensitive credentials<br>🧩 Smart diff truncation and untracked file detection |
| [**`git-vault`**](https://github.com/git-odd/git-vault) | Manages public and private assets separately within a single project. | Separating public code from private assets (docs, keys) in the same project and syncing them to different remotes. | 🔒 Managed automatically via `.vaultignore` rules<br>🔄 Seamless synchronization using Git Hooks<br>📦 Completely transparent to the public repository |
| [**`git-chkpt`**](https://github.com/git-odd/git-chkpt) | A non-intrusive workspace snapshot tool. | Providing a temporary snapshot mechanism that is easier to manage than `git stash` and does not pollute the commit history. | ⏱️ One-command creation and restoration of snapshots<br>🌳 Stored independently, leaving the Git tree untouched<br>⚡ Fast diffing between snapshots |

### Design Principles

**Native Subcommand Experience**
Each tool functions as a standard `git <name>` subcommand, integrating seamlessly into existing workflows and terminal muscle memory.
  
**Local-First and Privacy-First**
Core functionalities operate locally without relying on unauthorized cloud services, ensuring the privacy of your code and data.

**Complex Implementation, Simple Interface**
We handle complex low-level logic (like diff parsing and hook management) to provide a clean and intuitive user interface.

<br>
<br>
<div align="center">

*Crafted with 🦀 Rust and weird ideas by **[plasma-blue](https://github.com/plasma-blue)** & Gemini.*  
*If it's odd, but it works, it's not odd.*

</div>
