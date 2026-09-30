# Prompt pour Claude Code — PorkOS, version publique (jeu ARG anglophone)

> À coller dans Claude Code, sur le dépôt `Totoken91/porkonia-os`, **dans la nouvelle branche publique** créée à partir de `porkos`.
> Fichier joint à lui donner avec ce prompt : `Porkonia_Canon_Maitre.md` (la bible du monde, source de vérité).

---

## 0. Contexte

Tu travailles sur **PorkOS**, un faux système d'exploitation jouable dans le navigateur (Next.js, export statique, voir `README.md` et `docs/ARCHITECTURE.md`). Tout le contenu vit dans des **packs de contenu** (`src/content/packs/`), pas dans les composants.

Il existe deux projets, sous le label **Porkonia Prod** :

| Projet | Branche | Langue | Contenu |
| --- | --- | --- | --- |
| **Porkonia Canal Historique** (projet perso) | `porkos` | Français | Édition Citoyenne actuelle, collègues réels, Sofiane Douzi |
| **PorkOS** (jeu ARG public) | **cette branche** | **Anglais** | Personnages renommés, Tonton, le poste de Colette |

**Ne touche jamais à la branche `porkos`.** Tout se fait ici.

Le jeu public s'appelle **PorkOS**, slogan : ***Save Him a Plate***.

Lis `Porkonia_Canon_Maitre.md` en entier avant de commencer : il contient la vision (Surface / Fond), les lois du monde, le ton, B.R.U.M.E., le Fondateur (Tonton), les noms définitifs et le journal des décisions. En cas de doute, **le Canon Maître fait foi** ; s'il ne répond pas, pose-moi la question au lieu d'inventer.

---

## 0 bis. Garde-fous FUN / GAME (à faire en tout premier)

Deux projets coexistent et **ne doivent jamais se mélanger** :

| Étiquette | Nom | Dépôt / branche | Site | Langue |
| --- | --- | --- | --- | --- |
| **FUN** | Porkonia Canal Historique (PorkOS Édition Citoyenne) | `porkonia-os`, branche `porkos` | porkos.vercel.app | Français |
| **GAME** | PorkOS — *Save Him a Plate* | **ce dépôt / cette branche** | projet Vercel séparé | Anglais |

Avant toute autre tâche :

1. Vérifie où tu es (`git remote -v`, `git branch --show-current`). Si tu es sur la branche `porkos` ou dans le dépôt FUN, **arrête-toi et préviens-moi**.
2. Crée à la racine un fichier **`PROJET_GAME.md`** et ajoute en tête de `CLAUDE.md` ce bloc :

   ```
   # ⚠ CE DÉPÔT EST PorkOS GAME (version publique anglophone, « Save Him a Plate »)
   - Ce n'est PAS le projet FUN (branche `porkos`, Édition Citoyenne, en français, avec Douzi et les vrais collègues).
   - Ne jamais fusionner, rebaser, cherry-picker ni copier du code ou du contenu vers la branche `porkos`.
   - Ne jamais importer de contenu depuis `porkos` sans le passer par les renommages et la traduction du prompt GAME.
   - Tous les textes du jeu sont en anglais ; les noms propres restent en français (voir docs/GLOSSAIRE_FR_EN.md).
   ```
3. Ajoute un **test de sécurité** `tests/game-guard.test.ts` qui échoue si l'un de ces mots apparaît dans `src/` ou `public/` (sans tenir compte de la casse ni des accents) : `douzi`, `sofiane`, `viteau`, `alvarez`, `ranga`, `lelouch`, `wilfrite`, `edwin valentin`, `fat nigga`, `martin chou`, `jox`, `fontanillas`, `bernis`, `mano`, `tchimbakala`, `matoutou`, `douala`, `moume`, `devilleneuve`, `netamiaou`, `lulenge`, `stanley ferret`, `pichoff`, `pierrick`, `mauriac`, `bilel`, `dren`, `desaintfuscien`, `econopork`, `gometz`. (Ajuste la liste pour éviter les faux positifs évidents, par exemple `mano` à l'intérieur d'un autre mot : cherche des mots entiers.) Ce test doit tourner avec `npm test`.
4. Change le titre de la page et l'écran de démarrage pour afficher clairement **« PorkOS — Save Him a Plate »**, jamais « Édition Citoyenne ».

## 1. Règles absolues

