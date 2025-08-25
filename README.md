# React + Vite Project

A modern React application built with Vite, featuring comprehensive CI/CD workflows.

## 🚀 Features

- **React 18** with modern hooks and features
- **Vite** for fast development and building
- **ESLint** for code quality and consistency
- **Vitest** for unit testing
- **GitHub Actions** for automated CI/CD
- **Multiple deployment options** (GitHub Pages, Vercel)

## 📋 Prerequisites

- Node.js 18 or higher
- npm or yarn package manager

## 🛠️ Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd <your-repo-name>
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

## 📜 Available Scripts

### Development
- `npm run dev` - Start development server
- `npm run preview` - Preview production build locally

### Code Quality
- `npm run lint` - Run ESLint with auto-fix
- `npm run lint:check` - Run ESLint without auto-fix (for CI)
- `npm run type-check` - Run TypeScript type checking

### Testing
- `npm run test` - Run tests once
- `npm run test:watch` - Run tests in watch mode
- `npm run test:coverage` - Run tests with coverage report

### Building
- `npm run build` - Build for production
- `npm run ci` - Run full CI pipeline locally (lint + test + build)

## 🔄 CI/CD Workflows

This project includes two GitHub Actions workflows:

### 1. GitHub Pages Deployment (`ci-cd.yml`)

**Triggers:**
- Push to `main` or `develop` branches
- Pull requests to `main` or `develop` branches

**What it does:**
1. **Lint & Test Job:**
   - Checks out code
   - Sets up Node.js 18
   - Installs dependencies
   - Runs ESLint
   - Runs tests
   - Builds the project
   - Uploads build artifacts

2. **Deploy Job** (only on main branch):
   - Deploys to GitHub Pages
   - Uses the `dist/` folder as the source

**Setup:**
1. Go to your repository Settings → Pages
2. Set source to "GitHub Actions"
3. The workflow will automatically deploy on pushes to main

### 2. Vercel Deployment (`vercel-deploy.yml`)

**Triggers:**
- Push to `main` branch
- Pull requests to `main` branch

**What it does:**
1. **Lint & Test Job:** Same as above
2. **Deploy Job:** Deploys to Vercel

**Setup:**
1. Create a Vercel account and project
2. Add these secrets to your GitHub repository:
   - `VERCEL_TOKEN` - Your Vercel API token
   - `ORG_ID` - Your Vercel organization ID
   - `PROJECT_ID` - Your Vercel project ID

## 🔧 Configuration

### ESLint Configuration
The project uses ESLint with React-specific rules. Configuration is in `.eslintrc.json`.

### Vite Configuration
Vite is configured in `vite.config.js` with:
- React plugin
- ESLint plugin
- Test configuration for Vitest

### Test Configuration
Tests are configured to run in a jsdom environment with setup files in `src/test/setup.js`.

## 📁 Project Structure

```
├── .github/
│   └── workflows/
│       ├── ci-cd.yml          # GitHub Pages deployment
│       └── vercel-deploy.yml  # Vercel deployment
├── public/
├── src/
│   ├── components/
│   ├── assets/
│   ├── test/
│   └── ...
├── .eslintrc.json
├── vite.config.js
└── package.json
```

## 🚀 Deployment

### GitHub Pages
The workflow automatically deploys to GitHub Pages when you push to the `main` branch. Your site will be available at:
`https://<username>.github.io/<repository-name>/`

### Vercel
The workflow automatically deploys to Vercel when you push to the `main` branch. You'll get a unique URL for each deployment.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run the CI pipeline locally: `npm run ci`
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.
