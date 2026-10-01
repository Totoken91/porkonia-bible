# Garde-fous — PorkOS FUN / PorkOS GAME

Deux projets, deux étiquettes, utilisées partout (dépôts, dossiers, conversations, noms de fichiers) :

| | **FUN** | **GAME** |
| --- | --- | --- |
| Nom complet | Porkonia Canal Historique | PorkOS — *Save Him a Plate* |
| Public | Toi et les collègues | Public anglophone |
| Langue | Français | Anglais (noms propres en français) |
| Personnages | Vrais noms, vraies photos, Sofiane Douzi | Noms PorkOS, nouveaux visages, Tonton |
| Code | `porkonia-os`, branche `porkos` | Dépôt séparé `porkos-game` (recommandé) |
| Site | porkos.vercel.app | Nouveau projet Vercel (ex. porkos-game.vercel.app) |
| ChatGPT | Projet « PORKONIA FUN » | Projet « PORKOS GAME » |
| Images | Dossier `FUN/` | Dossier `GAME/`, fichiers préfixés `game-` |

---

## 1. Le code : un dépôt séparé plutôt qu'une branche

Une branche, c'est deux versions dans le même dossier : on peut se tromper de branche, fusionner par erreur, ou Claude Code peut « aider » en recopiant d'un côté à l'autre. **Un dépôt séparé** rend l'erreur presque impossible : deux dossiers, deux sites, rien en commun.

Comment faire (une seule fois) :
1. Sur GitHub, crée un nouveau dépôt vide **`porkos-game`**, en **privé** jusqu'à la sortie.
2. Donne cette consigne à Claude Code, dans le dépôt FUN :
   « Pousse une copie de la branche `porkos` dans le nouveau dépôt `Totoken91/porkos-game` (branche `main`), sans rien modifier dans `porkonia-os`. »
3. Dans Vercel, crée un **nouveau projet** relié à `porkos-game`. Ne touche pas au projet actuel.
4. À partir de là, **tout le travail GAME se fait dans `porkos-game`**, avec le prompt GAME.

Si tu préfères rester sur une seule branche malgré tout, le prompt GAME contient déjà les garde-fous (vérification de la branche, `CLAUDE.md`, test qui bloque les anciens noms).

---

## 2. Bloc à ajouter dans le projet FUN

Ajoute ce bloc **en tête du `CLAUDE.md` de la branche `porkos`** (tu peux le coller toi-même, ou demander à Claude Code de le faire et rien d'autre) :

```
# ⚠ CE DÉPÔT EST PorkOS FUN (Porkonia Canal Historique, projet perso, en français)
- Ce n'est PAS PorkOS GAME (dépôt `porkos-game`, version publique anglophone).
- Ici on garde : les vrais noms des collègues, leurs vraies photos, Sofiane Douzi, Douzi City, la Douzi Ambrée, le français.
- Ne jamais appliquer ici les renommages des collègues, la traduction anglaise ou les nouveaux visages de la version GAME.
- Exception (fusion progressive, 1er oct. 2026) : Tonton, le Premier Convive, et Grand-Couvert font partie du FUN. Douzi y devient un personnage secondaire.
- Ne jamais importer de code ou de contenu depuis `porkos-game`.
- Si une demande parle de « version publique », « GAME », « Save Him a Plate » ou « anglais », s'arrêter et demander confirmation.
```

---

## 3. ChatGPT : deux projets séparés

Crée **deux Projets** dans ChatGPT, chacun avec ses fichiers et ses instructions. Ne génère jamais d'image GAME dans une conversation FUN, ni l'inverse.

**Instructions du projet « PORKONIA FUN »** :

```
Projet PORKONIA FUN (Porkonia Canal Historique). Langue : français.
Personnages : vrais noms et vraies photos de référence des collègues, Sofiane Douzi inclus.
Tonton, le Premier Convive, fondateur sans visage, est au centre du pays ; Sofiane Douzi est un personnage secondaire (Premier Servant de la Table). Ne jamais utiliser les noms ou visages de remplacement des collègues (Steeve Carrié, DJ Toulemonde, etc.).
```

**Instructions du projet « PORKOS GAME »** :

```
Project PORKOS GAME ("Save Him a Plate"), public English-language version of Porkonia.
Characters use their PorkOS names and ONLY the new reference portraits (ref-01 to ref-16) or the approved photos of consenting colleagues.
Never use Sofiane Douzi, Douzi City, Douzi Ambrée or any real photo of a colleague who refused. Tonton (the Premier Convive) never shows his face.
All in-image text in English, except proper names which stay French.
```

Mets dans chaque projet ses propres fichiers : la bible FUN d'un côté, le Canon Maître et les portraits `ref-` de l'autre.

---

## 4. Réflexes au quotidien

- Commence chaque demande (à moi, à Claude Code, à ChatGPT) par **« FUN : »** ou **« GAME : »**.
- Préfixe tous les fichiers GAME par `game-` (images, exports, documents).
- Avant de coller une image ou un texte d'un projet dans l'autre, pose-toi une question : est-ce qu'il contient un vrai nom, une vraie tête ou du français ? Si oui, il ne passe pas de FUN vers GAME tel quel.
