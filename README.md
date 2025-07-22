# php-nvm

🐳 **php-nvm** is a generic, lightweight Docker image for PHP applications that includes [NVM](https://github.com/nvm-sh/nvm), allowing dynamic management of multiple Node.js versions at runtime.

[![Docker Pulls](https://img.shields.io/docker/pulls/ocreaper/php-nvm)](https://hub.docker.com/r/ocreaper/php-nvm/)
![NVM Version](https://img.shields.io/badge/nvm-v0.40.3-blue)

---

## 🚀 Features

- ✅ PHP 8.x support (8.0–8.4)
- ✅ Pre-installed [NVM](https://github.com/nvm-sh/nvm) for managing multiple Node.js versions
- ✅ Ideal for modern full-stack PHP projects that require Node.js tooling (e.g. Webpack, Vite, etc.)
- ✅ CI-friendly: small, clean, and consistently versioned
- ✅ Useful system tools: `git`, `rsync`, `openssh-client`, `make`, `curl`, etc.
- ✅ All images share the same consistent build logic

---

## 📦 Available Tags

| Tag  | PHP Version | Included Tools                         |
|------|-------------|----------------------------------------|
| 8.0  | 8.0         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.1  | 8.1         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.2  | 8.2         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.3  | 8.3         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.4  | 8.4         | ✅ PHP, Composer, NVM, Node.js via NVM |

> ℹ️ The exact Node.js version is not preinstalled — use `nvm install` as needed in your Dockerfile or entrypoint script.

---

## 🧪 Usage

### 🐋 Example Dockerfile

```Dockerfile
FROM ocreaper/php-nvm:8.3

# Install Node.js 18 using NVM
RUN source ~/.nvm/nvm.sh && \
    nvm install 18 && \
    nvm use 18 && \
    node -v && npm -v

# Set up your app
COPY . /app
WORKDIR /app
RUN composer install
```

### 💻 Run it interactively

```sh
docker run -it --rm ocreaper/php-nvm:8.3 bash
```

## 🤝 Contributing

Any contributions are welcomed!

Use Conventional Commits with a required scope:

- ✅ feat(8.4): add PHP 8.4 support
- ✅ fix(8.3): correct NVM installation path

GitHub Actions will:

- ✅ Enforce PR title formatting
- ✅ Ensure the Docker image builds successfully

See [CONTRIBUTING.md](CONTRIBUTING.md) for full contribution guidelines.
