# Phenopacket Generator

A lightweight, **browser‑based** tool for creating [GA4GH Phenopacket] YAML files from clinical and genomic information.  
Everything runs client‑side in plain HTML + JavaScript—no build step or backend required.

---

## ✨ Features

|  |  |
|---|---|
| **Interactive form** | • Basic subject metadata<br>• Remote HPO lookup (Select2 + Jackson Lab API)<br>• VCF filename/URL field |
| **Instant YAML** | Standards‑compliant phenopacket YAML generated in‑browser with **js‑yaml** |
| **Download** | Saves the YAML to **`<subject‑ID>.yml`** (default: `unknown.yml`) |
| **100 % client‑side** | Works offline once opened; deploy on any static host (GitHub Pages, Netlify, S3, …) |

---

## 🚀 Quick start

```bash
# clone the repo
git clone https://github.com/<you>/phenopacket-generator.git
cd phenopacket-generator

# no build step – just open the file
open index.html        # or use any static server
```

Serve locally on <http://localhost:8000/>:

```bash
python3 -m http.server
```

Open the URL in your browser.

---

## 🗂 Project structure

```
phenopacket-generator/
├── phenopacket.html          # main app (Phenopacket builder)
└── README.md
```

*All CSS/JS deps are loaded from CDNs; no `node_modules` needed.*

---

## 🛠 Tech stack

| Purpose | Library |
|---------|---------|
| CSS utility framework | [Tailwind CSS (Play CDN)] |
| Ontology search UI | [Select2] + [jQuery] |
| HPO API | Jackson Laboratory `https://ontology.jax.org/api/hp/search` |
| YAML serialisation | [js‑yaml] |

---

## 📋 Usage tips

1. **Basic Details** – fill in ID, name, sex, age.  
2. **Phenotype** – type ≥ 2 chars to search HPO, hit **Enter** to add.  
3. *(Optional)* enter a local VCF filename or public URL.  
4. Click **Generate YAML** – YAML appears in the box.  
5. Click **Download** – file saves as `ID.yml` (or `unknown.yml`).  

---

## 🗺 Roadmap

- [ ] JSON Schema validation of generated phenopacket.  
- [ ] Dark‑mode toggle.

Pull requests welcome!

---

## 📝 License

**MIT** © 2025

---

[GA4GH Phenopacket]: https://phenopacket-schema.readthedocs.io/
[Tailwind CSS (Play CDN)]: https://tailwindcss.com/docs/installation/play-cdn
[Select2]: https://select2.org
[jQuery]: https://jquery.com
[js‑yaml]: https://github.com/nodeca/js-yaml
