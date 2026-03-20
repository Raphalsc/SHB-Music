# SHB Music

**SHB Music** est un petit lecteur de musique Windows orienté usage simple :
- lecture locale de fichiers `.mp3`
- playlists par dossiers
- lecture aléatoire pondérée par note
- historique de session
- statistiques par playlist
- recherche / lecture / téléchargement YouTube
- interface simple pour utilisateurs non techniques

## Version actuelle

**v1.0.0** — Initial Release

---

## À quoi sert SHB Music ?

L’idée est simple :

- tu mets tes musiques dans des dossiers
- chaque dossier devient une playlist
- tu peux noter tes morceaux sur 10
- l’application choisit plus souvent les morceaux mieux notés
- tu peux aussi rechercher des musiques sur YouTube, les écouter et les télécharger directement dans ta playlist actuelle

---

## Fonctionnalités principales

- Lecture de musiques locales au format `.mp3`
- Playlists automatiques à partir de sous-dossiers
- Lecture aléatoire pondérée par les notes
- Système de note sur 10
- Historique des morceaux joués pendant la session
- Fenêtre de statistiques pour la playlist actuelle
- Renommage du **titre affiché** dans l’application
- Recherche YouTube intégrée
- Lecture YouTube directe
- Téléchargement d’une musique YouTube vers la playlist actuelle
- Mode **Suggestions YouTube**
- Bouton **Aide** intégré dans l’application
- Bouton **Reset stats** pour remettre à zéro les notes/écoutes d’une playlist

---

## Plateforme

Actuellement, cette version est pensée pour **Windows**.

---

## Installation

Aucune installation compliquée.

1. Télécharge `SHB Music.exe`
2. Place-le où tu veux sur ton PC
3. Lance-le

Au premier lancement, l’application crée automatiquement son dossier de données à côté du `.exe`.

---

## Structure créée automatiquement

Au premier démarrage, l’application crée un dossier du type :

```text
SHB Music.exe
SHB Music Data/
├── music/
├── tools/
├── _youtube_cache/
├── ratings.json
└── settings.json
```

### Détail

- `music/` : contient toutes tes playlists
- `tools/` : contient les outils utilisés par l’application
- `_youtube_cache/` : cache temporaire pour la lecture YouTube
- `ratings.json` : notes, écoutes et noms affichés
- `settings.json` : paramètres de l’application

---

## Comment ajouter ses musiques

Toutes les playlists sont gérées via des **dossiers**.

Chaque sous-dossier dans `SHB Music Data/music/` devient automatiquement une playlist.

### Exemple

```text
SHB Music Data/
└── music/
    ├── Ma playlist/
    │   ├── morceau1.mp3
    │   └── morceau2.mp3
    ├── Metal/
    │   ├── song_a.mp3
    │   └── song_b.mp3
    └── Classique/
        └── track.mp3
```

Dans cet exemple :
- `Ma playlist` est une playlist
- `Metal` est une playlist
- `Classique` est une playlist

---

## Format supporté

Actuellement, les musiques locales doivent être au format :

- `.mp3`

---

## Utilisation rapide

### Ajouter des musiques

1. Lance l’application
2. Clique sur **Aide**
3. Clique sur **Ouvrir dossier des playlists**
4. Ouvre `Ma playlist` ou crée un nouveau dossier
5. Glisse-dépose tes fichiers `.mp3`
6. Reviens dans l’application

### Choisir une playlist

- Clique sur **Choisir playlist**
- Sélectionne un dossier / une playlist

### Choisir un morceau précis

- Clique sur **Choisir musique**
- Recherche un titre
- Double-clique ou joue la sélection

### Lecture aléatoire pondérée

Chaque morceau a une note sur 10.

Plus la note est élevée, plus il a de chances d’être rejoué.

Exemple :
- un morceau noté `10` sortira beaucoup plus souvent qu’un morceau noté `1`

---

## Notes et aléatoire

Le mode aléatoire n’est pas un simple shuffle uniforme.

Il prend en compte :
- la note du morceau
- un système pour éviter de rejouer trop vite les mêmes morceaux récents

