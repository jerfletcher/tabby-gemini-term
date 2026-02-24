# Tabby + Gemini CLI: Cloud-Native Terminal coding Agent

A professional, containerized terminal coding environment designed for seamless deployment on **Coolify**. This stack provides a persistent, tool-heavy workspace powered by **Gemini CLI**, accessible through the sleek **Tabby Web** interface.

## 🚀 Overview

This repository provides a multi-container Docker Compose stack that includes:
- **Tabby Web:** A high-performance web-based terminal emulator.
- **Gemini Terminal:** A specialized Node.js environment pre-loaded with:
    - `gemini-cli`: AI-powered coding assistance.
    - `wrangler`: For Cloudflare Workers and Pages management.
    - `gh`: GitHub CLI for repository management.
    - `tmux`, `git`, and other essential CLI tools.
- **MariaDB:** High-performance database for Tabby's session and configuration persistence.

## 🛠️ Integrated Tools

The environment is pre-configured with access to:
- **Cloudflare (Wrangler):** Manage edge deployments directly from your terminal.
- **Coolify API:** Programmatically interact with your self-hosted infrastructure.
- **GitHub CLI:** Seamless private repo access and PR management.
- **Telegram:** Integrated bot notifications and alerts.

## 📦 Deployment on Coolify

1. **Create Application:**
   - In Coolify, create a new application and point it to this repository.
   - Select the **Docker Compose** build pack.

2. **Environment Variables:**
   Configure the following variables in the Coolify UI:

   | Variable | Description |
   | :--- | :--- |
   | `COOLIFY_FQDN` | The domain for your Tabby instance (e.g., `tabby.domain.com`). |
   | `GH_TOKEN` | Personal Access Token for GitHub CLI operations. |
   | `CLOUDFLARE_API_TOKEN` | API Token for Wrangler/Cloudflare deployments. |
   | `COOLIFY_API_TOKEN` | Token to manage your Coolify instance via CLI. |
   | `TELEGRAM_TOKEN` | Bot token for Telegram integration. |
   | `GOOGLE_API_KEY` | Required for Gemini CLI AI features. |
   | `SOCIAL_AUTH_GITHUB_KEY` | GitHub OAuth Client ID for Tabby login. |
   | `SOCIAL_AUTH_GITHUB_SECRET` | GitHub OAuth Client Secret for Tabby login. |

3. **Domain Mapping:**
   - Map your primary domain (e.g., `https://tabby.domain.com`) to the `tabby` service on port `80`.

## ⌨️ Usage

Once deployed:
1. Access the web UI at your configured domain.
2. Log in using the GitHub OAuth provider.
3. To access your tools, go to **Settings > Profiles & Connections**.
4. Add a new **Docker** profile and select the `gemini-terminal` container.
5. Launch the profile to start coding with your AI agent.

## 💾 Persistence

The stack uses Docker volumes to ensure your data stays safe across deployments:
- `gemini_workspace`: Your working files and projects.
- `gemini_auth`: Persistence for Gemini CLI and other tool authentications.
- `tabby-db`: Persistent MariaDB storage for Tabby settings.

---
*Created and maintained for cloud-native engineers.*
