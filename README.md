# Bizconnect – Starter (Deutschland, Privacy‑First)

Dieses Projekt ist ein **fertig verdrahtetes** Grundgerüst für Bizconnect:

- **Öffentlich sichtbar ohne Login**
- **Firmen-Login nur per E‑Mail + Passwort**
- **Öffentlich KEINE Standort-/Kontaktdaten**
- **Anfragen per Formular** → landen im Firmen-Dashboard
- Kleine „Spielerei“: **Konfetti** beim Veröffentlichen 🎉
- Modernes UI: Tailwind + Dark Mode

---

## 1) Voraussetzungen (einmalig)

1. Installiere **Node.js (LTS)**.
2. Installiere **Git** (optional, aber empfohlen).
3. Lege eine **PostgreSQL Datenbank** an (am einfachsten: Supabase).

---

## 2) Projekt starten (lokal)

1. Entpacke den Ordner.
2. Öffne den Ordner in VS Code.
3. Kopiere `.env.example` zu `.env` und trage deine Werte ein:

```
DATABASE_URL=...
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=... (irgendein sehr langes Random)
```

4. Terminal im Projekt öffnen und ausführen:

```
npm install
npx prisma migrate dev --name init
npm run dev
```

5. Öffne im Browser:
- Start: http://localhost:3000
- Register: http://localhost:3000/register
- Firmenliste: http://localhost:3000/companies
- Dashboard: http://localhost:3000/dashboard

---

## 3) Deployment (Live stellen)

Empfehlung: **Vercel**.

- Repo auf GitHub pushen
- Vercel → „New Project“ → Repo auswählen
- ENV Variablen in Vercel setzen (DATABASE_URL, NEXTAUTH_URL, NEXTAUTH_SECRET)
- Deploy

---

## 4) Wichtige Logik

Öffentlich werden NUR diese Felder angezeigt:
- name, headline, description, industry, services, tags

Private Felder (contactEmail, phone, street, zip, city, …) werden **nirgends öffentlich** selektiert oder gerendert.

---

## 5) Nächste sinnvolle Erweiterungen

- Verifizierung/Badges (z.B. „geprüft“)
- Admin‑Bereich
- Kategorien/Branchen als feste Liste
- Rate‑Limiting / Captcha fürs Anfrageformular
