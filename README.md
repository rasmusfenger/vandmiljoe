# Vandmiljø – interaktiv visualisering

Dette projekt samler overvågningsdata om det danske vandmiljø og gør dem tilgængelige gennem en interaktiv webside (hostet via GitHub Pages).  
Første datasæt er **ålegræs (Zostera marina)**, men projektet udvides til også at inkludere ilt, miljøfarlige stoffer m.m.

👉 [Se den interaktive side her](https://DIT_GITHUB_BRUGERNAVN.github.io/vandmiljoe/)

---

## 📂 Projektstruktur

```
vandmiljoe/
├── data/                # Rådata og mellemformater (IGNORERET i git)
│   ├── raw/             # Originale CSV-filer fra Danmarks Miljøportal
│   ├── parquet/         # Konverterede Parquet-filer
│   └── processed/       # Filtreret data klar til analyse
│
├── scripts/             # Python scripts
│   ├── build_json.py    # Genererer JSON-filer til web
│   └── notebooks/       # Jupyter notebooks til analyse og prototyping
│
├── web/                 # Webdelen (ligger på GitHub Pages)
│   ├── index.html       # Hovedsiden (kort + UI)
│   └── json/            # JSON-udtræk til visualisering
│
├── .gitignore
└── README.md
```

---

## ⚙️ Sådan kører du projektet lokalt

1. **Klon repoet**
   ```bash
   git clone https://github.com/DIT_GITHUB_BRUGERNAVN/vandmiljoe.git
   cd vandmiljoe
   ```

2. **Installer afhængigheder**  
   Projektet bruger Python 3.10+.
   ```bash
   pip install -r requirements.txt
   ```

3. **Konverter data** (fra CSV til Parquet)  
   Læg rå CSV’er i `data/raw/` og kør:
   ```bash
   python scripts/build_json.py
   ```

   Dette genererer fx `web/json/aalegraes_stations.json`.

4. **Kør websiden lokalt**
   ```bash
   cd web
   python -m http.server
   ```
   Åbn [http://localhost:8000](http://localhost:8000) i browseren.

---

## 🌍 GitHub Pages

Websiden hostes automatisk via GitHub Pages.  
Når du pusher ændringer til `main` branch, bliver de synlige her:

👉 https://DIT_GITHUB_BRUGERNAVN.github.io/vandmiljoe/

---

## 📊 Datasæt

- **Ålegræs (Zostera marina)**  
  Kilde: [Danmarks Miljøportal](https://miljoeportal.dk) (NOVANA-overvågningen).  
  Rå CSV’er findes i `data/raw/` (ikke inkluderet i repoet, da de er store).  
  Data konverteres til Parquet og derefter til JSON til brug i webapplikationen.

Fremtidige datasæt:
- Ilt
- Miljøfarlige stoffer
- Flere biologiske og kemiske indikatorer

---

## 👩‍💻 Bidrag

- Projektet er tænkt som en **prototype**, der kan udvides.  
- Pull requests og idéer til nye funktioner/data er velkomne.  

---

## 📄 Licens

Kode: MIT License  
Data: Følg datakildens licensbetingelser (Danmarks Miljøportal / NOVANA).
