# EscrowX 🔒 — AI-Powered Web3 Escrow Platform

> A mini-project built as part of our B.Tech coursework, exploring how AI + Web3 concepts can be combined to solve a real-world freelancing problem: **trust between clients and freelancers.**

---

## 📌 About the Project

Freelancing online has one big trust issue — clients are scared to pay upfront, and freelancers are scared to deliver work without a payment guarantee. **EscrowX** is our attempt at solving this using an escrow-style payment flow, combined with AI to help review work and settle disagreements.

In simple words:
- The client deposits (simulated) funds into an escrow before work starts.
- The freelancer completes the project in milestones instead of all at once.
- Every milestone submission is checked by AI before the client makes the final call.
- Money is only released when the client approves a milestone.
- If both sides disagree, an AI dispute assistant looks at both arguments and gives a fair, non-binding recommendation.

This is a **frontend prototype / demo** — there is no real blockchain or real money involved anywhere. All wallet addresses, transaction hashes, and "confirmations" are simulated so we could focus on the product idea and UI/UX instead of setting up actual smart contracts.

---

## ✨ Features

- **Dual dashboards** — switch between Client view and Freelancer view to see both sides of the same project.
- **Milestone-based payments** — projects are broken into milestones, each with its own amount, deadline, and status (Pending → In Progress → Submitted → AI Review → Client Review → Approved → Paid).
- **AI deliverable review** — when a freelancer submits work, an AI checks it against the agreed requirements before the client reviews it.
- **AI dispute assistant** — if a milestone is rejected, either side can raise a dispute; the AI reads both statements and suggests a resolution (client still has the final say).
- **Explainable risk assessment** — a scoring system that looks at things like milestone structure, account reputation, and dispute history, and shows *why* it gave that score instead of a random number.
- **In-app AI chat assistant** — ask questions about your project (payments, deadlines, status) and get answers based only on that project's data.
- **Simulated blockchain layer** — fake wallet addresses, transaction hashes, and an activity/transaction history log, to mimic how an on-chain escrow would look and feel.
- **Smart agreement generator** — auto-generates a plain-text agreement summarizing scope, milestones, deadlines, and refund rules.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| UI Library | React 18 (via CDN, no build step) |
| JSX Compilation | Babel Standalone (in-browser) |
| Styling | Inline CSS-in-JS (custom design tokens) |
| Icons | Custom inline SVGs (Lucide icon set, self-hosted so no npm install needed) |
| Fonts | Google Fonts — Fraunces, Inter, IBM Plex Mono |
| AI | Anthropic Claude API (`claude-sonnet-4-6`) for reviews, disputes, and chat |
| Blockchain | Simulated only — no real Web3 library or wallet connection used |

We intentionally kept this as a **single HTML file** with everything (React, styles, and app logic) inside it. No `npm install`, no bundler, no build step — just open the file in a browser. This made it much easier for us to share, run, and demo without dealing with dependency/environment issues before our evaluation.

---

## 🚀 How to Run

Since this is a single self-contained HTML file, there's nothing to install.

1. Download / clone this repository.
2. Open `index.html` directly in any modern browser (Chrome/Edge recommended).
3. Click **"Explore Demo"** on the landing page.
4. Use the role switch (Client / Freelancer) at the top to see both perspectives of the same demo project.

That's it — no server, no `.env` file needed for the demo project itself, since it comes pre-seeded with sample data.

> ⚠️ Note: The AI features (milestone review, dispute assistant, chat) call the Anthropic API. If the request fails (e.g., no internet or API access in your environment), the app falls back to a safe default message/response instead of crashing.

---

## 👥 User Roles

- **Client** — creates projects, funds escrow, reviews submitted milestones, approves/releases payments, and can raise disputes.
- **Freelancer** — accepts/declines project assignments, submits deliverables per milestone, and can raise disputes.

The same demo project can be viewed from either role using the toggle in the navbar, so you don't need two separate logins to test the flow.

---

## 🤖 About the AI Parts (Important!)

We want to be transparent about what the "AI" actually does here, since it's a core part of the project:

- The AI **never directly moves money or makes a final decision** — it only reviews and *suggests*. The client (or mutual agreement) always makes the final call on approvals, releases, and refunds.
- The risk score is **explainable** — it's built from clear rule-based signals (like milestone size, account history, on-time delivery) and only *then* uses AI to phrase a short recommendation on top of it. It's not a black box.
- If the AI call fails for any reason, the app has fallback logic so the core escrow flow still works.

---

## 📂 Project Structure

Since everything lives in one file, here's roughly how `EscrowX.html` is organized internally:

1. Icon library (inline SVGs)
2. Design tokens (colors, fonts)
3. Helper functions (formatting money, dates, fake wallet addresses, etc.)
4. Risk detection engine
5. Claude API integration
6. Demo data (seed project)
7. Reusable UI components (buttons, cards, chips, modals, etc.)
8. Landing page
9. Client & Freelancer dashboards
10. Project detail view (milestones, disputes, transactions)
11. AI chat assistant panel
12. App mount / root render

---

## 🔮 Future Scope

Since this was built as a learning project, there's a lot we'd like to add if we continue working on it:

- Actual wallet connection (MetaMask) and a real testnet smart contract instead of simulated transactions.
- User authentication instead of a role toggle.
- Backend + database so projects persist beyond a browser refresh.
- File upload support for real deliverables instead of text/link descriptions.
- Multi-currency / multi-chain support.

---

## 🎓 Disclaimer

This project was built for **academic/learning purposes** as part of our B.Tech coursework. It is a UI/UX + AI-integration prototype and:
- Does **not** use real cryptocurrency or move real money.
- Does **not** connect to any real blockchain network.
- Should **not** be used for actual freelance payments or escrow in its current form.

---

## 🙌 Team

Built by a team of 2nd Year B.Tech students as a mini-project — feedback and suggestions are always welcome!
