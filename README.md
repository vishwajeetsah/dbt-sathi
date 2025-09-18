```markdown
# DBT-Sathi — DBT Bank Seeding Verification (Prototype)

**Team:** Saksham  
**Hackathon:** Smart India Hackathon / University Ideathon (Reference: Problem Statement ID25059)  
**Project:** DBT-Sathi — Student awareness & verification platform for Aadhaar → DBT seeding

---

## 🚀 Project Summary

**DBT-Sathi** is a student-focused prototype web app that helps users verify whether their Aadhaar is seeded with a bank account for Direct Benefit Transfer (DBT). The prototype demonstrates the full user journey:

- Awareness (video + guide)
- DBT verification (Aadhaar → Captcha → OTP flow — **simulated** in prototype)
- Support (chatbot mock + call center info)
- Result screen (DBT Enabled / Not Enabled)
- Recent check history (local)

> ⚠️ **Important:** This prototype is a **demo** and does NOT call UIDAI or NPCI production APIs. It uses **mocked results** for demonstration. Real integration requires official approvals and secure server-side integration.

---

## 🎯 Problem Statement (aligned to SIH ID25059)

Many students do not understand the difference between **Aadhaar-linked** and **DBT-enabled Aadhaar-seeded bank accounts**, causing scholarship payment failures and delays. DBT-Sathi addresses this shortfall by combining awareness campaigns and a verification/support tool (App/Web/WhatsApp/SMS).

---

## ✨ Features (Prototype)

- Clean 3-step verification UI (Aadhaar → Captcha → OTP)
- Demo toggle behavior: verification alternates between **Enabled** and **Not Enabled** to show both flows
- Mock DBT success screen with randomized bank details
- Not-enabled flow with step-by-step guide and awareness video placeholder
- Chatbot (mock, scripted responses)
- Call center card with availability (May–June demonstration scheduling)
- Recent checks saved locally (masked Aadhaar)
- Responsive layout using Tailwind CSS

---

## 🧩 Tech Stack (Prototype)

- Frontend: Plain HTML / CSS (Tailwind) / JavaScript
- No backend required for prototype (static site)
- Storage: `localStorage` (for demo check history)
- Deployment: GitHub Pages (static hosting)

---

## 📁 Repository Structure (example)

```

dbt-sathi/
├─ index.html
├─ saksham-logo.png
├─ README.md
└─ (optional) assets/
├─ style.css
└─ video-placeholder.mp4

````

---

## 🛠️ How to Run Locally (quick)

### Option A — Quick (no installs)
1. Open `index.html` directly in your browser (double click file).  
   - Note: Some browsers restrict `localStorage`/video playback for `file://` — for best results use a local server.

