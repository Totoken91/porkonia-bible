# Règles pour les IA (Claude, ChatGPT, Codex)

À lire en entier avant toute lecture ou modification de ce dépôt.

## 0. Qui fait quoi

| Rôle | Claude | ChatGPT | Kenny |
| --- | --- | --- | --- |
| **Code** (PorkOS FUN et GAME, `porkonia-os`, `porkos-game`) | ✅ Seul responsable | ❌ Ne touche pas au code | Valide et teste |
| **Assets** (images, portraits, visuels, illustrations) | Écrit les prompts d'images si demandé | ✅ Seul responsable de la génération | Valide et choisit |
| **Rédaction** (notices, mails, dialogues, textes du jeu) | ✅ Contribue | ✅ Contribue | Relit |
| **Suivi du lore** (canon, journal, cohérence) | ✅ Contribue | ✅ Contribue | Seul à valider en « Canon » |

**En pratique :**
- **Claude** écrit et modifie le code. Quand du texte ou une règle de ce dépôt doit entrer dans le jeu, c'est Claude qui l'intègre dans le code.
- **ChatGPT** génère les images, en suivant `GAME/prompts/images-chatgpt.md` pour GAME et les portraits de référence (`ref-01` à `ref-16`). Il nomme les fichiers GAME avec le préfixe `game-`. Il ne modifie jamais de code.
- **Rédaction et lore** : les deux IA peuvent écrire dans ce dépôt, avec le statut « Proposition ». Quand l'une propose quelque chose, elle vérifie d'abord que ça ne contredit pas `COMMUN/` ni `JOURNAL.md`. Si elle repère une contradiction laissée par l'autre, elle la signale dans le journal au lieu de la corriger en silence.
- **Images → code** : ChatGPT livre les images à Kenny. Kenny les dépose dans le dépôt du jeu, ou les donne à Claude pour qu'il les intègre. Toute image encore à produire est listée dans `docs/IMAGES_A_PRODUIRE.md` du dépôt du jeu.

## 1. Savoir sur quel projet on travaille

- Chaque demande de Kenny commence normalement par **« FUN : »** ou **« GAME : »**.
- Si ce n'est pas le cas et que la demande touche aux personnages, aux noms, aux images ou à la langue : **demander** avant d'écrire.
- **FUN** = `FUN/` + `COMMUN/`. **GAME** = `GAME/` + `COMMUN/`.
- Ne jamais copier du contenu de `FUN/` vers `GAME/`, ni l'inverse.

## 2. Ce qui ne doit jamais apparaître dans le jeu

Ces éléments ne doivent jamais apparaître dans les contenus du jeu : textes, mails, notices, images, ni dans le dépôt `porkos-game`. Les fichiers de `GAME/` peuvent les citer uniquement pour dire de les éviter (listes d'interdits, tables de renommage).

- Sofiane Douzi, Douzi City, la Douzi Ambrée, la Sauce Douzi, le jeu de mots Douzi / douze.
- Les vrais noms des collègues : seulement les noms PorkOS (voir `COMMUN/07-personnages-registre.md`).
- Des données réelles : dates de naissance, communes, adresses, téléphones, employeur réel (Econocom).
- Le nom de scène « Fat Nigga ». Le personnage s'appelle **Fatbass**.
- Des étiquettes d'origine (« le Gitan », « collectionneur chinois », etc.).

## 3. Comment modifier

- **Une modification = un sujet.** Message de commit clair en français, par exemple : `GAME: ajoute 3 mails d'Honoré Mignot`.
- **Toute décision nouvelle** ajoute une ligne **en haut** du tableau de `JOURNAL.md`, avec :
  - la date ;
  - la décision ;
  - le statut : Canon, Proposition, Rumeur, Mensonge d'État, Archive altérée ou Hors-canon ;
  - l'auteur : Kenny, Claude ou ChatGPT.
- **Une IA n'écrit jamais « Canon » toute seule.** Elle écrit « Proposition ». Seul Kenny passe une ligne en Canon.
- **Ne jamais réécrire un fichier entier pour changer un paragraphe.** Modifier seulement la partie concernée.
- **Ne rien supprimer sans demande explicite.** Une idée rejetée passe en « Hors-canon » dans le journal.
- **ChatGPT / Codex** : travailler sur une branche et ouvrir une pull request. Kenny valide.
- **Claude** : peut pousser sur `main` quand Kenny le demande. Sinon, branche + pull request.

## 4. Règles de cohérence (résumé)

Les règles complètes sont dans `COMMUN/`. Les plus souvent oubliées :

- France rurale de montagne (esprit Savoie ou Jura). Présent porkonien : 2000-2008. PorkOS se passe en 2007.
- Le futur chromé est la propagande de Porkonia 3000.
- Monnaie : **Pork$** aujourd'hui, **Groin (GRN)** avant, « porko » en argot.
- Les gobelins réseau existent, l'État les nie. Running gag limité à une dizaine d'apparitions.
- GAME : Tonton, le Premier Convive, ne montre jamais son visage. On ne connaît pas son vrai prénom.
- GAME : B.R.U.M.E. n'a pas de notice dans le Porkopédia du jeu.

## 5. Format

- Markdown simple, en français (sauf les textes du jeu, en anglais).
- Moins de 500 lignes par fichier. Au-delà, découper.
- Pas de secrets, de mots de passe ni de clés d'API dans ce dépôt.
