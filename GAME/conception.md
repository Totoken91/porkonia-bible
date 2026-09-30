# PorkOS — Conception

*Statut : proposition, à valider.*

## Pitch

**Porkonia, 2007. Tu es technicien chez Lardware. Ton ticket du jour : un poste de l'administration qui « rame », dont l'utilisatrice ne s'est pas présentée depuis trois semaines.** Tu prends la main à distance sur sa machine PorkOS. Tu découvres un pays absurde, gras et chaleureux : ses mails de bureau, ses tableurs de banquets, son Porkopédia, sa radio. Puis ses comptes qui ne tombent jamais juste, un dossier caché, un service secret qui n'existe pas. Et une question que personne à Porkonia ne se pose : pour qui garde-t-on toujours une place ?

*Save Him a Plate.*

## Le joueur et l'ordinateur

**Le joueur est un technicien de Lardware.** C'est le cadre le plus naturel pour fouiller un ordinateur : on a un ticket, un accès à distance et une raison légitime d'ouvrir des dossiers. Le jeu parle aussi le langage du support informatique, que tu connais par cœur, ce qui donne une vraie crédibilité aux gags (« avez-vous essayé de redémarrer ? »).

**Le poste appartient à une agente du Bureau des Banquets Inattendus**, le service qui attribue les places à table lors des fêtes officielles. Nom de travail : **Colette Marsan**, personnage entièrement fictif.

- **Son métier** : compter les convives, les chaises, les portions. Un travail banal, drôle, très porkonien.
- **Son déclic** : ses tableurs ne tombent jamais juste. Il y a toujours une portion servie de plus que de convives. Tout le monde lui répond que c'est « pour Tonton ».
- **Sa descente** : elle enquête seule, puis contacte le Bureau des Probabilités Improbables (Honoré Mignot, qui ne trouve rien de rationnel), puis reçoit un mail d'une « entreprise d'entretien frigorifique » : la couverture du B.R.U.M.E.
- **Son absence** : dans le registre du service, elle est notée **« excusée »**.

**Le ticket Lardware d'ouverture** : « Poste lent. Imprime seul la nuit. Utilisatrice absente, merci de ne pas éteindre. » Ce que le poste imprime la nuit : des plans de table.

## Structure en trois actes

**Le jeu glisse de la comédie vers l'horreur sans jamais changer de ton.** Le premier acte est presque entièrement drôle ; le troisième reste administratif, mais la blague n'arrive plus.

| Acte | Ce que fait le joueur | Ce qu'il découvre | Ton |
| --- | --- | --- | --- |
| **1. Le ticket** | Répare le poste : nettoie le démarrage, vide la file d'impression, fouille pour comprendre pourquoi ça rame | Porkonia : mails de bureau, tableurs de banquets, Porkopédia hors ligne, Radio Toulemonde, jeux installés. Première anomalie : une portion de trop dans chaque tableur | Comédie, environ 80 % |
| **2. Le dossier COMPTES** | Trouve et déverrouille le dossier privé de Colette, recoupe ses preuves | Son enquête, les mails du Bureau des Probabilités Improbables, le contact « frigorifique », les premiers dossiers du B.R.U.M.E. (012, 046, 004) | Malaise, environ 50 % |
| **3. La place** | Remonte jusqu'aux dossiers classifiés et aux notices retirées | Le Premier Convive : décrets « pour le Premier Convive, retenu », portraits sans visage, la note Hôte. Le poste lui-même commence à réagir | Horreur calme, environ 20 % d'humour |

**Glissement vers le Fond, dans l'ordinateur lui-même** (un par acte, jamais spectaculaire) :

1. Acte 1 : l'agenda de Colette contient un rendez-vous récurrent « Dîner — Tonton — 20 h » qu'elle n'a pas créé.
2. Acte 2 : un fichier déjà lu a changé quand le joueur le rouvre. L'historique indique « modifié par : invité ».
3. Acte 3 : la file d'impression sort un plan de table où figure le nom de session du joueur, à la place douzième.

