# JK CAPITAL — Prisma Compute edition

Adaptation of the supplied JK CAPITAL test application for Prisma Compute. It retains the Express/EJS interface and PostgreSQL data model, adding a Prisma Composer service, managed PostgreSQL resource, Bun bundle build, and GitHub Actions deploy workflow.

## Simulation only
This app simulates deposits, withdrawals, balances and administrative actions. It does not receive real funds, execute bank transfers, or promise returns. Do not enter real financial credentials or use it to hold customer funds.

## Upload layout
Upload the CONTENTS of this folder to the root of the connected GitHub repository. `package.json`, `app.js`, `service.ts`, `module.ts`, and `prisma.config.ts` must be at repository root. Keep `.github/workflows/prisma-deploy.yml` at that exact path.

## Before deploy
1. Connect this exact repository in Prisma Console.
2. In Prisma project Environment settings, add `SESSION_SECRET` (random, at least 32 characters), `ADMIN_EMAIL`, and `ADMIN_PASSWORD` (strong, unique, at least 10 characters).
3. The Composer module provisions its own PostgreSQL database.
4. Push the files to `main`.
5. Open GitHub → Actions → `prisma-deploy`. The run report and Prisma Console show the public URL.

The workflow explicitly runs `npm install` and `npm run build`; Bun builds `dist/server.mjs`. Defaults: demo mode OFF, public registration OFF, currency EUR.
