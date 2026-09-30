# GAME — Prompts images PorkOS (version publique)

> ⚠ Projet **GAME** uniquement. À faire dans le projet ChatGPT « PORKOS GAME », jamais dans une conversation du projet FUN. Préfixe toutes les images produites par `game-`.

Deux étapes, dans l'ordre :

- **Partie A** : générer les 16 portraits de référence des nouveaux visages, une image par portrait.
- **Partie B** : régénérer les images de PorkOS qui montrent les anciennes têtes, en s'appuyant sur ces portraits.

Tout est à faire dans **une seule conversation ChatGPT**, pour qu'il garde les portraits en mémoire d'une image à l'autre.

---

## PARTIE A — Les 16 portraits de référence

Colle ce message tel quel dans ChatGPT :

```
I need 16 separate character reference portraits for a fictional country called Porkonia, year 2007.
Generate them ONE BY ONE: one image per portrait, one portrait per image, never a collage or a grid.
Generate portrait 1, then immediately continue with portrait 2, and so on until portrait 16, without waiting for my confirmation between images. Before each image, write its number and the character's name.

SHARED STYLE (identical for all 16 images):
- Official Pork ID photo taken with a cheap 2007 consumer digital camera.
- Straight-on frontal view, head and shoulders, eyes looking into the lens, neutral or slight expression, centered, 4:5 vertical frame.
- Plain pale grey-blue wall background, direct on-camera flash, slight JPEG compression, mild chromatic noise, imperfect white balance, small orange digital date stamp "2007" in the lower right corner.
- Realistic human faces, documentary realism. No painting, no illustration, no cinematic lighting, no beauty retouching.
- No text other than the date stamp, no logos, no flags, no emblems.
- All 16 people must look clearly different from each other (face shape, age, hair, skin tone, build).
- These portraits will be reused as permanent face references: faces must be sharp, well lit and fully visible.

THE 16 CHARACTERS:
1. Steeve Carrié — chef turned AI engineer. Man, early 30s, round cheerful face, full cheeks, small soul patch, short dark hair under a red kitchen bandana, white chef jacket.
2. Honoré Mignot — detective of crumbs. Man, 40s, very thin angular face, bald on top with neat grey sides, sharp curious eyes, thin wire glasses, brown corduroy jacket, powdered sugar on the lapel.
3. Aldric Troupel — pig herder with strange hand gestures. Man, late 50s, weathered tanned skin, long grey hair tied in a low ponytail, deep wrinkles, calm half-smile, dark green farm work jacket.
4. DJ Toulemonde — king of zouk. Man, mid-40s, Black, round friendly face, short afro, thin moustache, huge warm smile, colourful loose short-sleeved patterned shirt, headphones around the neck.
5. Jonas Delcourt ("Fatbass" / Lt. Salamander) — submarine sonar officer and DJ. Man, late 30s, very tall and broad, shaved head, thick dark full beard, heavy-lidded relaxed eyes, navy sailor sweater with a small anchor badge.
6. Anatole Dorival — obsessive gold decorator and collector. Man, 60s, white, silver swept-back pompadour, gold-rimmed round glasses, theatrical raised eyebrow, velvet burgundy jacket with far too many gold buttons.
7. Yanis Montaigu — national Groinball champion. Man, mid-20s, North African, very tall and lean, short curly black hair with a fade, serious focused expression, amber sports jersey with the number 12.
8. Ferdinand Agathe — a real goblin, marble thief. Small goblin with realistic olive-green skin, long pointed ears, bald head with two white tufts above the ears, beady clever eyes, crooked smirk, a monocle, tiny grey waistcoat. Photographed exactly like the humans (same ID-photo style).
9. General Aymon Chaudier — cyborg general. Man, mid-50s, grey buzz cut, heavy walrus moustache, cold stare, thin scar on the chin, discreet brass-and-copper implants on the neck and one temple, burgundy military collar with plain stars.
10. Isadora Chaudier — the general's wife, "the Endless Beauty". Woman, about 40, tall, golden-brown skin, long wavy black hair, amber eyes, calm magnetic gaze, elegant ivory and burgundy clothing.
11. Placide Vautrin — telephone presence officer. Man, early 60s, balding crown, grey moustache, gentle distracted eyes, beige cardigan over a checked shirt.
12. Jean-Marc — street "startup founder", always hungry. Man, 50s, white, weathered face, ginger-grey stubble, tired but hopeful eyes, woolly beanie, old parka.
13. Pierre-Alexandre Dumoutier — unqualified licence inspector. Man, early 30s, very neat slicked side parting, pencil moustache, smug expression, overdressed in a three-piece suit with a pocket square.
14. Roland Poidevin — driver of giant beer tanker trucks. Man, late 50s, ruddy red face, bushy eyebrows, short white beard, trucker cap, high-visibility vest over a flannel shirt.
15. Hubert Rondelle — owner of an all-you-can-eat pork buffet who hates people eating. Man, 60s, heavy jowls, short grey hair, suspicious narrow eyes, dark suit, burgundy tie, a buffet serving tong clipped to the breast pocket.
16. Colette Marsan — civil servant at the Unexpected Banquets Office. Woman, mid-30s, white, chestnut hair in a loose bun with a few strands falling, clear tortoiseshell glasses, attentive tired eyes, beige blouse with a lanyard badge.
```

