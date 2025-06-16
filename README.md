# 🧾 comparateurfunc – Déploiement d'une Azure Function Python

Ce dépôt contient une application **Azure Function en Python** dédiée à des traitements automatisés (par exemple, des comparaisons comptables ou des exports Excel), avec un workflow GitHub Actions pour déploiement continu.

---

## 🚀 Objectif

Automatiser le **déploiement continu** d’une Azure Function Python à chaque push sur la branche `main`, via GitHub Actions.

---

## 🧰 Technologies utilisées

- **Python 3.11**
- **Azure Functions**
- **GitHub Actions**
- **Oryx Build System**
- **Azure Publish Profile (authentification via secret GitHub)**

---

## 🔄 Déploiement automatique avec GitHub Actions

### 📂 Fichier concerné :
`.github/workflows/deploy.yml`

### 🔁 Déclenchement :
- Automatique sur `push` dans la branche `main`
- Manuel via l’interface GitHub (onglet **Actions**)

### ⚙️ Étapes du workflow :

1. **Checkout du code**  
2. **Installation de Python 3.11**
3. **Déploiement vers Azure Function avec Oryx** (installe automatiquement les dépendances via `requirements.txt`)

---

## 🔐 Configuration requise

Ajoute ce secret dans ton dépôt GitHub :

| Nom du secret | Description |
|---------------|-------------|
| `AZUREAPPSERVICE_PUBLISHPROFILE_xxxxxxxxxxxxxxxxxxxxxxxx` | Profil de publication Azure (.PublishSettings) |

> 📌 Pour obtenir ce profil :  
> Va dans le **Portail Azure > ta Function App > Centre de déploiement > Obtenir le profil de publication**.

---

## ✅ Résultat attendu

À chaque mise à jour du code sur `main`, GitHub Actions :
- installe les dépendances Python (requests, pandas, etc.)
- déploie automatiquement le code vers Azure Functions
- rend la fonction immédiatement disponible en production

---

## 🧪 Exemple de cas d’usage

Fonction appelée via un webhook HTTP qui :
- compare des fichiers Excel
- génère un fichier ZIP de résultats
- l’envoie automatiquement sur SharePoint ou autre stockage

---

## 📬 Contact

Pour toute question ou amélioration, n’hésitez pas à ouvrir une **Issue** ou un **Pull Request**.
