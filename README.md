# ⚡ Tabby + Gemini CLI: AI-Powered Cloud Terminal

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Coolify Supported](https://img.shields.io/badge/Platform-Coolify-blue.svg)
![Docker Compose](https://img.shields.io/badge/Build-Docker_Compose-blue.svg)
![AI Powered](https://img.shields.io/badge/AI-Gemini_CLI-orange.svg)

A high-performance, containerized terminal environment designed for engineers who need a persistent, AI-augmented workspace in the cloud. This stack seamlessly integrates **[Tabby Web](https://github.com/Eugeny/tabby-web)** with the **[Gemini CLI](https://github.com/google/gemini-cli)**, providing a sleek interface for advanced coding and infrastructure management.

## 🌟 Key Features

*   **Integrated AI Assistant:** Leverage Gemini CLI for real-time coding help, shell command generation, and technical insights.
*   **Sleek Web Interface:** Powered by the official [Tabby Web](https://github.com/Eugeny/tabby-web) for a terminal experience that feels like a native app.
*   **Tool-Heavy Backend:** Pre-configured with `wrangler`, `gh` CLI, `tmux`, and more.
*   **Persistent Environment:** Your workspace and AI authentications stay safe across deployments using Docker volumes.
*   **Secure & Private:** Designed for deployment on self-hosted instances like [Coolify](https://coolify.io).

## 🏗️ Architecture

The stack consists of three primary services:
1.  **Tabby (Web UI):** The frontend terminal interface.
2.  **Gemini Terminal:** The background tool-container where your code and CLI tools live.
3.  **MariaDB:** A robust database backend for Tabby settings and session management.

## 🚀 Quick Start on Coolify

### 1. Prerequisites
-   A running [Coolify](https://coolify.io) instance.
-   A GitHub OAuth Application (for Tabby login).
-   A Google API Key (for Gemini CLI features).

### 2. Deployment Steps
1.  Create a new **Application** in Coolify.
2.  Connect this repository and select the **Docker Compose** build pack.
3.  Configure the environment variables in the Coolify UI (see table below).
4.  **Important:** In the Coolify service settings, map your domain (e.g., `https://tabby.domain.com`) to the `tabby` service on port `80`.

### 3. Environment Variables

| Variable | Description |
| :--- | :--- |
| `COOLIFY_FQDN` | The primary domain for your Tabby instance. |
| `SOCIAL_AUTH_GITHUB_KEY` | GitHub OAuth Client ID. |
| `SOCIAL_AUTH_GITHUB_SECRET` | GitHub OAuth Client Secret. |
| `GOOGLE_API_KEY` | Your Google API Key for AI features. |
| `GH_TOKEN` | Personal Access Token for GitHub CLI. |
| `CLOUDFLARE_API_TOKEN` | API Token for Wrangler deployments. |
| `TELEGRAM_TOKEN` | Token for integrated bot alerts. |

## ⌨️ Usage

Once the stack is live:
1.  Log in via GitHub OAuth.
2.  Navigate to **Settings > Profiles & Connections**.
3.  Create a **Docker** profile and select the `gemini-terminal` container.
4.  Run the profile to enter your persistent, AI-powered coding environment.

## ⚖️ License

Distributed under the MIT License. See `LICENSE` for more information.

---
*Maintained by the cloud-native engineering community.*
