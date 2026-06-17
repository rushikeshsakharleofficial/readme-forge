# Pattern: SaaS / Web App

Use for Next.js, SvelteKit, Nuxt, Remix, Astro projects intended as deployable applications.

---

## Section Order

1. Hero (centered, with demo link)
2. Demo screenshot or GIF (high priority — captures attention)
3. Features (3-column table for rich, bullet list for minimal)
4. Tech stack
5. Getting started (env setup → install → dev server)
6. Environment variables
7. Deployment
8. Project structure
9. Contributing
10. License

---

## Template (rich style, startup-landing feel)

```markdown
<div align="center">

# APP-NAME

### One sentence. What it does. Who it's for.

[![Demo](https://img.shields.io/badge/Live_Demo-000000?style=for-the-badge&labelColor=000000&color=22D3EE)](DEMO_URL)
[![License](https://img.shields.io/badge/license-MIT-000000?style=for-the-badge&labelColor=000000&color=A78BFA)](LICENSE)
[![Deploy](https://img.shields.io/badge/Deploy_to_Vercel-000000?style=for-the-badge&logo=vercel&labelColor=000000)](https://vercel.com/new/clone?repository-url=REPO_URL)

</div>

---

![App screenshot](docs/screenshot.png)

## Features

<table>
  <tr>
    <td width="33%" valign="top">
      <b>Feature One</b>
      <p><sub>One to two sentences. What it does and why it matters to the user.</sub></p>
    </td>
    <td width="33%" valign="top">
      <b>Feature Two</b>
      <p><sub>One to two sentences.</sub></p>
    </td>
    <td width="33%" valign="top">
      <b>Feature Three</b>
      <p><sub>One to two sentences.</sub></p>
    </td>
  </tr>
</table>

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 15 / App Router |
| Styling | Tailwind CSS v4 |
| UI Components | shadcn/ui |
| Database | Postgres (via Drizzle ORM) |
| Auth | NextAuth.js |
| Deployment | Vercel |

## Getting Started

**Prerequisites:** Node.js 20+, [package manager]

**1. Clone and install:**
```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
npm install
```

**2. Set up environment variables:**
```bash
cp .env.example .env.local
```

Fill in `.env.local`:
```env
DATABASE_URL=          # Postgres connection string
NEXTAUTH_SECRET=       # Generate with: openssl rand -base64 32
NEXTAUTH_URL=http://localhost:3000
```

**3. Start the dev server:**
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `DATABASE_URL` | ✅ | Postgres connection string |
| `NEXTAUTH_SECRET` | ✅ | Random string for session signing |
| `NEXTAUTH_URL` | ✅ | App base URL |
| `OPTIONAL_VAR` | ❌ | Description of what it controls |

## Deployment

**Vercel (recommended):**

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=REPO_URL)

**Manual:**
```bash
npm run build
npm start
```

**Docker:**
```bash
docker build -t APP-NAME .
docker run -p 3000:3000 --env-file .env APP-NAME
```

## Project Structure

```
src/
├── app/                 ← Next.js App Router pages
│   ├── (auth)/          ← Auth routes
│   ├── (dashboard)/     ← Protected routes
│   └── api/             ← API routes
├── components/          ← Shared UI components
├── lib/                 ← Utilities, db client, auth config
└── styles/              ← Global styles
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Run tests with `npm test`.

## License

[MIT](LICENSE)
```

---

## Key rules for SaaS / web app READMEs

1. **Demo link in the hero** — if the app is deployed, link it immediately. This is the most clicked thing.
2. **Screenshot above the fold** — an actual screenshot of the UI converts more than any feature list.
3. **Environment variables table is mandatory** — every variable, whether required, and what it controls.
4. **Never expose actual values** — only `.env.example` key names, never real secrets.
5. **One-command dev setup** — if setup takes more than 4 steps, developers will not try it.
6. **Deployment instructions for at least one platform** — Vercel deploy button if it's a Next.js app.
7. **Tech stack table** — helps developers know if they can contribute or fork.
