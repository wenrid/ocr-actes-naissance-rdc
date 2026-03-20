# 📜 Numérisation Automatique des Actes de Naissance Manuscrits — RDC

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-2.x-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Colab](https://img.shields.io/badge/Google%20Colab-A100%2080GB-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

> Projet de Master 2 — International School (IS) / VNU Hanoi  
> Option : Systèmes Intelligents et Multimédia  
> Auteur : **RIDORE Wenchel & KIMBANGI MENAKUNTIMA Rabbi**
> Encadrant : **Dr. Ho Tuong Vinh**  

---

## 🎯 Description

Ce projet développe un pipeline complet de **reconnaissance automatique de texte manuscrit (OCR)** appliqué aux actes de naissance de la République Démocratique du Congo (RDC).

Le modèle **LightOnOCR-2-1B** (1 milliard de paramètres) a été fine-tuné via **LoRA** sur un corpus de **300 certificats** (40 réels + 260 synthétiques) pour reconnaître :
- Les noms congolais (Kabongo, Tshilombo, Mbuyi...)
- La structure administrative des actes RDC (32 champs)
- Les dégradations tropicales (jaunissement, taches, flou)

---

## 📊 Résultats

| Métrique | Valeur |
|---|---|
| **CER** (Character Error Rate) | 10,95% |
| **WER** (Word Error Rate) | 9,15% |
| **F1-Score** | 93,7% |
| **Recall** | 96,0% |
| **Précision** | 91,5% |

---

## 🏗️ Architecture du Pipeline

```
Image PNG (300 DPI)
      │
      ▼
LightOnOCR-2-1B fine-tuné
      │
      ▼
Texte brut (génération autorégressive)
      │
      ▼
Post-correction regex (40 champs)
      │
      ▼
Export Word + SQLite
```

---

## 📁 Structure du Projet

```
ocr-actes-naissance-rdc/
├── app.py                          ← Application Streamlit
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── pipeline_complet.ipynb      ← Fine-tuning + Évaluation
├── graphiques/
│   ├── 1_tp_fp_fn.png
│   ├── 2_precision_recall_f1.png
│   ├── 3_types_erreurs.png
│   ├── 4_matrice_confusion.png
│   ├── 5_camembert_erreurs.png
│   ├── 6_precision_rappel.png
│   └── 7_cer_par_certificat.png
└── rapport/
    ├── rapport_evaluation.tex
    └── rapport_evaluation.pdf
```

---

## 🚀 Installation

```bash
git clone https://github.com/wenrid/ocr-actes-naissance-rdc.git
cd ocr-actes-naissance-rdc
pip install -r requirements.txt
```

---

## 💻 Lancer l'Application

```bash
streamlit run app_rdc.py
```

---

## 📦 Modèle Fine-tuné

Le modèle `modele_merged_complet` (~2 GB) est hébergé sur Google Drive
en raison de sa taille. Contactez-nous pour y accéder.

Le modèle de base est disponible sur HuggingFace :
[lightonai/LightOnOCR-2-1B](https://huggingface.co/lightonai/LightOnOCR-2-1B)

---

## 📓 Notebook

Le notebook `pipeline_complet.ipynb` contient 3 parties :

| Partie | Contenu |
|---|---|
| 🔧 Setup | Vérification GPU, installation, montage Drive |
| 🏋️ Fine-tuning | LoRA, preprocessing, entraînement, sauvegarde |
| 📊 Évaluation | Inférence 45 certificats, métriques, 7 graphiques |

[![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wenrid/ocr-actes-naissance-rdc/blob/main/notebooks/pipeline_complet.ipynb)

---

## 🛠️ Technologies

![LightOnOCR](https://img.shields.io/badge/-LightOnOCR--2--1B-8E44AD?style=flat-square&logoColor=white)
![LoRA](https://img.shields.io/badge/-LoRA%20PEFT-E74C3C?style=flat-square&logoColor=white)
![SQLite](https://img.shields.io/badge/-SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![OpenCV](https://img.shields.io/badge/-OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![Transformers](https://img.shields.io/badge/-Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

---

## 👥 Auteurs

- **Rabbi KIMBANGI MENAKUNTIMА**
- **Wenchel RIDORE** — [github.com/wenrid](https://github.com/wenrid)

