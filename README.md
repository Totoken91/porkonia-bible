# Porkonia — La Bible

**Source de vérité unique de Porkonia Prod.** Tout ce qui est canon est écrit ici. Tout le reste (Claude Docs, projets ChatGPT, notes, vidéos) n'est qu'une copie ou une illustration.

Kenny, Claude et ChatGPT peuvent lire et modifier ce dépôt. Les règles sont dans [`REGLES_IA.md`](REGLES_IA.md). **Toute IA doit les lire avant de toucher à quoi que ce soit.**

## Les deux projets

| Étiquette | Projet | Langue | Code |
| --- | --- | --- | --- |
| **FUN** | Porkonia Canal Historique : projet perso, vrais collègues, Douzi | Français | `porkonia-os`, branche `porkos` |
| **GAME** | PorkOS — *Save Him a Plate* : jeu ARG public | Anglais (noms propres en français) | `porkos-game` |

## Plan du dépôt

```
README.md            ← tu es ici
REGLES_IA.md         ← règles pour Claude, ChatGPT, Codex (à lire en premier)
GARDE-FOUS.md        ← séparation FUN / GAME au quotidien
JOURNAL.md           ← décisions validées + questions ouvertes

COMMUN/              ← le monde, valable pour FUN et GAME
  01-vision.md
  02-lois-du-monde.md
  03-le-fond-brume.md
  04-voix-et-humour.md
  05-direction-visuelle.md
  06-systeme-de-canon.md
  07-personnages-registre.md   ← correspondance noms réels ↔ noms PorkOS

FUN/                 ← uniquement le projet perso
  README.md
  audit-site-porkopedia.md

GAME/                ← uniquement le jeu public
  README.md
  tonton-premier-convive.md
  conception.md
  porkopedia-porkos.md
  porkos-arg.md
  langue-anglais.md
  glossaire-fr-en.md
  prompts/
    claude-code-porkos-game.md
    images-chatgpt.md
```

## Ordre de priorité si deux sources se contredisent

1. `JOURNAL.md` (la décision la plus récente l'emporte)
2. `COMMUN/`, puis `FUN/` ou `GAME/` selon le projet
3. Le site Porkopédia
4. PorkOS et les contenus ARG (ils peuvent mentir, c'est voulu)
5. Les vidéos et les images
