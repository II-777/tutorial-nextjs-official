---
title: README
date: 2024-09-28 22:12
author: II-777
gitea: none
include_toc: true
tags: typescript react nextjs tutorial
---

# 🕮 NEXT.JS CONSPECTUS

This is a repository for documenting my journey of learning Next.js

## Next.js Official Tutorial:
- [Nextjs: Official Tutorial](https://nextjs.org/learn/dashboard-app) 
- [Git: starter example repo](https://github.com/vercel/next-learn/tree/main/dashboard/starter-example)

```bash
# install package manager
npm install -g pnpm
# start nextjs project 
npx create-next-app@latest nextjs-dashboard --example "https://github.com/vercel/next-learn/tree/main/dashboard/starter-example" --use-pnpm
```
### Project Dir Structure
```plaintext
user1@ii777:~/Desktop/tutorial-nextjs-official$ tree -L 2 -I node_modules/
.
├── app
│   ├── layout.tsx
│   ├── lib
│   ├── page.tsx
│   ├── seed
│   └── ui
├── next.config.mjs
├── next-env.d.ts
├── package.json
├── pnpm-lock.yaml
├── postcss.config.js
├── public
│   ├── customers
│   ├── favicon.ico
│   ├── hero-desktop.png
│   ├── hero-mobile.png
│   └── opengraph-image.png
├── README.md
├── tailwind.config.ts
└── tsconfig.json

6 directories, 14 files
```
### Dir Structure Notes
> - /app: Contains all the routes, components, and logic for your application, this is where you'll be mostly working from.
> - /app/lib: Contains functions used in your application, such as reusable utility functions and data fetching functions.
> - /app/ui: Contains all the UI components for your application, such as cards, tables, and forms. To save time, we've pre-styled these components for you.
> - /public: Contains all the static assets for your application, such as images.
> - Config Files: You'll also notice config files such as next.config.js at the root of your application. Most of these files are created and pre-configured when you start a new project using create-next-app. You will not need to modify them in this course.