1. **Architecture** : respecte le principe « tout est données ». Aucun texte narratif dans les composants. Une nouvelle appli = un `kind` dans `types.ts`, un composant dans `src/apps/<kind>/`, une entrée dans `registry.tsx`, un manifeste dans le pack.
2. **Tests** : `npm run typecheck`, `npm test` et `npm run build` doivent passer à la fin de chaque phase. `tests/pack.test.ts` doit valider le nouveau pack.
3. **Aucune trace de Sofiane Douzi** dans la version publique : ni nom, ni portrait, ni Douzi City, ni Douzi Ambrée, ni Sauce Douzi, ni jeu de mots Douzi / douze, ni cri « MWA KA KRIÉ DOUZIIII », ni volume `/douzi` au démarrage. À la fin, `grep -ri douzi src/ public/` ne doit rien renvoyer.
4. **Visages** : les photos de Porkopédia montrent de vrais collègues. **Aucune image montrant Douzi ou un personnage « refus » (voir §6) ne doit apparaître dans le jeu public.** Remplace-la par un emplacement réservé neutre (image grise « PHOTO PENDING — [nom du personnage] ») et liste-la dans `docs/IMAGES_A_PRODUIRE.md`. Les images des personnages « accord » peuvent rester.
5. **Pas de dépendance au site privé** : ne plus lier les images de `porkopedia.totoken.chatgpt.site` pour la version publique. Liste les images à rapatrier ou à produire dans `docs/IMAGES_A_PRODUIRE.md` ; utilise les emplacements réservés en attendant.
6. **Langue** : tout le jeu est en **anglais**, sauf ce qui est listé au §5. Les blagues sont **réécrites en anglais natif**, jamais traduites mot à mot. Une blague traduite meurt : si le jeu de mots ne passe pas, invente-en un autre au même endroit, au même niveau de crudité.
7. **Ton** : « délire encyclopédique impassible » (voir Canon, section Voix et humour). Humour cru assumé, adulte, jamais de caricature d'origine, jamais de mot qui annonce la blague (*weird, crazy, absurd, wacky…*).

---

## 2. Phase 1 — Mise en place

1. Crée un nouveau pack **`src/content/packs/save-him-a-plate.ts`** (le poste de Colette), en partant d'une copie du pack `porkos.ts` pour récupérer la structure, les applis, les menus, Channel Pork, le portail PigNet, etc.
2. Fais pointer `page.tsx` sur ce nouveau pack. Supprime de cette branche tout ce qui ne sert qu'à l'Édition Citoyenne française, s'il n'est plus utilisé.
3. Applique **tous les renommages** du §6 et les **règles de cohérence** du §7 dans le pack et dans les notices Porkopédia.
4. Vérifie les tests.

---

## 3. Phase 2 — Traduction de l'OS en anglais

1. Repère **toutes les chaînes françaises restantes**, y compris celles codées en dur dans les composants (BIOS, écran de chargement, connexion, menu PorkOS, barre des tâches, dialogues système, sons, économiseur, erreurs). Déplace-les dans le pack si elles n'y sont pas, puis traduis-les.
2. Garde l'humour administratif de chaque message : c'est l'âme de PorkOS. Exemple de niveau attendu :
   - « Aucune imprimante homologuée n'a été trouvée. L'imprimante nationale est occupée à imprimer le portrait du Fondateur, en 12 000 exemplaires. »
   - → *"No approved printer was found. The national printer is currently busy printing the Founder's portrait, 12,000 copies."*
3. **Channel Pork** : les voix off sont des fichiers audio en français. **Garde l'audio français et affiche des sous-titres anglais** : dans le monde du jeu, c'est la télévision d'État porkonienne vue depuis l'étranger. Traduis sous-titres, bandeaux, chyrons et télétexte.
4. **PorkAmp / Radio** : les morceaux restent tels quels (musique). Traduis l'interface et les titres affichés si ce sont des phrases ; les titres de morceaux déjà « noms propres » restent (voir §5).
5. **Époque** : le jeu se déroule en **2007**. Le poste tourne encore sous « PorkOS 98 » (l'administration n'a pas mis à jour) : c'est volontaire et c'est une blague. Horloge, dates des fichiers et des mails : 2007.

---

## 4. Phase 3 — Nouvelles applis

À ajouter en respectant l'architecture (§1.1). Tout leur contenu vient du pack.