Si ChatGPT s'arrête en route : réponds simplement « Continue with portrait N ».

Une fois les 16 validés, **télécharge chaque portrait** et nomme-le `ref-01-steeve-carrie.jpg`, `ref-02-honore-mignot.jpg`, etc. Ce sont désormais les seules sources de visage de ces personnages.

---

## PARTIE B — Régénérer les images avec les anciennes têtes

### Méthode

Pour chaque image de la liste :

1. Télécharge l'image d'origine (lien plus bas, ou dossier du dépôt pour celles marquées « dépôt »).
2. Dans la même conversation ChatGPT, envoie **l'image d'origine + les portraits de référence des personnages concernés** (pour les personnages « accord », joins leur vraie photo de référence habituelle).
3. Colle le **message de base** ci-dessous, puis la **consigne propre à l'image**.

**Message de base** (à coller avant chaque consigne) :

```
Recreate the first attached photo as faithfully as possible: same composition, same framing, same camera angle, same setting, same lighting, same action, same 2000s consumer digital camera look (direct flash or poor available light, JPEG compression, chromatic noise, imperfect white balance, candid framing). Only change what is listed below.
Every replaced person must have EXACTLY the face of the matching reference portrait I attached (same face structure, features, hair, skin tone). Keep their pose and gestures from the original photo; clothing can follow the scene.
Remove any readable text, caption or label burned into the photo unless I give you the new text. No flags of real countries, no real brands, no invented emblems.
```

Les URLs d'origine commencent toutes par `https://porkopedia.totoken.chatgpt.site/assets/` (sauf celles marquées « dépôt », qui sont dans `public/tv/` du dépôt PorkOS).

### 1. DJ Toulemonde (ex-DJ Viteau) — 9 images

| Image | Consigne |
| --- | --- |
| dépôt `viteau/doigt.jpg` | Replace the man pointing at the camera with DJ Toulemonde (ref 4). Remove the sunglasses if they hide his face too much. |
| dépôt `viteau/plage.jpg` | Replace the man with crossed arms on the beach with DJ Toulemonde (ref 4). |
| dépôt `viteau/platines.jpg` | Replace the DJ at the turntables with DJ Toulemonde (ref 4). |
| dépôt `viteau/quai.jpg` | Replace the man on the quay with DJ Toulemonde (ref 4). |
| `dj-viteau-grand-zoukeur.jpg` | Replace the DJ at the decks in front of the dancing banquet with DJ Toulemonde (ref 4). |
| `dj-viteau-grand-zouk.jpg` | Replace the DJ leading the crowd in the beer hall with DJ Toulemonde (ref 4). |
| `dj-viteau-studio.jpg` | Replace the DJ in the brewery studio with DJ Toulemonde (ref 4). Remove the goblin sound engineer, replace him with a human sound engineer. |
| `dj-viteau-decale-quach.jpg` | Replace the dance teacher with DJ Toulemonde (ref 4). Remove the goblin; dancers stay human. |
| `douzi-archives/wilfrite-viteau.jpg` | Replace the man guiding the pigs with Aldric Troupel (ref 3) and the DJ with DJ Toulemonde (ref 4). |

