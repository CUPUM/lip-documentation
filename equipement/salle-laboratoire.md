# Utilisation de la salle laboratoire (unité ACE)

## Composantes

Les éléments du système audiovisuel installé dans le local 4133 se divisent en trois catégories principales, à savoir&nbsp;:

<div class="letter-list" markdown="1">

1. [Les sources]();

2. [Les appareils de diffusion]();

3. [La matrice de gestion]().

</div>

### *a.* Les sources (*inputs*)

Le système comporte 4 sources principales, soit&nbsp;:

1. #### L'ordinateur du podium

   L'ordinateur se décline ici en fait en 2 sources, chacune indiquée sur l’interface murale&nbsp;:

   - La source `PC`, qui correspond à l’écran principal.

   - La source `PC 2`, qui correspond à l’écran secondaire. Cet écran peut fonctionner comme miroir de l’écran principal ou comme prolongation du bureau, selon la configuration établie dans les paramètres de **Windows**.

2. #### Le CYNAP

   Pour plus d'information, référez-vous à la [section spécifique à ce système](../equipement/cynap.md)

3. #### Les caméras vidéo de la salle (*webcams*)

4. #### Les micros

### *b.* Les appareils de diffusion (*outputs*)

Cette catégorie comprend les appareils d’affichage visuel et audio, c’est-à-dire les 3 moniteurs à l’avant de la salle, et le système de son.

#### Le moniteur central

Ce moniteur 4K offre une fonctionnalité multi-touche.

!> Notez cependant que son branchement actuel est tel que le signal d’interaction tactile est envoyé uniquement à l’ordinateur. Ainsi, si jamais il est souhaité d'utiliser la fonctionnalité multi-touche sur le CYNAP, il faudra brancher le câble USB de l'écran au CYNAP pour y envoyer le signal des interactions.

#### Les moniteurs latéraux (gauche et droit)

#### Les haut-parleurs de plafond

### *c.* La matrice de gestion

La matrice de gestion permet de décider quelle source assigner à l'un ou l’autre des appareils de diffusion. L’interface utilisateur pour l’opérer se retrouve sur le petit écran mural adjacent au podium. La gestion des appareils avec cette interface permet aussi de désigner les sources (canaux entrants) de l’ordinateur et du CYNAP.

![(écran mural de la matrice)](assets/lip-ecran-mural.svg ':class=figure-large')

## Configuration de base proposée

En vue de conduire une séance de consultation, d’idéation, ou de révision de contenu multimédia, nous proposons l’organisation suivante des écrans d’affichage et des sources&nbsp;:

![(configuration ACE)](assets/unite-ace.svg ':class=figure-xlarge')

En principe, l’ordinateur devrait déjà être configuré en mode double-écran. **Si ce n’est pas le cas** et qu’il est prévu d’utiliser l’étendue de deux écrans, il faut d'abord établir les paramètres d’affichage nécessaires dans **Windows**&nbsp;:

1. Faites un clic droit sur le bureau puis sélectionnez `Paramètres d’affichage`

2. Dans le menu déroulant intitulé `Affichages multiples`, choisissez l’option `Étendre ces affichages`

À l’aide de l’interface murale de gestion de la matrice, assignez les sources aux moniteurs tels que&nbsp;:

- le **moniteur central** servira à afficher et interagir avec le **contenu principal** (i.e.&nbsp;: avec l’outil de visualisation approprié)

- le **moniteur du côté droit** servira pour l’**affichage secondaire** de contenu multimédia ou pour la visio-conférence

## Enregistrer un séance

Advenant le cas où il est souhaité d’enregistrer les événements qui se déroulent dans la salle et sur l'ordinateur, il est prévu d’utiliser l’écran restant pour y diffuser et y capturer l’activité. Pour ce faire, nous profiterons de la fonctionnalité de *capture d’écran* offerte par **CYNAP**.

![(configuration d'enregistrement CYNAP)](assets/unite-ace-cynap.svg ':class=figure-xlarge')

Cette portion nécessite d’abord de configurer les **2 sources** du CYNAP pour qu’elles correspondent à l’**écran d’ordinateur principal** et à une **caméra au choix**&nbsp;:

1. Sur l’écran mural de gestion de la matrice, sélectionner `Sources CYNAP` dans la colonne de gauche et faire le choix des sources.

   ?> Le CYNAP accepte un maximum de deux sources; il faut alors choisir entre une caméra de la salle ou l’écran secondaire de l’ordinateur pour la seconde source.

2. Des fenêtres devraient s’ouvrir automatiquement dans CYNAP pour afficher les sources sélectionnées. Si ce n’est pas le cas, il est possible de les ouvrir manuellement en spécifiant quelles sources présenter&nbsp;:
   - À l’aide du bouton ![(bouton menu)](assets/cynap-more.svg ':class=inline-icon'), ouvrir le menu de navigation et sélectionner les sources `HDMI 1` et `HDMI 2`.

3. Une fois que les flux vidéo des deux sources sont disposés dans leurs fenêtres respectives, utilisez la fonction de capture d’écran pour en faire l’enregistrement&nbsp;:

   <div class="roman-list">

   1. Appuyez sur le bouton de la manette ayant pour icône ![(trois points)](assets/cynap-settings.svg ':class=inline-icon')

   2. Sélectionnez l’option `Start recording`;

   3. Lorsque demandé, remplissez le nom à donner au fichier d’enregistrement. La capture d’écran démarrera ensuite automatiquement.

   4. Pour mettre fin à l’enregistrement, retournez dans le menu d’options ![(trois points)](assets/cynap-settings.svg ':class=inline-icon') et sélectionnez `Stop recording`.

   </div>

### Récupérer des fichiers d’enregistrement

!> Le fonctionnement standard de CYNAP enregistre les fichiers dans la mémoire interne de la machine&nbsp;: il est donc important de les récupérer avant de fermer la session sans quoi ils seront perdus.

En utilisant une clé USB&nbsp;:

1. Branchez la clé dans le connecteur à l’avant de l’appareil

2. Après que l’indication «&nbsp;*USB stick added*&nbsp;» soit apparue temporairement à l’écran, appuyez sur le bouton ![(bouton menu)](assets/cynap-more.svg ':class=inline-icon') sur la manette (ou à l'écran si le multi-touche est branché au CYNAP)

3. Sélectionnez l’option `Files` et naviguez à l’emplacement des fichiers enregistrés, soit&nbsp;:  
`Files` > `System` > `Recordings`

4. Sélectionnez-y le(s) fichier(s) concerné(s) puis choisissez l’option `more…` dans la partie droite de la fenêtre

5. Cliquez sur l’option de transfert vers la clé USB
