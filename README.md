# concord-builds

Automated Linux `amd64` (GLIBC 2.35+, compatible with Debian 13) builds of [Vialibrex/concord](https://github.com/Vialibrex/concord) `main` branch.

## First-Time Setup on GitHub

1. Create a **Public** repository named `wuiiled/concord-builds` on GitHub (public repos get unlimited free GitHub Actions minutes and require no token to download Releases).
2. Push this folder to `main`:
   ```bash
   cd concord-builds
   git init -b main
   git add .
   git commit -m "init: automated concord build workflow"
   git remote add origin https://github.com/wuiiled/concord-builds.git
   git push -u origin main
   ```
3. In GitHub repo **Settings → Actions → General → Workflow permissions**, ensure **Read and write permissions** is selected (already declared in `permissions: contents: write`, enabling repo default ensures `git push` and Release creation always succeed).
4. Open the **Actions** tab → **Build Concord (Linux amd64)** → click **Run workflow** once to trigger the first build.

## Router Usage (`10.0.254.1`)

- Check for updates (read-only): `update-concord --check`
- Update immediately: `sudo update-concord`
- Force reinstall latest build: `sudo update-concord --force`
- Roll back to previous binary: `sudo update-concord --rollback`
- Automatic daily update: `concord-update.timer` runs at `04:30` local time.