### 2. Yanis Montaigu (ex-Mickael Jox) — 6 images

| Image | Consigne |
| --- | --- |
| `mickael-jox-jox-celeste.png` | Replace the player performing the jump near the hoop with Yanis Montaigu (ref 7). |
| `mickael-jox-finale.png` | Replace the star player crossing the green defence with Yanis Montaigu (ref 7). |
| `mickael-jox-entrainement.png` | Replace the player training in the mountain inn with Yanis Montaigu (ref 7). |
| `mickael-jox-trophee.png` | Replace the player holding the golden trophy with Yanis Montaigu (ref 7). |
| `home-archives/home-mountain.jpg` | Replace the athlete moving the trophy with Yanis Montaigu (ref 7). Keep John Pork (attach his usual reference photo). |
| `douzi-archives/jox-john.jpg` | Same as above: the athlete becomes Yanis Montaigu (ref 7), John Pork stays (his usual reference). |

### 3. Ferdinand Agathe (ex-Luis Fontanillas) — 5 images

| Image | Consigne |
| --- | --- |
| `luis-fontanillas-billomancien.png` | Replace the goblin surrounded by drawers of marbles with Ferdinand Agathe (ref 8). |
| `luis-fontanillas-barrage.png` | Replace the goblin filling the brewery valve with marbles with Ferdinand Agathe (ref 8). |
| `luis-fontanillas-contre-pente.png` | Replace the goblin chasing the marbles up the street with Ferdinand Agathe (ref 8). |
| `douzi-archives/martin-luis.jpg` | Replace the man gilding the terminal with Anatole Dorival (ref 6) and the goblin with Ferdinand Agathe (ref 8). |
| `douzi-archives/douzi-luis.jpg` | Replace the bearded official listening (Douzi) with a generic middle-aged female civil servant with grey hair and reading glasses (new anonymous person, no reference). Replace the goblin with Ferdinand Agathe (ref 8). |

### 4. Steeve Carrié et Anatole Dorival (ex-Kevin Ranga, ex-Martin Chou) — 4 images

