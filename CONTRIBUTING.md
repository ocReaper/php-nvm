# Contributing Guide

Thank you for your interest in contributing! This repository hosts versioned PHP Docker images with optional NVM and Node.js support.

## 📋 Contribution Checklist

Before opening a Pull Request, please make sure that:

- You are modifying or adding files in the correct version folder (e.g. `8.3/Dockerfile`)
- Your PR **title follows the [Conventional Commits](https://www.conventionalcommits.org/) format** and includes a valid **scope**
    - ✅ Correct examples:
        - `feat(8.4): add support for PHP 8.4`
        - `fix(8.3): correct NVM install path`
        - `chore(8.3): update nvm version`
    - ❌ Invalid examples (missing scope or wrong format):
        - `feat: add PHP 8.4` ← missing scope
        - `fix php 8.3 image` ← not a conventional commit format

> The `scope` must describe the context of the change, such as the PHP version (`8.0`, `8.3`, etc.) or a general target like `docker` or `ci`.

- Your Dockerfile change builds successfully
    - The GitHub workflow will attempt to build the image automatically
    - You can also test locally with:
      ```sh
      docker build -t php-custom:8.3 ./8.3
      ```

## ✅ Best Practices

- **Avoid modifying multiple PHP versions in a single PR** unless necessary
- Keep version-specific differences minimal and well-documented in `README.md` if needed
- If adding a new PHP version (e.g. `8.4`), use the closest previous version (e.g. `8.3`) as a starting point

## 🧪 CI Workflow

All PRs trigger a GitHub Actions workflow which will:

- Validate the PR title against Conventional Commits with required scope
- Build the updated Docker image to ensure it compiles successfully

After a successful squash merge a GitHub Actions workflow will publish the new versions to Docker Hub.

You can find the workflow definitions at [.github/workflows](.github/workflows).

## 🛡️ Security

If you're introducing or updating external binaries (e.g. Node.js, NVM), use official sources and verify integrity (e.g. via checksum or GPG).

If you're unsure about anything, feel free to open a draft PR or discussion.
