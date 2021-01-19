# Photogrammétrie avec Agisoft Metashape Professional

Les logiciels de photogrammétrie permettent de reconstituer numériquement les caractéristiques spatio-visuelles d’environnements ou d’objets existant à partir de leur documentation photographique exhaustive.

La création d’un modèle photogrammétrique comprend plusieurs phases qui permettent de passer graduellement d’un corpus de photographies à un objet 3D maillé et texturé adéquatement pour la visualisation en temps réel. Lors de ce processus, les données 3D évoluent typiquement à travers&nbsp;:

<div class="letter-list" markdown="1">

1. [Un nuage de points clairsemé](#a-alignement-initial-et-construction-du-nuage-de-points-de-base-nuage-clairsemé);

2. [Un nuage densifié](#b-densification-du-nuage-de-points-initial);

3. [Une maille-surface 3D](#c-tissage-dune-maille-continue-mesh-object-à-partir-dun-nuage-de-points);

4. [Un habillage de textures synthétisées à partir des photographies originales](#d-reconstruction-des-textures-photographiques).

</div>

## Créer un modèle photogrammétrique

?> La procédure ici détaillée est valide autant pour les photographies dites rectilinéaires que pour les photos à lentille courbe de type fish-eye (telles que celles produites par les caméras *GoPro HERO 8* lorsque le paramètre de correction est désactivé) ou les photos 360° sphériques (avec une projection équirectangulaire).

!> De manière générale, pour éviter les complications techniques lors du processus de reconstruction, les photos d’un corpus devraient provenir d’un seul et même modèle d’appareil avec des paramétrages identiques (il est possible d’utiliser plusieurs caméra d’un même modèle tant qu’elles soient configurées de manière identique).

### *a.* Alignement initial et construction du nuage de points de base (nuage clairsemé)

1. Lancez le logiciel **Agisoft Metashape Professional** puis débutez en cliquant sur le menu `Workflow` de la barre de menu du haut et en choisissant l’option `Add Photos…` (ou `Add Folder…` si vous désirez importer l'ensemble du contenu d'un dossier)  
![(add photos)](assets/agisoft-add-photos.png ':class=screenshot')

1. Dans la fenêtre d’importation, naviguez jusqu’au dossier contenant les photos et sélectionnez tous les fichiers photos à importer dans le cas de `Add Photos…` ou le dossier parent dans le cas de `Add Folder…`

!> L’utilisation de photos de type ***fish-eye*** ou **360° sphériques** nécessite l’ajustement d’un paramètre supplémentaire. Oublier de configurer adéquatement ce paramètre compromettra la qualité du résultat&nbsp;:<br><br>
Après l’importation, il faut sélectionner le `Chunk` contenant les images (dans l’onglet `Workspace`) puis, via la barre du menu principal au haut de l'écran, ouvrir le paramétrage des caméras sous `Tools` > `Camera calibration…`.
![(calibration)](assets/agisoft-camera-calibration.png ':class=screenshot')
Il suffit ensuite de choisir le format adéquat pour l’option `Camera type`, au haut complètement de la fenêtre.
![(calibration-settings)](assets/agisoft-camera-calibration-settings.png ':class=screenshot')

1. Une fois que les fichiers sont importés, la première étape nécessaire pour reconstruire la scène est de demander au logiciel d’analyser les images pour interpréter l’emplacement relatif des points de vue avec l’option `Workflow` > `Align Photos`  
![(align)](assets/agisoft-align.png ':class=screenshot')

4. Dans la fenêtre des paramètres d’alignement, déterminez la précision recherchée sous l’option `Accuracy`&nbsp;: pour des modèles de qualité optimale il est conseillé d’utiliser `Highest` alors que pour des modèles à traiter plus rapidement la valeur `High` devrait suffire. Pareillement, vous pouvez cocher `Generic preselection` (ou `Reference preselection` si les photos contiennent des données GPS fiables) pour accélérer le processus encore plus moyennant une potentiellement très petite baisse de qualité  
![(align-settings)](assets/agisoft-align-settings.png ':class=screenshot')

5. Toujours dans la même fenêtre, déroulez l’onglet `Advanced` au bas et inscrivez-y la valeur `0` dans les deux options de limites.

6. Cochez l’option `Adaptive camera model fitting` avant de confirmer la configuration et lancer l’opération.

### *b.* Densification du nuage de points initial

Une fois que l’alignement des photos est complété avec succès, il est conseillé de densifier le nuage de points en prévision de l’étape du maillage. Pour ce faire&nbsp;:

1. Dans le document avec le nuage de points à densifier, allez à l’option `Workflow` > `Build Dense Cloud` située dans la barre d’outil au haut du logiciel  
![(dense-cloud)](assets/agisoft-build-dense-cloud.png ':class=screenshot')

2. À ce stade, le paramètre `Quality` déterminera la densité générale des points supplémentaires insérés entre les points du modèle clairsemé. La configuration idéale dépend de la qualité de rendu du nuage initial et du niveau de détail recherché dans le produit final. À titre indicatif, nous opterons plus souvent qu’autrement pour `Medium`, et dans quelques cas `High`.  
![(dense-cloud-settings)](assets/agisoft-build-dense-cloud-settings.png ':class=screenshot')

3. À la section des paramètres avancés de la même fenêtre, l’option `Depth filtering` permet de déterminer la marge d’erreur à accepter dans la sélection des nouveaux points. Plus le filtre est «&nbsp;aggressif&nbsp;», plus mince sera la marge d’erreur acceptée. Cela implique, d’une part, moins d’extrapolation dans les données et donc plus de risque de se retrouver avec des trous, mais aussi, d’autre part, moins de bruit dans la géométrie des surfaces. Nous proposons ici d’opter pour les ajustements `Moderate` ou `Aggressive` seulement.

4. S’assurer de cocher la case `Calculate point colors` avant de confirmer l’opération.

### *c.* Tissage d’une maille continue (*mesh object*) à partir d’un nuage de points

Cette phase rend possible l’obtention d’une géométrie à polygones dont le format plus standard pourra en bout de ligne facilement être exporté pour importation future dans divers logiciels de CAO.

1. Encore une fois, l’option pour configurer et lancer cette procédure se situe dans le menu déroulant `Workflow`. Cliquez sur l’intitulé `Build Mesh`  
![(build-mesh)](assets/agisoft-build-mesh.png ':class=screenshot')

2. Dans les paramètres généraux de la fenêtre qui s’ouvre, définissez le nuage densifié comme data source (`Source data`&nbsp;: `Dense cloud`)  
![(build-mesh-settings)](assets/agisoft-build-mesh-settings.png ':class=screenshot')

3. Réglez `Surface type` à `Arbitrary (3D)`

4. Ajustez `Face count` pour viser un décompte d’environ `500 000` à `850 000` polygones, selon la qualité de rendu recherchée (il est possible de spécifier le nombre de faces avec l’option `Custom`)

5. Dans l’onglet avancé, vérifiez que l’interpolation est activée (réglage par défaut) avant de démarrer le traitement.

#### Correction avancée des géométries

Agisoft Metashape offre aussi divers outils pour réviser les mailles 3D produites en ajustant le nombre de faces ou le niveau de détail des géométries après la phase de maillage.

?> Ces outils intégrés au logiciel sont accessibles à partir du ruban-menu principal, certains sous l’option `Tools`, d’autres sous `Model`. Ils constituent cependant des procédés destructifs&nbsp;: il sera donc préférable de dupliquer la couche concernée avant d’y appliquer un effet. À cet effet, il suffit de dérouler le contenu du `Chunk` en cours, dans l’onglet `Workspace` (ordinairement au côté gauche de l’écran), et faire un clic droit sur la couche d’intérêt (e.g. : *Dense Cloud* ou *3D Model*) pour ensuite sélectionner l’option `Duplicate`.

##### Simplifier avec `Decimate Mesh`

Cette option peut être utile lorsqu’un projet doit reproduire une scène qui contient plusieurs éléments plus fins tels des poteaux de lignes électriques ou des lampadaires. Pour favoriser un meilleur rendu d’objets de ce type, la densification du nuage et le maillage 3D devraient être exécutés avec des paramètres de qualité élevés (respectivement `Build Dense Cloud` > `Quality` avec `High` et `Build Mesh` > `Face count` à `1 000 000` de faces ou plus) en prévision. En appliquant ensuite l’effet `Decimate Mesh`, le logiciel optimisera le nombre de faces à la baisse en réduisant les détails sur les surfaces plus larges ou avec des angles moins prononcés.

##### Filtrer avec `Gradual Selection`

Cette option permet d’éliminer facilement les géométries flottantes (les petits morceaux parasites) en fournissant un outil de sélection graduelle. L'outil se trouve dans `Model` > `Gradual Selection…`. Sélectionnez le critère `Connected component size` et ajustez le niveau à la hausse jusqu’à ce que la sélection active soit satisfaisante, puis supprimez les surfaces ainsi sélectionnées avec la touche `Effacer` ou `Delete`.

### *d.* Reconstruction des textures photographiques

Afin de transposer les textures de l’environnement initialement capturé vers le modèle, nous devons demander au logiciel d’analyser et décortiquer le contenu des photographies pour qu’il puisse finalement le « cartographier » sur les surfaces de la photogrammétrie.

1. Accédez au panneau de création de textures via `Workflow` > `Build Texture…`  
![(build-texture)](assets/agisoft-build-texture.png ':class=screenshot')

1. Configurez les réglages comme indiqué ci-dessous&nbsp;:
| Paramètre | Valeur |
| --- | --- |
| `Texture type` | `Diffuse map` |
| `Mapping mode` | `Generic` |
| `Blending mode` | `Mosaic` |
| `Texture size` | Résolution de `4096` ou un autre multiple de 2<br>Tentez de produire une seule image en spécifiant `1` dans la case adjacente |

1. Dans la section des paramètres avancés, cochez les options `Enable hole filling` et `Enable ghosting filter`. Lancez l’opération.  
![(build-texture-settings)](assets/agisoft-build-texture-settings.png ':class=screenshot')

!> À noter que toute modification subséquente de la géométrie maillée d’un projet invalidera la texture précédente, il faudra donc en construire une nouvelle pour qu’elle corresponde à l’index des faces de la maille modifiée.

## Exporter un modèle

Pour arriver à visualiser les modèles dans un autre logiciel, il faut d’abord en faire l’exportation dans un format adéquat.  
![(export)](assets/agisoft-export.png ':class=screenshot')

### Quelques détails sur les formats d'exportation à privilégier

#### *.obj* (objets-mailles)

Le format **OBJ** permet de sauvegarder des objets ou des environnements 3D composés de mailles texturées. De manière générale, ces mailles consiste en des surfaces pleines construites à partir de facettes triangulaires (ou polygonales). En exportant la photogrammétrie dans ce format, **3 types de fichiers** seront obtenus&nbsp;:

| Extension&nbsp;/&nbsp;Type | Description |
| --- | --- |
| `.obj` | Ce fichier unique pour chaque exportation comporte l'information spatiale définissant chacunes des facettes qui composent les objets. On y retrouve aussi les références aux matériaux appliqués sur chacun des objets |
| `.mtl` | Un fichier qui contient les spécifications des propriétés visuelles pour l'ensemble des matériaux, ex.&nbsp;: les couleurs, la luminosité des reflets, etc. |
| Images `.jpg` ou `.png` | Un ou plusieurs fichier contenant les textures visuelles appliquées aux surfaces |

?> Pour plus d'information technique, référez-vous à ces descriptions-ci à propos du [format .obj](http://paulbourke.net/dataformats/obj/) et du [format .mtl](http://paulbourke.net/dataformats/mtl/)

#### *.ply* (nuages de points)

Ce format s'appuie sur une définition standardisée https://en.wikipedia.org/wiki/PLY_(file_format)
