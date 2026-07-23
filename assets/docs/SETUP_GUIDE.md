# 🛠️ GitHub Profile Setup & Customization Guide

Welcome to the setup guide for **MeghanaVastrad**'s GitHub Profile Repository! This document walks through configuring all dynamic components, setting up GitHub Secrets, setting up GitHub Actions workflows, and resolving common errors.

---

## 📋 Required GitHub Secrets

To unlock full dynamic functionality (Snake animation, WakaTime coding stats, Spotify widget, Blog post automation, and Metrics dashboard), configure the following repository secrets under **Settings ➔ Secrets and variables ➔ Actions**:

| Secret Name | Purpose / Widget | How to Get / Instructions |
| :--- | :--- | :--- |
| `GH_PAT` / `METRICS_TOKEN` | GitHub Metrics & Snake Action | Generate a **Personal Access Token (Classic)** with `repo`, `read:user`, `user:email` scopes at [github.com/settings/tokens](https://github.com/settings/tokens). |
| `WAKATIME_API_KEY` | WakaTime Weekly Coding Stats | Get your API key from [WakaTime Account Settings](https://wakatime.com/settings/account). |
| `SPOTIFY_CLIENT_ID` | Live Spotify Player Card | Obtain from [Spotify Developer Dashboard](https://developer.spotify.com/dashboard). |
| `SPOTIFY_CLIENT_SECRET` | Live Spotify Player Card | Obtain from [Spotify Developer Dashboard](https://developer.spotify.com/dashboard). |
| `SPOTIFY_REFRESH_TOKEN` | Live Spotify Player Card | Follow `novathesheep/spotify-github-readme` auth workflow to generate a refresh token. |

---

## ⚙️ Enabling GitHub Actions Permissions

1. Go to your repository **Settings**.
2. Under **Actions**, click **General**.
3. Scroll to **Workflow permissions**.
4. Select **Read and write permissions**.
5. Check **Allow GitHub Actions to create and approve pull requests**.
6. Click **Save**.

---

## 🚀 Workflows Overview

### 1. Snake Contribution Grid (`.github/workflows/snake.yml`)
- Runs automatically on a daily cron schedule (`0 0 * * *`) and on push.
- Generates `github-contribution-grid-snake.svg` and `github-contribution-grid-snake-dark.svg` into an `output` branch.

### 2. RSS Blog Posts (`.github/workflows/blog-post-workflow.yml`)
- Runs every 6 hours (`0 */6 * * *`).
- Automatically replaces text between `<!-- BLOG-POST-LIST:START -->` and `<!-- BLOG-POST-LIST:END -->` in `README.md`.

### 3. Account Metrics (`.github/workflows/metrics.yml`)
- Runs every midnight (`0 0 * * *`).
- Uses `lowlighter/metrics` to build isometric contribution charts and language breakdowns.

---

## ⚠️ Common Mistakes & Troubleshooting

1. **Snake Action Fails with 403 Forbidden / Permission Error**:
   - **Fix**: Ensure Workflow permissions are set to *Read and write permissions* in Repository Settings -> Actions -> General.

2. **Blog Posts Not Updating**:
   - **Fix**: Verify your RSS/Atom feed URL in `.github/workflows/blog-post-workflow.yml` (e.g. Dev.to or Medium feed).

3. **Spotify / WakaTime Cards Showing Error / Blank**:
   - **Fix**: Verify that secrets (`WAKATIME_API_KEY`, `SPOTIFY_REFRESH_TOKEN`) are properly added in GitHub Secrets without leading/trailing spaces.

4. **Stats Card Rate Limit Exceeded**:
   - **Fix**: Provide a GitHub Personal Access Token to stats widgets or host your own Vercel instance of `github-readme-stats`.

---

## 🎨 Customizing Links & Usernames

Simply update the placeholders in `README.md`:
- Replace `meghanavastrad` with your specific social media handles (LinkedIn, X/Twitter, Instagram, Portfolio URL).
- Update your Discord ID for Lanyard status widgets: `https://lanyard.cnrad.dev/api/raw?id=YOUR_DISCORD_ID`.
- Update your WakaTime username: `https://github-readme-wakatime.vercel.app/api?username=YOUR_USER`.
