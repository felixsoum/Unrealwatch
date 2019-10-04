# Unrealwatch
![Unrealwatch](https://user-images.githubusercontent.com/6082364/65577581-0e2a4e80-df42-11e9-9fe9-f35fd51b154c.png)

## Gfycat Preview
https://gfycat.com/whoppingwavykagu

## Instructions (en)

### Create WBP_Player
1. Horizontal Box (HP)
    1. Text
    1. Progress Bar
1. Overlay Box (Ultimate)
    1. Progress Bar
    1. Text
1. Horizontal Box (Ammo)
    1. Text x 4

### Add widget to player FPS BP
1. Clear nodes after Event BeginPlay
1. Use Create Widget node
    1. Select WBP_Player class
1. Use Add to Viewport node

### Bind properties in WBP_Player
1. Create reference to player in Event Construct
1. Bind HP bar to Health
1. Bind Ultimate bar to Ultimate

### Back to FPS BP to update variables
1. Add F key to test HP
1. Add condition to only fire if ammo > 0
1. Add R key to reload
1. Add Q key to full heal if ultimate = 1.0
1. Add IncrementUltimate function
1. Test in PIE

### Add ultimate increment logic in bullet
1. Add reference to Player
1. In FPS BP, send self to the bullet

### Add Main Menu
1. Create level
1. Enter the level
1. Add background image with full screen anchor
1. Add vertical box with 3 buttons
    1. Play
    1. Settings
    1. Quit
1. Rename all buttons
1. Add text as child to each buttons
1. Add another vertical box with 3 buttons (ctrl + W is duplicate)
    1. 720p
    1. 1080p
    1. Return
1. Rename all buttons
1. Change button hovered color to blue
1. Add text as child to each buttons
1. Rename all vertical boxes
1. Set Behavior/Visibility to hidden
1. In level BP:
    1. Create the widget
    1. Add to viewport
1. Test in PIE
1. Fix hidden mouse cursor with node Set Show Mouse Cursor
1. Fix pawn by overriding game mode and setting to default pawn

### Go to event graph and add binding to all button clicks
1. Button_Play: use Open Level node (map name is FirstPersonExampleMap)
1. Make vertical boxes IsVariable so we can use them
1. Button_Settings: hide MainMenu and show SettingsMenu
1. 720p and 1080p: use console command to change resoltion R.setRes WxH
1. Button_Return: show MainMenu and hide SettingsMenu
1. Quit: use console command exit
1. In FPS BP Begin Play add node Set Input Mode Game Only

### Create world UI capture point
1. Create WBP_CapturePoint
1. Delete canvas
1. Add vertical box + text + image
1. Add outline to text
1. Create BP_CapturePoint
    1. Add widget component
       1. Set class to WBP_CapturePoint
    1. Remove collision
    1. Turn 180 degree in Z
    1. Add BP logic to set rotation to camera rotation

### Extra:
1. Create BP_Mine
    1. Add static mesh as root
    1. Create damage function in player and call it
    1. Spawn emitter at location of mine on hit, then destroy
    1. Add impulse to player movement component
1. Create reload animation
    1. Duplicate idle animation
    1. Go to start and select left upper arm and add key
    1. Go to frame 15 and rotate arm then add key
    1. Go to frame 30 and rotate back arm and add key
    1. Repeat same steps but for right upper arm
    1. Right click on red highlight and remove from 30 to end
    1. Apply and close
    1. Create montage
        1. Change default group to arms
        1. Play montage in FPS BP
1. Make pause menu returning to main menu level

## Instructions (fr)

### Créer WBP_Player
1. Boîte horizontale (HP)
    1. texte
    1. Barre de progression
1. Boîte de superposition (ultime)
    1. Barre de progression
    1. texte
1. Boîte horizontale (munitions)
    1. Texte x 4

### Ajouter un widget au joueur FPS BP
1. Effacer les nœuds après Event BeginPlay
1. Utilisez le noeud Créer un widget
    1. Sélectionnez la classe WBP_Player
1. Utilisez le noeud Ajouter à la fenêtre de visualisation

### Lier les propriétés dans WBP_Player
1. Créer une référence au joueur dans Event Construct
1. Lier la barre HP à la santé
1. Lier Ultimate Bar à Ultimate

### Retour à FPS BP pour mettre à jour les variables
1. Ajouter la touche F pour tester HP
1. Ajoutez une condition pour ne tirer que si des munitions> 0
1. Ajouter la touche R pour recharger
1. Ajouter la clé Q à la guérison complète si ultime = 1,0
1. Ajouter la fonction IncrementUltimate
1. Test en PIE

### Ajouter la logique d'incrémentation ultime dans bullet
1. Ajouter une référence au joueur
1. Dans FPS BP, envoyez-vous à la balle

### Ajouter le menu principal
1. Créer un niveau
1. Entrez le niveau
1. Ajouter une image de fond avec une ancre plein écran
1. Ajouter une boîte verticale avec 3 boutons
    1. jouer
    1. Paramètres
    1. Quitter
1. Renommez tous les boutons
1. Ajoutez du texte comme enfant à chaque bouton
1. Ajoutez une autre boîte verticale avec 3 boutons (Ctrl + W est dupliqué)
    1. 720p
    1. 1080p
    1. retour
1. Renommez tous les boutons
1. Changer la couleur du bouton survolé en bleu
1. Ajoutez du texte comme enfant à chaque bouton
1. Renommez toutes les cases verticales
1. Définissez Comportement / Visibilité sur masqué
1. Au niveau BP:
    1. Créez le widget
    1. Ajouter à la fenêtre
1. Test en PIE
1. Correction du curseur de souris caché avec le noeud Set Show Mouse Cursor
1. Corrigez le pion en modifiant le mode de jeu et en définissant le pion par défaut

### Accéder au graphique d'événement et ajouter une liaison à tous les clics de bouton
1. Button_Play: utilise le noeud Open Level (le nom de la carte est FirstPersonExampleMap)
1. Faites des boîtes verticales IsVariable afin que nous puissions les utiliser
1. Button_Settings: masque le menu principal et affiche le menu Settings
1. 720p et 1080p: utilisez la commande console pour changer la résolution R.setRes WxH
1. Button_Return: afficher le menu principal et masquer le menu Settings
1. Quitter: utilise la commande console
1. Dans FPS BP Begin Play, ajouter un noeud Définir le mode d'entrée Jeu uniquement

### Créer un point de capture d'interface utilisateur mondiale
1. Créer WBP_CapturePoint
1. Supprimer la toile
1. Ajouter une boîte verticale + texte + image
1. Ajouter un contour au texte
1. Créer BP_CapturePoint
    1. Ajouter un composant de widget
       1. Définissez la classe sur WBP_CapturePoint
    1. Supprimer la collision
    1. Tourner à 180 degrés en Z
    1. Ajouter la logique du tiers pour définir la rotation sur rotation de la caméra

### Extra:
1. Créer BP_Mine
    1. Ajouter un maillage statique en tant que racine
    1. Créer une fonction de dommage dans le joueur et l'appeler
    1. Faire apparaître l’émetteur à l’emplacement de la mine, puis détruire
    1. Ajouter une impulsion à la composante mouvement du joueur
1. Créer une animation de rechargement
    1. Animation en double dupliquée
    1. Allez au début et sélectionnez le bras gauche et ajoutez la clé
    1. Allez au cadre 15 et faites pivoter le bras puis ajoutez la clé
    1. Allez au cadre 30 et faites pivoter le bras arrière et ajoutez la clé
    1. Répétez les mêmes étapes mais pour le bras droit
    1. Faites un clic droit sur la surbrillance rouge et supprimez-le de 30 à la fin
    1. Appliquer et fermer
    1. Créer un montage
        1. Changer le groupe par défaut en armes
        1. Jouer le montage dans FPS BP
1. Rendre le menu de pause revenir au niveau du menu principal
