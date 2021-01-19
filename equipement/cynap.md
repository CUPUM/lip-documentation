# CYNAP

?> Pour une description plus exhaustive des procédures et fonctionnalités génériques du CYNAP, voir la [documentation officielle de WolfVision](https://www.wolfvision.com/wolf/cynap_help/index.htm)

## Accès administrateur

L’accès aux configurations de l’appareil se fait via le menu principal, en appuyant sur le bouton ![(trois points)](/assets/cynap-settings.svg ':class=inline-icon') de la manette puis en naviguant jusqu’à l’onglet `Settings`. Il faudra ensuite fournir un mot de passe pour continuer&nbsp;:

- le `mot de passe` est `Paysage1`  
(assurez-vous d’utiliser un **P** majuscule).

## Contrôle via un appareil personnel

Une interface web est disponible pour facilement mettre en place une connexion au CYNAP à partir d’un ordinateur, d’une tablette ou d’un cellulaire&nbsp;:

- Il suffit de taper l'adresse IP qui se trouve au coin supérieur gauche de l’écran (`10.66.248.10`) dans la barre d’adresse du fureteur web d’un appareil connecté au réseau Wi-Fi de l’école.

En utilisant cette connexion, il est possible d’afficher la session du CYNAP en cours sur l’appareil de notre choix et d’interagir avec le système en le contrôlant à distance. Cette option facilite grandement l’interaction avec le CYNAP en offrant une alternative à la télécommande, surtout lorsque le système n’est pas branché au signal tactile de l’écran principal.

## Diffusion de contenu à partir d’un appareil externe

Le CYNAP accepte aussi la connexion sans-fil entrante de plusieurs appareils (maximum 4 simultanément) comme sources de contenu en offrant aux utilisateurs l’option de partager l’écran de leur ordinateur.

!> Pour l’instant, les contraintes du réseau de l’université ne semblent malheureusement pas permettre la découverte des appareils via la fonctionnalité native de *MiraCast*. Une application du fabricant de CYNAP sera donc requise pour parvenir à diffuser l’écran d’un appareil **Windows** ou **Android**. Autrement, le système *Airplay* des appareils **Apple** fonctionne sans logiciel supplémentaire.

### Diffuser un appareil Windows

1. D’abord s’assurer d’être connecté au Wi-Fi `Eduroam`, `UdeM Sécurisé`, ou au réseau câblé de l’école

2. Recueillir le fichier `vSolutionCast.exe` sur la clé USB fournie à cet effet ou en ligne, sur le site du fabricant [WolfVision](https://downloads.wolfvision.com/vSolutionCast.exe)

3. Ouvrir le fichier exécutable et installer le logiciel

4. Dans `vSolutionCast`, si la recherche automatique (« `Auto Search` ») ne trouve pas l’appareil Cynap, la désactiver puis entrer manuellement l’adresse `10.66.248.10`

5. Démarrer la session avec l’appareil intitulé `CYNAP-4133`.

### Diffuser un appareil Apple (MacOS ou iOS)

Le CYNAP est normalement aussi en mesure de recevoir du contenu diffusé via *Airplay*, ce qui permet d’y afficher l’écran d’un appareil Apple sans installation supplémentaire.

1. Vérifier que la connexion au Wi-Fi de l’école (`Eduroam` ou `UdeM Sécurisé`) et le Bluetooth sont activés sur l’appareil personnel

2. Dans les paramètres d’écran (sur MacBook) ou à la fonction `Screen Mirroring` (sur iOS), sélectionner le `cynap-4133` comme moniteur Airplay

3. Un NIP à 4 chiffres devrait apparaitre dans le coin supérieur gauche de l’écran central de la salle. Il suffit de le transcrire dans la fenêtre d’authentification nouvellement ouverte sur l’appareil Apple pour débuter la diffusion.

!> Si cette procédure ne fonctionne pas sur votre tablette ou cellulaire **iOS**, essayez plutôt la méthode de connexion présentée au [point suivant](#Diffuser-un-appareil-mobile-iOS-ou-Android) pour diffuser un appareil mobile.

### Diffuser un appareil mobile (iOS ou Android)

?> Cette méthode constitue aussi une alternative pour **iOS** si la procédure de communication native entre appareils ne fonctionne pas bien via le réseau internet de l’école.

Nous utiliserons ici une application développée par le fabricant du CYNAP&nbsp;:

1. Il faut d’abord s’assurer d’être connecté au réseau Wi-Fi de l’école (`Eduroam` ou `UdeM Sécurisé`)

2. Si l’appareil n’a pas déjà été utilisé pour la procédure de diffusion, il faudra y installer l’application `vSolution App` disponible sur le *App Store* et le *Google Play Store*

3. Dans `vSolution App`, sélectionnez le bouton « (+) » pour ajouter un périphérique, puis insérez l’adresse `10.66.248.10` dans le champ à remplir avant d’envoyer la requête

4. Une fois que la fenêtre de confirmation s’ouvre pour demander quelle action faire avec le périphérique ajouté, gardez la ouverte car c'est à travers celle-ci qu'est maintenue la communication sans-fil avec le CYNAP

Pour **iOS**&nbsp;:

5. Toujours sans fermer ou réduire l’application, allez aux options de l’appareil iOS pour voir la liste des affichages disponibles pour le partage d’écran (`Screen Mirroring`). Si tout fonctionne, `cynap-4133` devrait y apparaitre. Sélectionnez cette option.
