# RUZIVO :- DEI Knowledge Challenge

**Peace, Gender and Climate Network (PGCN)**
Create | Initiate | Innovate | Leaving No One Behind

RUZIVO is a standalone, multi-zone DEI knowledge and reflection game built for PGCN and its affiliated networks (TFA, TFZ, AIIDEV Africa, UNDP, ZOU, MBIMB, IEP). It combines timed knowledge challenges, self-assessment toolkits and a psychometric DEI profile into a single deployable HTML file, closing with an EGSI-certified PGCN certificate.

---

## 1. What Is Included

| File | Purpose |
|---|---|
| `RUZIVO.html` | The complete game. No build step, no dependencies. Deploy as-is. |
| `apps-script-backend.gs` | Optional Google Apps Script backend that turns a Google Sheet into a real, live M&E database. |

---

## 2. Deploying the Game

RUZIVO.html is fully self-contained and requires no build process:-

1. Upload `RUZIVO.html` to any static host (GitHub Pages, Netlify, or a PGCN-owned domain).
2. Rename it `index.html` if it is the landing page for that host.
3. No further configuration is required for the game itself to run.

---

## 3. Enabling Real Cross-Country M&E Data

By default, the M&E dashboard and leaderboard only reflect data stored on the current device (`localStorage`). To collect real player data from across countries and organisations, connect the included Google Apps Script backend:-

1. Create a new Google Sheet named "RUZIVO M&E Data."
2. Open Extensions → Apps Script.
3. Delete the starter code and paste in the full contents of `apps-script-backend.gs`.
4. Click Deploy → New deployment → Web app.
   - Execute as :- Me
   - Who has access :- Anyone
5. Copy the resulting Web App URL (ending in `/exec`).
6. Open `RUZIVO.html`, locate the `CONFIG` object near the top of the `<script>` section, and paste the URL into `API_URL`.
7. Redeploy the updated HTML file.

Once connected, every completed profile is written as a row to the Google Sheet, and the M&E dashboard within RUZIVO pulls that data live. The Sheet itself remains fully readable and exportable at any time for institutional reporting.

---

## 4. Certificate and Branding

The final report screen generates a downloadable PGCN certificate rendered in the Network's stronghold colours :- blue, green and white, with the EGSI 2026 certification mark. No external image assets are required; the certificate is generated entirely client-side via HTML canvas.

---

## 5. Known Limitations

- Live AI translation of quiz content (via the Anthropic API) is only available inside the Claude.ai artifact preview environment and does not function once the file is deployed independently. The deployed build ships with English question text; additional languages must be pre-translated and embedded directly into the file rather than fetched at runtime.
- Without the Apps Script backend connected, M&E and leaderboard data remain local to each device and will not reflect other players.

---

## 6. Support

Peace, Gender and Climate Network
pgcnglobal@gmail.com
www.peacegenderandclimatenetwork.com