| Image | Consigne |
| --- | --- |
| `home-archives/home-network.jpg` | Replace the cook stirring the curry with Steeve Carrié (ref 1) and the huge man holding the hatch with Mathurin Gorlier (keep Maxime's usual reference photo). Keep Kenny (his usual reference). |
| `douzi-archives/kevin-kenny-maxime.jpg` | Same three people: the cook becomes Steeve Carrié (ref 1); Kenny and Mathurin keep their usual reference photos. |
| dépôt `ftg/candidats.jpg` | Game show: four contestants behind buzzers. Keep contestant 1 (Frédéric, pink polo) and contestant 4 (David, cream shirt, his usual reference). Replace contestant 2 with Steeve Carrié (ref 1, grey blazer over black shirt) and contestant 3 with Anatole Dorival (ref 6, white shirt). New name plates, in this order: FRÉDÉRIC, STEEVE, ANATOLE, DAVID. Keep the scores on the small screens. |
| dépôt `ftg/plateau.jpg` | Wide shot of the same set: the four contestants must match the new `candidats.jpg` (same four people, same clothes). |

### 5. Général Chaudier, Jonas Delcourt, Honoré Mignot — 3 images

| Image | Consigne |
| --- | --- |
| `douzi-archives/edwin-bernis.jpg` | Replace the man inspecting the pork cargo at the port with Jonas Delcourt (ref 5) and the armoured general with General Aymon Chaudier (ref 9). Keep the armour, only the face and head change. |
| `douzi-archives/bernis-reserves.jpg` | Replace the armoured general with General Aymon Chaudier (ref 9). Replace the bearded civilian he argues with (Douzi) with a generic 50-year-old male minister in a grey suit (new anonymous person). |
| `douzi-archives/alvarez-pierrick.jpg` | Replace the long-haired man comparing curry-stained receipts with Honoré Mignot (ref 2). Keep the man with the cable (Gildas, his usual reference). |

### 6. Images de Sofiane Douzi (il ne doit plus apparaître)

Règle absolue : **Tonton, le Premier Convive, ne montre jamais son visage.** Quand la scène le représente, son visage doit être caché, coupé, flou ou masqué, et ça doit avoir l'air accidentel.

| Image | Consigne |
| --- | --- |
| `unique-archive-iii-le-fondateur-sofiane-douzi.jpg` | Ribbon-cutting ceremony in fur robes. The man cutting the ribbon is now Tonton, the Premier Convive: same robe, same pose, but his face is completely hidden by a spectator's raised compact camera in the foreground, as if the photographer was unlucky. Nothing of his face is visible. |
| `douzi-archives/fondation-table.jpg` | The founding banquet. Remove the bearded young man in the foreground. Instead, at the head of the table, a man seen only from behind (Tonton): broad shoulders, dark coat, no face visible. Everyone else keeps looking toward him. |
| `home-archives/home-banquet.jpg` | The man holding up the table leg (Douzi) is replaced by a man crouched under the tablecloth: only his hands and shoes are visible, never his face. Keep David (his usual reference) checking the dishes and Jordan (his usual reference) bringing the table extension. |
| `douzi-archives/onze-centimetres.jpg` | Replace the man measuring the strip of empty tablecloth (Douzi) with a thin commission official in a grey suit holding a ruler (new anonymous person). |
| `douzi-archives/nuit-louche-vide.jpg` | Replace the man studying the delivery map (Douzi) with a stressed female transport official in a hi-vis vest (new anonymous person). |
| dépôt `viteau/chope.jpg` | Replace the young bearded man holding the beer with a different anonymous reveller (older man, moustache, flat cap). |
| dépôt `douzi-ambree-inspecteur.jpg` | Replace the young bearded man inspecting the beer glass with a stern, elderly female beer inspector with short white hair and a lab coat (new anonymous person). |
| `pork-id.png` et `article-pork-id.jpg` | Redraw this Pork ID card as the card of Colette Marsan (ref 16), same layout. Text: surname MARSAN, given name COLETTE, nationality PORKONIAN, date of birth 14 MAR 1972, place of birth HAMELOT, occupation AGENT — UNEXPECTED BANQUETS OFFICE, issued 03 SEP 2005, expires 03 SEP 2015, banquet level VI, signature "C. Marsan". Remove the red flag with the maple leaf entirely. Leave a blank area where the official Porkonia emblem will be added afterwards. |

### 7. Rebranding de la bière et de la sauce (pas de visage)

| Image | Consigne |
| --- | --- |
| dépôt `douzi-ambree-bouteille.jpg` | Change the bottle label text from "Douzi Ambrée" to "Tonton Ambrée", same label design and colours. |
| dépôt `douzi-ambree-tirage.jpg` | Change every "Douzi" on the bottle and the crates to "Tonton". |
| `article-auto-la-douzi-ambree.jpg` | Remove the burned-in caption at the bottom. |
| `article-auto-la-sauce-douzi.jpg` | Remove the burned-in caption at the bottom. |
| `article-auto-archive-v-la-pork-id.jpg` | Remove the burned-in caption at the bottom. |

Les fichiers `douzi-ambree-*.jpg` du dépôt seront ensuite renommés `tonton-ambree-*.jpg` par Claude Code.

---

## À la fin

- Remplace les images dans le dépôt (ou donne-les à Claude Code) avec leur nouveau nom, et coche-les dans `docs/IMAGES_A_PRODUIRE.md`.
- Les images qui ne montrent que des personnages « accord » (Octave Corbin / Stanley, David Walala / Tonio, Jordan Brochard / Brandon, Kenny, John Pork…) n'ont pas besoin d'être refaites : seuls leurs noms changent.
- Les nouvelles notices du Porkopédia réduit auront besoin d'images supplémentaires (Placide Vautrin, Jean-Marc, Dumoutier, Poidevin, Isadora, Rondelle, Colette…) : elles seront générées plus tard, à partir des mêmes portraits de référence.
