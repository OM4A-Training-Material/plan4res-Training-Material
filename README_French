# 🧰 Plan4res – Section Formation

## 📘 Introduction

**plan4res** est un outil d’optimisation et de simulation des systèmes électriques, composé de trois modèles intégrés :

- **CEM** – *Modèle d’expansion de capacité* : optimise les investissements dans la production, le stockage et les interconnexions pour répondre à la demande tout en minimisant les coûts totaux du système.
- **SSV** – *Modèle de valorisation du stockage saisonnier* : calcule les « valeurs de l’eau » pour optimiser l’utilisation du stockage saisonnier lors des périodes de forte demande.
- **SIM** – *Modèle de simulation* : effectue l’engagement unitaire et le dispatch horaire du système sur une année complète.

L’écosystème plan4res inclut :
- 🔧 `p4r-env` : environnement d’exécution développé par CRAY & HPE ([GitLab](https://gitlab.com/cerl/plan4res/p4r-env))  
- 📦 Modèles de base construits avec la bibliothèque `SMS++` de l’Université de Pise ([GitLab](https://gitlab.com/smspp/smspp-project))  
- 🛠️ Outils Python pour le traitement et la visualisation des données ([plan4res-scripts](https://github.com/plan4res/plan4res-scripts))  
- 🔁 Scripts de gestion des workflows ([include](https://github.com/plan4res/include))  

---

## 📚 Matériel de Formation

Vous pouvez accéder à toute la documentation et aux tutoriels pour installer et utiliser plan4res :

- 📄 [Manuel Utilisateur (PDF)](https://github.com/plan4res/documentation/blob/main/plan4resUserManual.pdf)  
  Comprend :
  - Installation sous Linux et Windows
  - Description des modules et workflows
  - Structure des fichiers d’entrée/sortie et formats
  - Tutoriels sur l’exécution des modules et l’interprétation des résultats

- 📊 [Introduction à plan4res](https://github.com/OM4A-Training-Material/plan4res-Training-Material/blob/main/plan4resIntroduction.pdf)  
  Vue d’ensemble des modèles mathématiques et de leur mise en œuvre

- 🛠️ [Guide d’installation (diapositives)](https://github.com/OM4A-Training-Material/plan4res-Training-Material/blob/main/plan4resInstall.pdf)  
  Étapes d’installation pas à pas

- 🧪 [Comment exécuter plan4res](https://github.com/OM4A-Training-Material/plan4res-Training-Material/blob/main/plan4resRun.pdf)  
  Guide pratique pour exécuter les modèles

---

## 💾 Installation

- Système recommandé : **Linux** (ou Windows Subsystem for Linux)
- Espace disque requis : **min. 3 Go**

### 🔧 Étapes :
1. Cloner le dépôt d’installation :
   ```bash
   git clone https://github.com/plan4res/install
   cd install
   ./plan4res_install.sh
   ```
   > Utilisez `./plan4res_install.sh -H` pour l’aide et les options.

2. Si vous utilisez un serveur ou un dépôt externe, configurez votre utilisateur :
   ```bash
   ./user_init_plan4res -D P4R_INSTALL_DIR
   ```
   > Utilisez `./user_init_plan4res.sh -H` pour plus d’infos.

---

## 🚀 Exécuter plan4res

Vous pouvez utiliser le [jeu de données d’exemple (toyDataset)](https://github.com/plan4res/toyDataset).

1. **Créer le jeu de données** à partir des entrées IAMC et des séries temporelles :
   ```bash
   p4r CREATE toyDataset
   ```

2. **Formater les données NetCDF** pour SSV (requis par SMS++) à partir des fichiers CSV de plan4res pour chaque module – stockage saisonnier (SSV), simulation (SIM) et expansion de capacité (CEM) :
   ```bash
   p4r FORMAT toyDataset -M optim    # pour SSV
   p4r FORMAT toyDataset -M simul    # pour SIM
   p4r FORMAT toyDataset -M invest   # pour CEM
   ```

3. **Exécuter les modules individuellement** :
   ```bash
   p4r SSV toyDataset     # Stockage saisonnier
   p4r SIM toyDataset     # Simulation
   p4r CEM toyDataset     # Expansion de capacité
   ```

4. **Exécuter un workflow complet** :
   ```bash
   p4r SSVandSIM          # SSV + SIM combinés
   p4r SSVandCEM          # SSV + CEM combinés
   ```

---

## 🎥 Support Vidéo Pas-à-pas

Vous pouvez retrouver tous les tutoriels sur  
<a href="https://www.youtube.com/playlist?list=PLHN93NPePQ1JNz3JROb_sVbF5pjOG-EDx" target="_blank" style="text-decoration: none;">
  <img src="https://cdn.simpleicons.org/youtube/FF0000/16" alt="YouTube" height="16" style="vertical-align: text-bottom; margin-left: 4px;">
</a>

---

## ❓ Besoin d’aide ?

Consultez notre page [Questions & Réponses](docs/faq.md) pour les problèmes fréquents et conseils.

---

## 📬 Contact

Pour toute demande d’assistance ou d’informations, utilisez le [formulaire de contact plan4res](https://plan4res.github.io/contact/contact.html).

---

Références :  
Dépôt officiel : [https://github.com/plan4res](https://github.com/plan4res)