| Appli | Rôle | Détails |
| --- | --- | --- |
| **Lardware Assist** (`lardware`) | Outil de prise en main à distance de Lardware, l'entreprise du joueur. Fil conducteur du jeu | Liste de tickets avec statut. Résoudre un ticket émet un `signal` et débloque des zones du poste. Écran de clôture de ticket avec le champ « Number of people present during the intervention » (voir fin, §8) |
| **Banquet Spreadsheet** (`tableur`) | Tableur du Bureau des Banquets Inattendus | Lecture seule au départ : feuilles par fête, colonnes Guests / Chairs / Portions served. Une ligne peut être ajoutée par une règle d'événement pendant la partie |
| **Print Queue** (`impression`) | File d'impression du poste | Travaux imprimés la nuit (plans de table). Vider la file = ticket résolu. Un travail peut apparaître via une règle |
| **Evidence Register** (`registre`) | Registre de preuves de Colette | Le joueur relie deux documents ; si la paire est prévue dans le pack, un dossier monte d'un état : *reported → corroborated → reproduced* (vocabulaire B.R.U.M.E.). Peut s'inspirer de la mécanique de `distinctions` |

Nouvelles capacités du moteur :

- Action de règle **`modify-file`** : remplace le contenu d'un fichier du pack pendant la session (le fichier affiche alors « Modified by: guest » dans ses propriétés).
- **Événements d'agenda venant du pack** dans le Calendrier (ex. rendez-vous récurrent « Dinner — Tonton — 8 pm » que Colette n'a jamais créé).
- **Dossiers verrouillés par mot de passe** trouvé dans le monde (réutilise `locked` de Mes documents, en ajoutant une vraie saisie de mot de passe si elle n'existe pas).
- **Visionneuse** : afficher aussi le **modèle d'appareil** et la date de prise de vue (façon EXIF, avec le timestamp orange sur l'image si possible).
- **PigNet** : un **cache** où l'on retrouve l'ancienne version d'une page retirée.

---

## 5. Ce qui reste en français

Règle générale : **les noms propres restent en français, tout le reste passe en anglais.**

