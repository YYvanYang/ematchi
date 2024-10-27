# Workers Getting Started Guide

> This guide is based on the official Cloudflare documentation: [Get Started with Static Assets](https://developers.cloudflare.com/workers/static-assets/get-started/#deploy-a-static-site)

This guide helps you get started with deploying applications on Workers, whether you're building a static site or a full-stack application.

## Table of Contents
- [Framework vs No Framework](#framework-vs-no-framework)
- [Static Site Deployment](#static-site-deployment)
- [Full-Stack Application Deployment](#full-stack-application-deployment)

## Framework vs No Framework

For most front-end applications, using a framework is recommended as they provide:
- Ready-to-use components
- Pre-defined and structured architecture
- Community support

However, building from scratch might be preferred if you:
- Want to learn by implementing core functionalities yourself
- Are working on a simple project
- Need to optimize for performance by minimizing dependencies
- Require complete control over the application
- Want to build your own framework

## Static Site Deployment

### 1. Create Project
Use C3 (create-cloudflare-cli) to set up your project:
```bash
pnpm create cloudflare@latest my-static-site --experimental
```

Select the following options:
- What would you like to start with? → Hello World example
- Which template would you like to use? → Hello World - Assets-only
- Which language do you want to use? → TypeScript
- Do you want to use git for version control? → Yes
- Do you want to deploy your application? → No

Navigate to your project:
```bash
cd my-static-site
```

### 2. Local Development
Start the local development server:
```bash
npx wrangler dev
```

### 3. Deployment
Deploy your project using:
```bash
npx wrangler deploy
```

> **Note**: Review the routing configuration documentation to understand how assets are configured and routing works.

## Full-Stack Application Deployment

### 1. Create Project
Initialize your full-stack project:
```bash
pnpm create cloudflare@latest my-dynamic-site --experimental
```

Select the following options:
- What would you like to start with? → Hello World example
- Which template would you like to use? → Hello World - Worker with Assets
- Which language do you want to use? → TypeScript
- Do you want to use git for version control? → Yes
- Do you want to deploy your application? → No

Navigate to your project:
```bash
cd my-dynamic-site
```

### 2. Local Development
Start the local development server:
```bash
npx wrangler dev
```

### 3. Project Structure & Modifications
Key files to modify:
- `src/index.ts` - Server-side Worker logic
- `public/index.html` - Static assets and content

### 4. Deployment
Deploy your application:
```bash
npx wrangler deploy
```

## Deployment Options
Your projects can be deployed to:
- `*.workers.dev` subdomain
- Custom Domain

Deployment can be done from:
- Local machine
- CI/CD systems
- Cloudflare's CI/CD

> **Note**: When using CI, make sure to update your "deploy command" configuration appropriately.

## References
- [Official Documentation: Get Started with Static Assets](https://developers.cloudflare.com/workers/static-assets/get-started/#deploy-a-static-site)