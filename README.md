# 🐞 Gestion des vulnérabilités — Nessus Essentials & Nmap

> Découverte du réseau, scan de vulnérabilités, priorisation des **CVE** selon leur criticité et **rapport de remédiation**.

![Scanner](https://img.shields.io/badge/Scanner-Nessus%20Essentials-00a3e0) ![Réseau](https://img.shields.io/badge/R%C3%A9seau-Nmap-4b5563) ![CVE](https://img.shields.io/badge/Analyse-CVE%20%2F%20CVSS-c00) ![Statut](https://img.shields.io/badge/statut-termin%C3%A9-2FA35F)

**Auteur :** Kouakou François Komenan — Analyste SOC / Technicien Réseau, Abidjan
**Portfolio :** https://thefulkom.tech/portfolio/

---

## 🎯 Objectif

Appliquer un cycle complet de gestion des vulnérabilités sur un réseau de laboratoire :

**Découvrir → Scanner → Analyser → Prioriser → Corriger → Vérifier**

## 🏗️ Environnement

```
 ┌───────────────────────┐        scans         ┌──────────────────────────┐
 │  Poste d'analyse      │ ───────────────────▶ │  Réseau de laboratoire   │
 │  Nmap + Nessus        │                      │  (serveurs, postes, VM)  │
 └───────────────────────┘                      └──────────────────────────┘
```

> 📸 Ajoute ton schéma réseau : `images/01-reseau-lab.png`

## ⚙️ Démarche

### 1. Découverte avec Nmap
Identification des hôtes actifs, des ports ouverts et des versions de services.

```bash
# Hôtes actifs du réseau
nmap -sn 192.168.X.0/24

# Ports, services et versions d'une cible
nmap -sV -sC -p- 192.168.X.Y
```
<!-- ✏️ Remplace 192.168.X.* par l'adressage de ton lab -->

### 2. Scan de vulnérabilités avec Nessus Essentials
- Création d'une politique de scan (*Basic Network Scan*).
- Scan des hôtes découverts à l'étape 1.
- Export des résultats.

### 3. Analyse et priorisation des CVE
Chaque vulnérabilité est classée selon son score **CVSS** et son exposition :

| Niveau | Score CVSS | Délai de traitement visé |
|---|---|---|
| 🔴 Critique | 9.0 – 10.0 | Immédiat |
| 🟠 Élevé | 7.0 – 8.9 | Sous 7 jours |
| 🟡 Moyen | 4.0 – 6.9 | Sous 30 jours |
| 🟢 Faible | 0.1 – 3.9 | Planifié |

### 4. Mesures correctives
Pour chaque vulnérabilité prioritaire : mise à jour, changement de configuration, fermeture de service inutile ou mesure compensatoire.

### 5. Rapport
Rédaction d'un rapport d'analyse : synthèse, liste des vulnérabilités priorisées, recommandations.

## 📊 Résultats

<!-- ✏️ À compléter avec tes vrais chiffres -->
| | Nombre |
|---|---|
| Hôtes scannés | _à compléter_ |
| Vulnérabilités critiques | _à compléter_ |
| Vulnérabilités élevées | _à compléter_ |
| Vulnérabilités moyennes | _à compléter_ |

**Exemples de CVE identifiées :** _à compléter (ex. CVE-XXXX-XXXXX — service concerné — correctif appliqué)_

## 📄 Rapport

Dépose ton rapport PDF ici : `rapport-analyse-vulnerabilites.pdf`

## 📸 Captures d'écran

| Fichier à déposer dans `images/` | Contenu |
|---|---|
| `01-reseau-lab.png` | Schéma du réseau de laboratoire |
| `02-nmap-decouverte.png` | Résultat de la découverte Nmap |
| `03-nessus-politique.png` | Configuration du scan Nessus |
| `04-nessus-resultats.png` | Synthèse des vulnérabilités par criticité |
| `05-detail-cve.png` | Détail d'une CVE critique |

![Réseau du lab](images/01-reseau-lab.png)
![Découverte Nmap](images/02-nmap-decouverte.png)
![Politique Nessus](images/03-nessus-politique.png)
![Résultats Nessus](images/04-nessus-resultats.png)
![Détail CVE](images/05-detail-cve.png)

## 🧠 Compétences démontrées

`Scan de vulnérabilités` · `Nmap` · `Nessus` · `CVE / CVSS` · `Priorisation des risques` · `Remédiation` · `Rédaction de rapport`

---

⚠️ *Scans réalisés uniquement sur un réseau de laboratoire m'appartenant. Ne scannez jamais un réseau sans autorisation écrite.*