Restent en français :
- **Noms de personnes** (voir §6), **Tonton**, **the Premier Convive**.
- **Lieux** : Porkonia, Grand-Couvert (la capitale), Hamelot, Lardombre, Brassefort, Port-Cochon, les Hauts-Monts, les Grands Coteaux, etc.
- **Plats et boissons** : la Tonton Ambrée, la Sauce du Dimanche, raclette, pâté de tête, etc. (avec une courte explication en anglais la première fois si nécessaire).
- **Monnaies** : **Pork$** (actuelle), **le Groin** (ancienne), « porko » (argot).
- **Pork ID**, **B.R.U.M.E.** (le sigle reste ; sa signification française *Bureau de Recherche sur les Usages et Manifestations Étranges* est donnée une fois, suivie d'une traduction anglaise).
- **Noms de marques porkoniennes** : Lardware, PigNet, PorkAmp, Brasswagen (Palou, Foudroy, Fourgonze), Nappe Vide (le démineur), Channel Pork, SCPB.
- Quelques mots qui font la couleur locale, en italique, sans traduction si le contexte suffit : *santé !*, *l'apéro*.

Passent en anglais (réécrits, pas traduits) :
- **Institutions** : nom anglais, avec l'original français entre parenthèses à la première mention. Ex. *the Senate of Tavernkeepers (Sénat des Taverniers)*, *the Ministry of Overly Complicated Affairs (Ministère des Affaires Trop Compliquées)*, *the Bureau of Improbable Probabilities*, *the Unexpected Banquets Office (Bureau des Banquets Inattendus)*.
- **Titres honorifiques**, dialogues, notices, mails, interface, blagues.
- **Titres des dossiers B.R.U.M.E.** : ex. 004 *The One Who Finishes Closing*, 012 *The Courtesy Place Setting*, 027 *The Platform That Calls Your Name*, 031 *The Ones in the Hallway*, 046 *We'll Let You In*, 058 *The Kitchen Under the Hillside*.
- **Expressions populaires autour de Tonton** : *"Tonton's coming."* (on ne commence pas à manger), *"Save some for Tonton."*, *"Tonton came by."* (un plat a disparu), *"Budge up for Tonton."*, *"Not in front of Tonton."*

Titulature de Tonton, à écrire directement en anglais à partir de la version de travail du Canon (section Le Fondateur). Exemples de niveau attendu : *His Awaited Presence, the Premier Convive* · *Grand Marshal of Seconds* · *Uncle to the Whole Nation, Including Those Who Already Have One* · *Lifetime Holder of the Seat by the Radiator* · *Undefeated Belote Champion, 1911* · *Doctor Honoris Causa of Head Cheese* · *The Only Citizen Allowed to Fart During the Anthem* · *He Who Said "Let's Eat"* · *Excused from All Meetings, for Life*.

---

## 6. Renommages (version publique)

### Personnages

« Accord » : nom changé, la photo peut servir de référence. « Refus » : nom **et** visage changés (aucune photo réelle, emplacement réservé). Les **histoires restent les mêmes**, seuls noms et visages changent.

| Nom de travail (Porkopédia) | Nom PorkOS | Statut |
| --- | --- | --- |
| Sofiane Douzi | **Retiré.** Remplacé par Tonton, le Premier Convive | — |
| Lulenge Walala Tonio | **David Walala** | Accord |
| Stanley Ferret | **Octave Corbin** | Accord |
| Brandon Pichoff | **Jordan Brochard** (supprimer le surnom « le Gitan ») | Accord |
| John Pork (Axel, Boule) | **John Pork** (inchangé) | Accord |
| Pierrick Nicolas | **Gildas Fumel** | Accord |
| Kenny Desaintfuscien | **Kenny de Saint-Fûts** | Accord |
| Maxime Mauriac | **Mathurin Gorlier** | Accord |
| Bilel Dren | **Samy Rouage** | Accord |
| Kevin Ranga | **Steeve Carrié** (RangaNet → **CarriéNet**) | Refus |
| François Alvarez | **Honoré Mignot** | Refus |
| Wilfrite Lelouch | **Aldric Troupel** | Refus |
| DJ Viteau | **DJ Toulemonde** (Radio DJ Viteau → **Radio Toulemonde**) | Refus |
| Edwin Valentin | **Jonas Delcourt**, alias **Lt. Salamander** et **Fatbass** | Refus |
| Martin Chou | **Anatole Dorival** | Refus |
| Mickael Jox | **Yanis Montaigu** | Refus |
| Luis Fontanillas | **Ferdinand Agathe** (gobelin) | Refus |
| Bernis Mano | **General Aymon Chaudier** ; sa femme **Isadora Chaudier** | Refus |
| Stéphane Tchimbakala Matoutou | **Placide Vautrin** | Refus |
| Eric | **Jean-Marc** | Refus |
| Charles Christian Douala Moume | **Pierre-Alexandre Dumoutier** | Refus |
| Sylvain Devilleneuve | **Roland Poidevin** | Refus |
| Benjamin Netamiaou | Nouveau nom à proposer, **sans aucun lien avec Benyamin Netanyahou** (ni nom, ni costume, ni drapeau) | Refus |
| Frédéric Legaigneur, Jean-Groin Laverdure | Inchangés (entièrement fictifs) | — |

**Important** : le nom de scène **« Fat Nigga » ne doit plus exister nulle part**. C'est **Fatbass**.

### Lieux, produits, entreprises

| Ancien | PorkOS |
| --- | --- |
| Douzi City | **Grand-Couvert** |
| Douzi Ambrée | **la Tonton Ambrée** |
| Sauce Douzi | **la Sauce du Dimanche** |
| Econopork | **Lardware** |
| Sofiane Douzi, Grand Maître | **Tonton, the Premier Convive** — il est aussi le Grand Maître ; aucun dirigeant vivant ; décrets signés « for the Premier Convive, detained » |
| Tonton Marcel (oncle de l'Édition Citoyenne) | **Gardé** comme fausse piste : un vrai oncle ordinaire qui s'appelle aussi Tonton (à confirmer avec moi) |

---

## 7. Règles de cohérence du monde (canon)

1. **Pays** : France rurale de montagne (esprit Savoie ou Jura). Neige, chalets, raclette nationale, Hauts-Monts. Supprime le folklore nordique des vieilles notices (hockey, Pork Metal, Père Groin).
2. **Époque** : présent porkonien = 2000–2008 ; le jeu = **2007**. Redate tout ce qui est postérieur à 2008 (emblème « 2025 », écoles bilingues « 2024 », commission « 2019 »…).
3. **Futur chromé** (ascenseur orbital, téléporteur, cristal quantique, Bluetooth des reliques) = **propagande de Porkonia 3000**. Le vrai futur est bricolé et tombe en panne.
4. **Monnaie** : Pork$ aujourd'hui, le Groin avant.
5. **Chambre haute** : Senate of Tavernkeepers (surnom historique : *Senate of Brewers*).
6. **Ministères** : la DG de la Mousse dépend du Ministère de la Bière ; l'Authenticité Porcine contrôle porc et bière.
7. **Sport national** : Groinball (le Football du Groin est un vieux sport régional).
8. **Gobelins** : l'État nie leur existence ; des « **network goblins** » (nom volontairement vague) câblent des choses sous terre sans qu'on sache pour qui. **Running gag dosé : une dizaine d'apparitions au maximum** dans tout le jeu, chacune choisie. Retire les gobelins-réflexes des légendes de photos (« le gobelin à droite… »). Ferdinand Agathe et le gobelin administratif restent des exceptions documentées.
9. **Emblème** : porc entier couronné, jamais un museau seul.
10. **Cloche du Dernier Banquet** et **Chope sans Fond** : les versions contradictoires sont **gardées volontairement** (ce sont des indices).
11. **Échelle de l'étrange** : le Ministry of Overly Complicated Affairs reçoit tout (help.pork), le Bureau of Improbable Probabilities (Honoré Mignot) explique le rationnel, ce qui reste part au B.R.U.M.E.
12. **B.R.U.M.E. n'a pas de notice dans le Porkopédia** du jeu : c'est un service secret, découvert en fouillant le poste. (Les dossiers déjà amorcés dans Channel Pork doivent donc être déplacés hors de la télévision publique ou devenir des bandes trouvées sur le poste.)
13. **Tonton** : aucun document, photo ou vidéo ne montre clairement son visage. On ne dit jamais qu'il est absent : il est *expected*, *detained*, *on his way*. Personne ne connaît son vrai prénom, et personne ne s'en soucie.

---

## 8. Phase 4 — Le contenu du jeu (le poste de Colette)

### Prémisse

**Porkonia, 2007.** Le joueur est un **technicien Lardware**. Ticket du jour : un poste du Bureau des Banquets Inattendus « rame », son utilisatrice n'est pas venue depuis trois semaines. Il prend la main à distance.

Le poste appartient à **Colette Marsan** (personnage fictif), qui attribue les places à table lors des fêtes officielles. Ses tableurs ont toujours **une portion servie de plus que de convives** ; on lui répond que c'est « for Tonton ». Elle a enquêté seule, contacté le Bureau of Improbable Probabilities (Honoré Mignot, qui ne trouve rien), puis reçu un mail d'une « refrigeration maintenance company » (la couverture du B.R.U.M.E.). Dans le registre de son service, elle est notée **« excused »**.

Ticket d'ouverture : *"Workstation slow. Prints by itself at night. User absent, please do not switch off."* — ce qu'il imprime la nuit : des plans de table.

### Les trois actes

| Acte | Le joueur | Il découvre | Ton |
| --- | --- | --- | --- |
| 1. The Ticket | Répare le poste (démarrage, file d'impression, disque plein, agenda qui sonne seul) | Porkonia via mails, tableurs, Porkopédia, radio, jeux. Première anomalie : la portion en trop | ~80 % comédie |
| 2. The COMPTES folder | Déverrouille le dossier privé de Colette, recoupe ses preuves | Son enquête, les mails de Mignot, le contact « refrigeration », les dossiers B.R.U.M.E. 012, 046, 004 | ~50 % |
| 3. The Seat | Remonte aux dossiers classifiés et aux notices retirées | Le Premier Convive, les décrets « detained », la note Hôte (*the Host*) ; le poste commence à réagir | ~20 % d'humour |

Glissements dans l'ordinateur (un par acte, jamais spectaculaires) :
1. Acte 1 : l'agenda contient « Dinner — Tonton — 8 pm », récurrent, que Colette n'a pas créé.
2. Acte 2 : un fichier déjà lu a changé ; propriétés : « Modified by: guest ».
3. Acte 3 : la file d'impression sort un plan de table avec le **nom de session du joueur** à la douzième place.

**Fin** : le joueur clôture le ticket dans Lardware Assist. Champ obligatoire : *"Number of people present during the intervention?"* Il est déjà rempli : **2**. Écran de fin : ***Save him a plate.***

### Règles de dosage

- Jamais de jump scare, de son fort ni de visage.
- Chaque découverte du Fond est précédée d'au moins une blague de Surface.
- Chaque indice existe à au moins deux endroits.
- Les mots de passe se trouvent dans le monde (ex. le dossier COMPTES s'ouvre avec une date trouvée dans le Porkopédia), jamais dans une énigme plaquée.

### Périmètre de la démo (à livrer en premier)

1. Bureau PorkOS, horloge 2007, compte de Colette.
2. **Lardware Assist** : 4 tickets (démarrage lent, file d'impression, disque plein, agenda qui sonne seul).
3. **State Mail** : une trentaine de mails (bureau, pots, pubs Tonton Ambrée, chaînes), dont 3 indices.
4. **Banquet Spreadsheet** : 5 fêtes, la portion en trop dans chacune.
5. **Porkopédia hors ligne** : 20 notices pour commencer, dont 1 notice retirée.
6. **Visionneuse** : 15 photos avec dates et modèles d'appareil.
7. **Radio Toulemonde** : 3 morceaux et un jingle.
8. **Dossier COMPTES** déverrouillable, qui ouvre le dossier B.R.U.M.E. 012.
9. **Fin de démo** : la file d'impression sort un plan de table avec le nom du joueur.

Écris tout ce contenu **directement en anglais**, dans le ton du Canon.

---

## 9. Phase 5 — Le Porkopédia du jeu (réduit)

Le Porkopédia du jeu est la **version officielle de l'État** : ~70 notices au lieu de 493. Une notice n'entre que si elle fait comprendre le monde, fait rire, ou cache un indice. Pour la démo, commence par 20 d'entre elles.

| Rubrique | Notices |
| --- | --- |
| The Republic (10) | Porkonia, Tonton the Premier Convive, Grand-Couvert, the Constitution of the Great Table, the Pork ID, Banquet Level VII, the Great Banquet, the Sacred Twelve, Toujours Plus, the Emblem |
| Institutions (6) | Porcine Authenticity, Overly Complicated Affairs, Bureau of Improbable Probabilities, Lardware, SCPB, Senate of Tavernkeepers |
| Figures (~24) | Les 21 personnages du §6 sous leur nom PorkOS + Frédéric Legaigneur, Jean-Groin Laverdure, Isadora Chaudier |
| Places (6) | Hamelot, Lardombre, Brassefort, Port-Cochon, the Pork Cube, the Kiosk (of a Billion Tickets) |
| History (8) | The Tableless Age, the Primordial Pot, the Treaty of the Seven Sausages, the March of the Hundred Cooks, the Hamelot Coup, the Night of the Uphill Marbles, the Night of the Gras-Fond, the Violet Double Check |
| Daily life (6) | la Tonton Ambrée, la Sauce du Dimanche, Groinball, Porcanna, Brasswagen, the Porkonian language |
| Objects & bestiary (8) | the Bottomless Tankard, the Bell of the Last Banquet, the Growing Map + 5 créatures : Cellar Wolf, Archivist Rat, Avalanche Hen, Lantern Piglet, Beer Dragon |
| **Retired notices (5)** | Phantom Taverns, the Disappearance of the Ministry, the Tunnel That Eats Files, the Village That Is Still Having Dinner, the Night the Pigs Spoke — la page existe dans l'index mais affiche seulement *"Notice withdrawn pending update."* Leur vrai contenu se trouve ailleurs sur le poste |

- Pars des notices existantes (`src/content/porkopedia/porkopedia.json` et le site d'origine) quand elles sont **vraiment écrites** ; **n'utilise jamais les « coquilles »** (notices générées dont le texte est identique d'une notice à l'autre, du type « Pour « X », les rues anciennes épousent le terrain… »).
- **Réécris** chaque notice en anglais avec les nouveaux noms et les règles du §7.
- La notice de Tonton ne donne jamais son prénom, et contient la titulature complète.

---

## 10. Livrables et méthode

- Travaille **phase par phase**. À la fin de chaque phase : tests verts, commit clair, et un court résumé de ce qui a changé et de ce qui reste.
- Tiens à jour **`docs/IMAGES_A_PRODUIRE.md`** (image, personnage, usage, statut) et **`docs/GLOSSAIRE_FR_EN.md`** (chaque terme porkonien, sa forme française, sa forme anglaise, et s'il reste en français). Un terme n'est traduit **qu'une seule façon** dans tout le jeu.
- Si une décision n'est pas couverte par ce prompt ou le Canon Maître, **demande-moi** plutôt que d'inventer.
- Ne pousse rien sur la branche `porkos`.
