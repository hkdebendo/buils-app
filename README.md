# Score X — Build desktop (Windows)

Build de test de l'application **Score X** (scoring de microcrédit explicable,
hors-ligne) pour l'équipe — hackathon CIF-DigiCoop-WA+ 2026.

Le code source complet vit sur le dépôt principal du projet (GitLab interne).
Ce dépôt sert uniquement à distribuer un **build Windows prêt à l'emploi** pour
que l'équipe puisse l'installer et le tester sans avoir à compiler quoi que ce
soit (Flutter, PyInstaller, etc.).

## Installer et lancer

1. Aller dans l'onglet **[Releases](../../releases/latest)** de ce dépôt.
2. Télécharger **`ScoreX-Windows.zip`**.
3. Dézipper où tu veux (ex. `C:\ScoreX`).
4. Lancer **`scorex.exe`**.

L'application fonctionne **entièrement hors-ligne** (aucune connexion requise) :
sur l'écran de connexion, choisir le mode **Local**.

### Comptes de démonstration

| Rôle | Email | Mot de passe |
|---|---|---|
| Conseiller crédit | aurelscore@gmail.com | aurelscore |
| Conseiller crédit | fideliascore@gmail.com | fideliascore |
| Conseiller crédit | lionelscore@gmail.com | lionelscore |
| Chef d'agence | ricardoscore@gmail.com | ricardoscore |

## Extraction automatique des documents justificatifs (OCR, optionnel)

Par défaut, `ScoreX-Windows.zip` suffit pour utiliser l'application normalement
(scoring, recommandation, synchro locale, etc.). Une fonctionnalité
**optionnelle** permet en plus d'extraire automatiquement certains champs
(revenu, etc.) depuis un document scanné (photo/PDF) : pour l'activer, deux
fichiers supplémentaires sont disponibles sur la page de release :

- **`tesseract.zip`** → dézipper dans `engine\tesseract\` (à côté de
  `engine\scorex_engine.exe`, dans le dossier où tu as dézippé l'app).
- **`qwen2.5-1.5b-instruct-q4_k_m.gguf`** → placer dans `engine\models\llm\`
  (créer le dossier si besoin).

Sans ces deux éléments, l'app fonctionne normalement, juste sans lecture
automatique de document (saisie manuelle du revenu à partir du texte OCR
affiché, ou fonctionnalité simplement absente si `tesseract.zip` n'est pas
présent non plus).

## Remarques

- Premier lancement un peu lent (scan antivirus sur les ~530 Mo de
  l'exécutable + dépendances) : c'est normal, le moteur reste ensuite résident.
- Pas d'installeur pour l'instant : c'est un build de test, à dézipper/lancer
  tel quel.