**Fin proposée** : le joueur clôture le ticket. Le logiciel Lardware demande, comme toujours, « Nombre de personnes présentes lors de l'intervention ? ». Le champ est déjà rempli : **2**. Écran de fin : *Save him a plate.*

## Mécaniques de jeu

**Tout se joue avec les gestes normaux d'un ordinateur : ouvrir, lire, chercher, recouper.** Aucune interface de jeu visible, pas de barre d'XP, pas de tutoriel qui parle au joueur. Seul l'outil Lardware sert de fil conducteur.

| Mécanique | Comment ça marche | Exemple |
| --- | --- | --- |
| **Les tickets Lardware** | L'outil de support liste des tâches techniques. Les résoudre ouvre de nouvelles zones du poste | « Vider la file d'impression » révèle les plans de table imprimés la nuit |
| **Mots de passe du monde** | Les codes se trouvent dans le monde lui-même, jamais dans une énigme plaquée | Le dossier COMPTES s'ouvre avec la date du Grand Banquet, trouvée dans le Porkopédia |
| **Recoupement** | Deux sources officielles se contredisent : la contradiction est l'indice | La Cloche du Dernier Banquet a trois descriptions incompatibles, et Colette a noté laquelle est vraie |
| **Registre de preuves** | Le joueur reprend le tableau de Colette. Relier deux documents fait monter un dossier : signalé, corroboré, reproduit | Relier l'agenda « Dîner — Tonton » et un décret « pour le Premier Convive, retenu » |
| **Données de photos** | Chaque photo garde sa date d'appareil (le timestamp orange) et son modèle. Les dates mentent parfois | Une photo de banquet de 2003 prise par un appareil sorti en 2006 |
| **Fichiers qui changent** | Certains fichiers déjà lus sont modifiés au retour. Rare, jamais annoncé | Un tableur gagne une ligne pendant que le joueur lit un mail |
| **Notices retirées** | Pages vides du Porkopédia ; leur vrai texte se trouve dans le cache du navigateur ou dans les archives de Colette | « Le Village qui Dîne Encore » retrouvée en cache |

**Règles de dosage**

- Jamais de jump scare, jamais de son fort, jamais de visage.
- Chaque découverte du Fond est précédée d'au moins une blague de Surface.
- Le joueur doit pouvoir tout comprendre sans aide. Un indice existe toujours en au moins deux endroits.

## Contenu de l'ordinateur

**PorkOS est le système d'exploitation officiel de l'administration porkonienne, version 2007.** Chaque application a un rôle dans l'humour et un rôle dans l'enquête.

| Application | En Surface | Dans l'enquête |
| --- | --- | --- |
| **Lardware Assistance** (outil de prise en main) | Tickets, jargon de support, formulaires absurdes | Fil conducteur, et l'écran de fin |
| **Groinmail** (messagerie) | Mails de service, chaînes de bureau, invitations au pot de départ, pubs pour la Tonton Ambrée | Les échanges de Colette avec Honoré Mignot, puis avec « l'entretien frigorifique » |
| **Tableur des Banquets** | Plans de table, portions, conflits de chaises | La portion en trop, colonne par colonne |
| **Porkopédia hors ligne** (les \~70 notices) | L'encyclopédie officielle, drôle | Version officielle à contredire ; notices retirées |
| **Navigateur PigNet** | Sites en .pork : help.pork, la SCPB, Brasswagen, Pork Crédit | Le cache garde les versions supprimées de certaines pages |
| **Visionneuse photo** | Photos de pots, de banquets, de la famille de Colette | Dates d'appareil, reflets, visages flous ; le Premier Convive jamais net |
| **Lecteur audio et vidéo** | Radio Toulemonde, disques de porc, clips | Répondeur du B.R.U.M.E., cassette du dossier 031 |
| **Agenda** | Réunions, anniversaires, pots | « Dîner — Tonton — 20 h », récurrent |
| **Corbeille** | Brouillons de mails gênants | Lettre de démission jamais envoyée, premiers soupçons |
| **File d'impression** | Bourrages, tickets de caisse | Plans de table imprimés la nuit |
| **Mes documents / COMPTES** (verrouillé) | — | L'enquête complète de Colette et son registre de preuves |
| **Jeux installés** | Démineur porkonien, Belote | Le score record de la Belote date de 1911 : « Premier Convive » |

