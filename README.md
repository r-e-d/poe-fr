# Pillars of Eternity : Traduction française corrigée

Ce projet a pour but de corriger et d'améliorer la traduction française de Pillars of Eternity. Les fichiers sont prévus pour la version BETA 3.00.957 du jeu.

## Installation:

### Sans utiliser l'outil 'git' (recommandé)
Décompresser le fichier .zip et placer les répertoires data et data_expansion1 dans le dossier approprié :

 * Windows : [dossier_PoE]\PillarsOfEternity_Data\
 * Linux : [dossier_Poe]/PillarsOfEternity_Data/
 * OSX : [dossier_Poe]/PillarsOfEternity.app/Contents/

Ensuite dans les options du jeu, choississez la nouvelle langue :

<a href='http://pix.toile-libre.org/?img=1428774262.jpg'><img src='http://pix.toile-libre.org/upload/img/1428774262.jpg' /></a>

### En utilisant l'outil 'git'

Pour bénéficier des mises à jours de ce répertoire sans devoir en télécharger/décompresser/copier le contenu à chaque fois, il est possible de configurer git pour ne télécharger que le répertoire fr-fixed.

* Se Rendre dans le répertoire contenant les langues:

        cd chemin/vers/Program Files\ (x86)/Steam/SteamApps/common/Pillars of Eternity/PillarsOfEternity_Data/data/localized

* Initialiser un repo git à cet endroit:

        git init
        Dépôt Git vide initialisé dans /media/dv/OS/Program Files (x86)/Steam/SteamApps/common/Pillars of Eternity/PillarsOfEternity_Data/data/localized/.git/

* Ajouter l'URL d'origine du répertoire Github au repo git venant tout juste d'être initialisé:

        git remote add -f origin https://github.com/r-e-d/poe-fr.git
        Mise à jour de origin
        remote: Counting objects: 4536, done.
        remote: Compressing objects: 100% (46/46), done.
        remote: Total 4536 (delta 12), reused 0 (delta 0), pack-reused 4490
        Réception d'objets: 100% (4536/4536), 6.75 MiB | 1.82 MiB/s, done.
        Résolution des deltas: 100% (2506/2506), done.
        Depuis https://github.com/r-e-d/poe-fr
        * [nouvelle branche] master     -> origin/master

* Configurer un 'Sparse Checkout' (ce qui permet de ne télécharger qu'une portion des fichiers d'un repo, c'est à dire seul fr-fixed qui nous intéresse):

        git config core.sparseCheckout true

* Ecrire, dans le fichier de configuration des options sparse-checkout quels fichiers/dossiers sont à télécharger:

        echo "fr-fixed" >> .git/info/sparse-checkout

Note: Cette configuration n'est valable que pour le dossier git local et n'est pas une option de configuration globale, comme indiqué dans la doc de git:

        man git config

> When reading, the values are read from the system, global and repository local configuration files by default, and options --system, --global, --local and --file <filename> can be used to tell the command to read from only that location (see the section called “FILES”).

* Et enfin rapatrier le dossier en question:

        git pull origin master
        Depuis https://github.com/r-e-d/poe-fr
        * branch            master     -> FETCH_HEAD

* Fr-fixed uniquement a bien été téléchargé:

        ls
        de  en  es  fr  fr-fixed  it  pl  ru

A l'avenir, pour bénéficier des derniers changements, plus besoin de re-télécharger le zip et le décompresser, seul un git pull origin master dans le répertoire des langues suffit. :-)