Donc :
- les musiques mieux notées sortent davantage
- mais l’application essaie aussi d’éviter les répétitions immédiates

---

## Renommer un morceau

Le bouton **Renommer** ne change **pas** le nom réel du fichier sur ton disque.

Il change uniquement le **nom affiché dans l’application**.

Exemple :
- fichier réel : `Coldplay - Viva La Vida [abc123].mp3`
- nom affiché dans SHB Music : `Viva La Vida`

---

## Historique

Le bouton **Historique** affiche les morceaux joués pendant la session en cours.

Tu peux :
- voir ce qui a été joué
- rejouer un morceau depuis l’historique

---

## Statistiques

Le bouton **Stats** affiche les statistiques de la playlist actuelle :

- nombre de titres
- nombre total d’écoutes
- note moyenne
- détail morceau par morceau

Tu peux aussi :
- jouer la sélection
- renommer la sélection
- utiliser **Reset stats**

### Reset stats

Le bouton **Reset stats** remet à zéro, pour la playlist actuelle :
- toutes les notes à `5.0`
- toutes les écoutes à `0`

Les fichiers `.mp3` ne sont **pas supprimés**.

---

## Fonctionnalités YouTube

Le bouton **YouTube** permet de :

- rechercher une musique
- la lire
- la télécharger dans la playlist actuelle

### Deux modes de lecture automatique

#### 1) Suite de la recherche
L’application lit les résultats de la recherche à la suite.

#### 2) Suggestions YouTube
L’application utilise les suggestions associées à la musique en cours.

Cela permet de découvrir des morceaux proches automatiquement.

### Télécharger la musique en cours

Quand une musique YouTube est en train d’être lue, le bouton **Télécharger** sur l’écran principal permet de l’ajouter directement à la playlist actuelle.

---

## Playlist par défaut

L’application crée une playlist par défaut nommée :

- `Ma playlist`

Elle peut aussi inclure des morceaux d’exemple pour éviter d’avoir une application vide au premier lancement.

---

## Données conservées

L’application conserve localement :
- tes playlists
- tes notes
- tes statistiques d’écoute
- tes noms affichés
- quelques paramètres comme le volume et le mode YouTube

Ces données sont stockées dans :
- `ratings.json`
- `settings.json`

---

## Vie privée / code source

Le code source n’est pas publié pour le moment.

Cette release est distribuée sous forme de **binaire `.exe` uniquement**.

L’application est pensée comme un outil personnel/simple à utiliser, sans installation compliquée.

---

## Limitations connues

- version principalement pensée pour **Windows**
- format local actuel : **.mp3**
- les stats/historique sont simples et orientées usage personnel
- l’historique affiché concerne surtout la session en cours
- le code source n’est pas inclus dans cette release

---

## Conseils d’utilisation

- garde ton `.exe` dans un dossier fixe
- organise tes playlists avec des sous-dossiers clairs
- utilise les notes pour orienter l’aléatoire
- utilise **Suggestions YouTube** pour découvrir facilement de nouveaux morceaux proches de ton style
- utilise **Reset stats** si tu veux repartir de zéro sur une playlist

---

## FAQ

### L’application ne voit pas mes musiques
Vérifie que :
- elles sont bien dans `SHB Music Data/music/`
- elles sont dans un sous-dossier
- elles sont bien au format `.mp3`

### Où dois-je mettre le `.exe` ?
Où tu veux.  
L’application créera son dossier de données à côté.

### Est-ce que renommer change le vrai fichier ?
Non.  
Ça change uniquement le nom affiché dans SHB Music.

### Est-ce que mes fichiers mp3 sont modifiés ?
Non, sauf si tu télécharges une musique YouTube dans une playlist : dans ce cas un nouveau fichier est ajouté.

### Est-ce qu’il faut créer les playlists à la main ?
Pas dans l’application.  
Il suffit de créer un sous-dossier dans `music/`.

---

## Merci

Merci d’avoir testé SHB Music.

Si tu veux faire un retour :
- bug
- idée d’amélioration
- suggestion d’interface
- comportement étrange

n’hésite pas à le signaler dans le post/release.