### Option B — Using Python (recommended)
```bash
# inside repo folder
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
````

### Option C — Using VS Code Live Server

* Install Live Server extension → Right-click `index.html` → `Open with Live Server`

---

## 📦 Deploy to GitHub Pages (step-by-step)

1. Create repo on GitHub (e.g. `dbt-sathi`) and push code.
2. In repo → **Settings** → **Pages** → Source: `main (root)` → Save.
3. Wait 1–2 minutes; published site will be:

```
https://<your-github-username>.github.io/dbt-sathi/
```

4. Add the live link to your hackathon submission.

---

## 📋 How the Prototype Mocking Works (explainable for reviewers)

* **Mock toggle**: Prototype uses a boolean `toggleResult` to switch between success/failure each verification attempt. This allows the demo to show both the DBT-enabled path and the Not-enabled path.
* **Mock OTP**: OTP UI is simulated — the prototype does not send SMS. Any 6-digit OTP is accepted for demo.
* **Sample data**: When showing `DBT Enabled`, sample bank name / branch / seeding date are chosen randomly from arrays to demonstrate variability.
* **History**: The site masks Aadhaar (e.g., `XXXX-XXXX-1234`) and stores last 5 checks in `localStorage` for demo convenience.

**Why mock?**
Real UIDAI/NPCI APIs are secured (CAPTCHA+OTP + legal access). For the hackathon, this simulation demonstrates UX, flow and design clearly, without touching sensitive systems.

---

## 🔁 How to Switch from Mock to Real (future plan)

> Only implement real calls after official approvals and compliance checks.

1. **Backend server** (Node/Express or Python Flask) — required for secure server-to-server calls and to store credentials safely.
2. **Obtain APIs & Credentials**:

   * Seek official access to NPCI DBT mapper / UIDAI authentication via ministry channels.
3. **Server-side flow**:

   * Frontend sends masked Aadhaar (or request token) to your backend.
   * Backend performs authenticated call to UIDAI/NPCI auth endpoints.
   * Backend returns DBT status to frontend (never expose raw Aadhaar to client).
4. **Security**:

   * Use HTTPS, store secrets in environment variables.
   * Adhere to UIDAI Aadhaar data masking & retention policies.
   * Maintain audit logs; do not persist full Aadhaar numbers.

---

## 🔐 Privacy & Security Notes (must-have in public repo)

* **This repo is a prototype and does not process real Aadhaar data.**
* For production: NEVER store full Aadhaar numbers in logs or DB; store only masked or hashed identifiers per UIDAI rules.
* Use strong encryption and follow government security guidelines before integrating with real systems.

---

## 🧪 Demo Use Cases for Judges

* Use Aadhaar `123456789012` (demo) → shows **DBT Enabled** (first run)
* Re-check same or another Aadhaar → shows **Not Enabled** (toggle)
* Use video modal and chatbot to show awareness & support flows
* Show call center card and explain seasonal intern-supported helpline (May–June)

---

## 📄 README / Documentation (what to include in your repo)

* This `README.md` with setup + run instructions
* `index.html` (main prototype)
* `saksham-logo.png` (team logo)
* `LICENSE` (suggest MIT)
* `CHANGELOG.md` (optional — track progress)
* `DEMO.md` (optional — screenshots + video link)

---

## 👥 Team

* Vishwajeet Sah — Developer & Legal (B.A. LL.B, 3rd Year)
* Rohan Kumar — Backend Developer (B.A. LL.B, 3rd Year)
* Heem Singh — UI/UX Designer (B.A. LL.B, 3rd Year)
* Hariom Kurmi — Frontend Developer (B.A. LL.B, 3rd Year)
* Seema — Content & Awareness Strategist (B.A. LL.B, 3rd Year)
* Lakhichand Chauhan — Data Analyst / Research (BSc, 2nd Year)

---

## 🧾 Acknowledgements & References

* Problem Statement ID25059 — MoSJE / DoSJE (DBT-Aadhaar awareness)
* UIDAI documentation (public site) — for understanding seeding concepts
* NPCI docs (for future DBT mapper integration)

---

## 📝 Example `README.md` snippet to add to your repo (copy/paste)

> Use the content of this README as your `README.md` file.

---

## 🧰 Useful Commands (Git quick reference)

```bash
# Initialize repo locally
git init
git add .
git commit -m "Initial commit: DBT-Sathi prototype"

# Add remote and push
git remote add origin https://github.com/<your-username>/dbt-sathi.git
git branch -M main
git push -u origin main
```

---

## ⚖️ License

We recommend **MIT License** for the prototype.

```text
MIT License
Copyright (c) <year> Team Saksham
...
```

---

## ❓ Frequently Asked (Hackathon-specific)

**Q: Does the demo use real Aadhaar data?**
A: No. Demo uses mock toggled results and does not call UIDAI.

**Q: Can this be production-ready?**
A: Yes — after official API access, backend integration, and compliance checks (UIDAI/NPCI).

**Q: How do you plan to scale this?**
A: Cloud-hosted backend, caching, seasonal call-centre scaling, and roll-out with government partnerships.

---

## 📞 Contact

For collaboration or questions, contact:
**Team Saksham** — \[[email@example.com](mailto:email@example.com)] *(replace with actual email)*

---

**Thank you — DBT-Sathi (Team Saksham)**

```

---

If you want, I can now:

- ✅ Customize the README with your exact GitHub username and live URL (if you already deployed), or
- ✅ Generate the `LICENSE` file content (MIT) and `CHANGELOG.md` template, or
- ✅ Create a short `DEMO.md` that lists the exact Aadhaar sample values and step-by-step actions the judge should click during demo.

Now — you said *“before that i have a questions”*. Go ahead and ask your questions — I’m ready to answer them. If you prefer, I can also immediately tailor the README to include your exact GitHub username and the live URL after you push. Which do you want first?
::contentReference[oaicite:0]{index=0}
```
