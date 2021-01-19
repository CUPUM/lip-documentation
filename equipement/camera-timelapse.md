# Caméra longue durée (*timelapse*) Afidus ATL-200

## Contrôle et configuration de la caméra

!> Comme les interactions pour contrôler la caméra Afidus se font principalement à travers une application, l’accès à un appareil portable – de type **iOS** ou **Android** – est ici **nécessaire**. L’application en question s’intitule `Time-Lapse Afidus` et peut être récupérée sur le App Store ou le Google Play Store.

### Connexion à la caméra

Pour mettre la caméra en marche, il suffit de maintenir enfoncé le bouton qui se situe sur le dessus du boitier jusqu’à ce que l’indicateur DEL vert s’allume. Le délai nécessaire est d’environ 3 secondes. Une fois démarrée, la caméra établira automatiquement son propre réseau Wi-Fi, réseau auquel il faut se connecter pour modifier la configuration des paramètres et/ou partir un enregistrement.

![(bouton démarrage)](/assets/afidus-power.svg ':class=figure')

Pour se connecter&nbsp;:

1. Trouvez le réseau `Wi-Fi` portant le nom `ATL200_[Suite de chiffres]`

2. Le `mot de passe` pour s'y connecter (valable pour les deux caméras) est `Paysage1` (assurez-vous d'utiliser un **P** majuscule).

### Configuration

#### Paramètres principaux

Après s’être connecté au réseau `Wi-Fi` de la caméra, nous pouvons lancer l'application `Time-Lapse Afidus` sur le téléphone intelligent ou la tablette utilisée. Cette application donne accès aux différents paramètres qui peuvent être ajustés dans le but d'obtenir la capture désirée&nbsp;:

| Paramètre | Description |
| --- | --- |
| `FPS` | Vitesse de défilement des images lors de la lecture du fichier vidéo qui sera assemblé et créé automatiquement à la fin de la période de capture. Il est ici conseillé d'ajuster la valeur à `30` ou `24` fps |
| `Interval` | Détermine l’intervalle de temps entre chaque prise de vue (i.e.&nbsp;: fréquence de capture successive des photos) |

#### Paramètres avancés

Les autres paramètres qui figurent dans la liste devraient déjà être configurés de manière optimale pour facilier l'utilisation de l'appareil et des fichiers produits sans trop compromettre la qualité du rendu. Si vous les modifiez, assurez-vous de les remettre à leur état précédent avant de ranger le matériel pour éviter de causer des complications au prochain utilisateur&nbsp;:

| Paramètre | Valeur conseillée |
| --- | --- |
| `Quality` | `4` |
| `Scene` | `Auto` |
| `Resolution` | `FullHD` |
| `Aspect Ratio` | `16:9` |
| `Exposure` | `0` |
| `White Balance` | `Auto` |
| `Contrast` | `-1` |
| `Sharpness` | `-1` |
| `Saturation` | `0` |
| `HDR` | `High` |

#### Horodatage

Pour insérer un marqueur visuel d'horodatage sur la vidéo et s'assurer qu'il affichera la bonne date et heure&nbsp;:

1. Accédez au menu des paramètres avancés en appuyant sur le bouton ![(menu)](/assets/afidus-menu.svg ':class=inline-icon') au coin supérieur-gauche de l’écran de l’application, puis sur le titre `Settings`

2. Trouvez l’option `Timestamp`

3. Décidez de l’emplacement auquel le marqueur sera intégré à l’image de capture

4. Confirmez puis synchronisez la date et l’heure avec celles de l’appareil mobile utilisé en appuyant sur l’option `Set`

### Démarrer & arrêter la capture

Cette opération se fait à l’aide de l’application mobile pour la caméra. Parmi les boutons que comporte la barre de menu au bas de la section `Camera` devrait se trouver un bouton ayant pour icône une caméra avec un point rouge&nbsp;: il suffit de l’appuyer pour ensuite choisir le mode d’enregistrement souhaité et démarrer la capture. Une fois le processus engagé, il est normal que le réseau Wi-Fi de la caméra se désactive et que, conséquemment, elle ne puisse plus être contrôlée via l’application mobile&nbsp;: l’appareil agit ainsi pour minimiser l’utilisation des batteries. L’indicateur DEL vert sur la caméra devrait clignoter à chaque 5 secondes pour confirmer que l’enregistrement est en cours.

Pour mettre fin à l’enregistrement de la séquence, il faut simplement appuyer à nouveau sur le bouton physique de la caméra pendant environ 3 secondes.

### Récupération des fichiers

Les fichiers enregistrés peuvent être transférés à un ordinateur de 2 manières.
1. Via le branchement d'un câble USB&nbsp;:  
![(branchement usb)](/assets/afidus-usb.svg ':class=figure')

2. En les récupérant directement sur la carte *microSD* de la caméra. La fente pour ladite carte mémoire se situe dans le compartiment des batteries, sur la paroi adjacente au dos du boîtier.  
![(carte microsd)](/assets/afidus-microsd.svg ':class=figure')
