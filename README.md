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
1. 720p and 1080p: use console command to change resoltion R.setRes:WxH
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
