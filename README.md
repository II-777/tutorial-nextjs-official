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
## Libraries:
- [zod input validation](https://zod.dev/?id=ip-addresses)

## Chapter 1
```bash
# install package manager
npm install -g pnpm
# start nextjs project 
npx create-next-app@latest nextjs-dashboard --example "https://github.com/vercel/next-learn/tree/main/dashboard/starter-example" --use-pnpm
```
#### Project Dir Structure
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
#### Dir Structure Notes
> - /app: Contains all the routes, components, and logic for your application, this is where you'll be mostly working from.
> - /app/lib: Contains functions used in your application, such as reusable utility functions and data fetching functions.
> - /app/ui: Contains all the UI components for your application, such as cards, tables, and forms. To save time, we've pre-styled these components for you.
> - /public: Contains all the static assets for your application, such as images.
> - Config Files: You'll also notice config files such as next.config.js at the root of your application. Most of these files are created and pre-configured when you start a new project using create-next-app. You will not need to modify them in this course.


## Chapter 2
### Use Tailwind and CSS modules together for styling
```js
<div className={`${styles.customStyle} bg-blue-500 text-white p-4 rounded`} />
```

### Conditional styling
```js
import clsx from 'clsx';
 
export default function InvoiceStatus({ status }: { status: string }) {
  return (
    <span
      className={clsx(
        'inline-flex items-center rounded-full px-2 py-1 text-sm',
        {
          'bg-gray-100 text-gray-500': status === 'pending',
          'bg-green-500 text-white': status === 'paid',
        },
      )}
    >
    // ...
)}
```

## Chapter 3
- [Google Fonts: Lusitana](https://fonts.google.com/specimen/Lusitana?query=Lusitana)
```ts

// @/app/ui/fonts.ts
import { Inter } from 'next/font/google';
import { Lusitana } from 'next/font/google';
 
export const inter = Inter({ subsets: ['latin'] });
export const lusitana = Lusitana({
  subsets: ['latin'],
  weights: ['400', '700'],
});
```

```ts
// @/app/page.tsx
...
import { lusitana } from '@/app/ui/fonts';

...
<p
      className={`${lusitana.className} text-xl text-gray-800 md:text-3xl md:leading-normal`}
    >
```

## Chapter 4
## Chapter 5
## Chapter 6: Setting Up Your Database
## Steps to Set Up PostgreSQL Database with Vercel

1. **Push Project to GitHub**
2. **Deploy Vercel Project**
3. **Create a Postgres Database**
   - Go to Dashboard > Storage tab.
   - Select **Connect Store** → **Create New** → **Postgres** → **Continue**.
   - Accept terms, name your database, and set region to Washington D.C (iad1).
   - Copy database secrets from the `.env.local` tab.
   - Rename `.env.example` to `.env` in your code editor and paste secrets.
   - Ensure `.env` is in your `.gitignore`.
   - Run `pnpm i @vercel/postgres` in your terminal.

5. **Seed Your Database**
   - In `/app/seed`, uncomment `route.ts`.
   - Run local server: `pnpm run dev`.
   - Navigate to `localhost:3000/seed` in your browser.
   - Confirm message "Database seeded successfully" appears.

6. **Explore Your Database**
   - Go to Vercel and click on **Data**.
   - Check tables: users, customers, invoices, revenue.

7. **Execute Queries**
   - Switch to "query" tab in Vercel.
   - Run the following SQL:
     ```sql
     SELECT invoices.amount, customers.name
     FROM invoices
     JOIN customers ON invoices.customer_id = customers.id
     WHERE invoices.amount = 666;
     ```

## Troubleshooting
- Ensure database secrets are copied correctly.
- If seeding fails, consider using `bcryptjs` instead of `bcrypt`.
- To rerun seed script, use `DROP TABLE tablename` carefully.
- Open a discussion on GitHub for persistent issues.

## Chapter 7
## Chapter 8
## Chapter 9
## Chapter 10
## Chapter 11
```bash
pnpm i use-debounce
```
## Chapter 14
```bash
pnpm lint
```
## Chapter 15 Authentication and Authorization
- [NexAuth Docs](https://authjs.dev/reference/nextjs)

```bash
pnpm i next-auth@beta
openssl rand -base64 32
```
## Chapter 16 Metadata
```bash
https://nextjs.org/docs/app/api-reference/functions/generate-metadata
```
```