## Démo jouable

**Première version : l'acte 1 complet et l'ouverture de l'acte 2, environ une heure de jeu dans le navigateur.** Assez pour tester le ton et le déclic, sans construire tout le Fond.

1. **Bureau PorkOS** avec fenêtres, icônes, horloge 2007, son de démarrage.
2. **Lardware Assistance** avec 4 tickets (démarrage lent, file d'impression, disque plein, agenda qui sonne seul).
3. **Groinmail** : une trentaine de mails, dont 3 indices.
4. **Tableur des Banquets** : 5 fêtes, la portion en trop dans chacune.
5. **Porkopédia hors ligne** : 20 notices d'abord, dont 1 notice retirée.
6. **Visionneuse** : 15 photos avec dates d'appareil.
7. **Radio Toulemonde** : 3 morceaux et un jingle.
8. **Dossier COMPTES** déverrouillable, qui ouvre le dossier 012 du B.R.U.M.E.
9. **Fin de démo** : la file d'impression sort un plan de table avec le nom du joueur.

**Technique : PorkOS existe déjà.** L'édition actuelle (branche `porkos`, en ligne sur porkos.vercel.app) est un OS complet piloté par des **packs de contenu** : tout le texte, les fichiers, les mails et les événements vivent dans un fichier de données, sans toucher aux composants. Son architecture prévoit déjà « l'ordinateur fouillé du futur spin-off d'enquête » comme un nouveau pack. Le jeu public = **un nouveau pack, le poste de Colette**, qui réutilise les applis existantes.

**Époque** : le poste administratif tourne encore sous « PorkOS 98 » en 2007. C'est crédible pour une administration, et c'est une blague de plus.

| Besoin du jeu | Appli existante | À faire |
| --- | --- | --- |
| Messagerie | Courrier d'État | Contenu seulement |
| Fichiers, dossier COMPTES verrouillé | Mes documents (dossiers `locked`, fichiers cachés) | Contenu seulement |
| Photos avec dates | Visionneuse (champ `date`) | Contenu ; afficher le modèle d'appareil si besoin |
| Porkopédia hors ligne, cache des notices retirées | PigNet Navigateur | Contenu : les \~70 notices publiques |
| Radio, répondeur, cassette 031 | PorkAmp, Channel Pork | Contenu (dossiers B.R.U.M.E. déjà amorcés) |
| Agenda « Dîner — Tonton » | Calendrier | Ajouter des événements venant du pack |
| Registre de preuves | Mes décorations (mécanique de déblocage) | Nouvelle appli ou déclinaison |
| **Lardware Assistance** (tickets) | — | **Nouvelle appli** |
| **Tableur des Banquets** | — | **Nouvelle appli** |
| **File d'impression** | — | **Nouvelle appli** ou fenêtre système |
| Fichiers qui changent | Règles d'événements (`rules`) | Nouvelle action « modifier un fichier » |

L'Édition Citoyenne actuelle reste le projet perso (Porkonia Canal Historique), avec Douzi.

## Décisions à prendre

- [ ] Le joueur est-il bien un technicien Lardware ?
- [ ] Le poste appartient-il bien à Colette Marsan, agente du Bureau des Banquets Inattendus (nom à valider) ?
- [ ] La fin proposée (« Nombre de personnes présentes : 2 ») convient-elle ?
- [ ] Langue : tout en anglais sur la branche publique, sauf noms propres et couleur locale (décidé le 30 sept. 2026) ; Channel Pork garde ses voix françaises avec sous-titres anglais
- [ ] « Tonton Marcel » (l'oncle qui écrit dans l'Édition Citoyenne) : le renommer dans le jeu public, ou le garder comme fausse piste face à Tonton le Premier Convive ?
- [x] Direction visuelle : PorkOS 98 existant, conservé
