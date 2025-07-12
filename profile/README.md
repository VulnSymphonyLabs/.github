# Vuln Symphony Labs

*A private catalogue of synthetic software systems deliberately seeded with ****known, exploitable vulnerabilities**** for benchmarking automated—primarily ****AI‑driven****—security‑analysis methods.*

---

## 🚀 Why we exist

**Vuln Symphony Labs (VSL)** hosts hundreds of compact “toy” software systems. Each is intentionally vulnerable and designed to be spun up quickly so that agents, scanners, and research prototypes can be tested against **unseen** code.

*Some systems ship Docker/Compose files, others rely on plain scripts or cloud manifests—choose whatever fits your test harness.*

**Key principles**

* **No data leakage 🛡️** — Repositories are private and licensed to forbid any ML/LLM training on the code.
* **Fine‑grained checkout 🎻** — One repo per system (`vs‑<slug>`); cloning stays fast and permissions stay tight.
* **Consistent metadata 📂** — Every repo inherits the same `vs-template` skeleton; all vulnerability specs live in \`\` for automated discovery.

---

## 📜 Licence & AI‑Training Prohibition

```
Copyright © 2025 Vuln Symphony Labs. All rights reserved.

Permission is granted to Authorized Users (listed in ACCESS.md inside each repo) to
view, run, and modify this repository for research and internal testing only.

**The contents may NOT be used to train, fine‑tune, evaluate, or otherwise improve
any machine‑learning model of any kind, including large language models.**

Redistribution or public disclosure is prohibited without written permission.
```

(Every `vs-*` repository automatically inherits this licence from the `vs-template`.)

---

## 🗂️ Repository Layout

| Folder / Repo                             | Purpose                                           |
| ----------------------------------------- | ------------------------------------------------- |
| `.github/profile/README.md` *(this file)* | Landing page you’re reading                       |
| `vs-template`                             | Template repo—common skeleton, licence, CI checks |
| `vs-…` repos                              | Individual vulnerable systems (private)           |
| `vsl-index` *(coming soon)*               | YAML manifest + CLI that pulls a system on demand |

---

## 📝 Prompt Library

> *These are the LLM prompts we use to generate the vulnerable systems.  Feel free to fork and iterate internally—but remember the licence above still applies.*

```markdown
%s
```

*Add future prompts by creating **`** files and embedding them here in additional **`** blocks.*

---

## 👥 Getting Access

1. Ask an owner to add you to the **vuln-authors** or **vuln-viewers** team.
2. Clone a system repo, e.g.:

   ```bash
   gh repo clone VulnSymphonyLabs/vs-iot-drone
   ```
3. Follow that repo’s \`\` (or `docker compose up`, or `scripts/setup.sh`) to launch the system locally.

---

## 🔧 Contributing a New System

1. Create the repo:

   ```bash
   gh repo create VulnSymphonyLabs/vs-<slug> --template vs-template --private
   ```
2. \*\*Document every seeded vulnerability under \*\*\`\` (one file per CWE/CVE).
   **Do *****not***** list vulnerabilities anywhere else, and do *****not***** encode them in the repo name.**
3. Provide run instructions in `RUN.md` (Docker, script, cloud deploy, etc.).
4. Open a PR; CODEOWNERS will tag reviewers for structure/licence checks.
5. After merge, append the slug to `vsl-index/manifest/systems.yml`.

---

Happy testing—may your agents catch every bug! 🎶🔐

