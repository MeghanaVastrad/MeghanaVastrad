# 🚀 Quick Setup & Configuration Checklist

To activate all dynamic features in your profile repository, follow these quick steps:

1. **Enable GitHub Action Write Permissions**:
   - Go to `Settings` ➔ `Actions` ➔ `General` ➔ `Workflow permissions`.
   - Select **Read and write permissions** and save.

2. **Add GitHub Repository Secrets** (`Settings` ➔ `Secrets and variables` ➔ `Actions`):
   - `GH_PAT` (Personal Access Token with `repo` scope)
   - `WAKATIME_API_KEY` (Your WakaTime API key)
   - `SPOTIFY_CLIENT_ID`, `SPOTIFY_CLIENT_SECRET`, `SPOTIFY_REFRESH_TOKEN` (For live music status)

3. **Run Initial Actions**:
   - Go to the **Actions** tab on GitHub and manually trigger `Generate Snake Animation`, `Latest Blog Posts Workflow`, and `GitHub Metrics Dashboard`.

For full documentation and troubleshooting details, see [assets/docs/SETUP_GUIDE.md](./assets/docs/SETUP_GUIDE.md).
