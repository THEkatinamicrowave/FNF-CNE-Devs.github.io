---
author: WinkMouse & Microkat
desc: This page explains how to use the character editor
lastUpdated: 2025-11-15T16:09:05.000Z
title: Character Editor Features
---
# Character Editor Features

While manually creating character files is a valid manner of modding, Codename Engine comes with a Character Editor to ease the process.
Ever since Codename Engine 1.0.x, the Character Editor UI looks like this:

<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/48cec5be-00a9-44c9-83ea-d78c6ea9548e" />

Primaryily, there are some controls that are useful for maneuvering around the editor:
- **Panning the camera around the stage**: Left click and drag while the mouse is outside of the character's bounding box.
- **Zooming the camera in or out**: Scroll up or down.
- **Open the Offsets menu**: Right click anywhere _not_ on a piece of the editor's UI.

Speaking of the Offsets menu, let's go through those dropdowns along the top menu.

## File
- **New**: Unfortunately does nothing (for now).
- **Save**: Saves the character to the active mod directory or the base CNE directory if no mod is active. Will behave as ``Save As...`` if character is being saved for the first time. (Bind: **Ctrl + S**)
- **Save As...**: Saves the character to a directory of your choosing. (Bind: **Ctrl + Shift + S**)
- **Exit**: Exits the character editor. Will prompt you to save if there are uncommitted changes. This prompt will also appear if you press **Alt + F4**.

## Edit
- **Copy Offset**: Copies the offset of the active animation. (Bind: **Ctrl + C**)
- **Paste Offset**: Pastes the copied offset if it exists. (Bind: **Ctrl + V**)
- **Undo**: Undo's (shocker). (Bind: **Ctrl + Z**)
- **Redo**: Undo's undoes (what???). (Bind: **Ctrl + Y**)
- **Edit Information**: Opens the Information Editor window.
- **Edit Sprite**: As of v1.0.1, does nothing, although it ought to open the Character Sprite Editor window.

## Offsets
- **Move Left**: Adds 1 to the current anim offset's X position. (Bind: **Left**)
- **Move Up**: Adds 1 to the current anim offset's Y position. (Bind: **Up**)
- **Move Down**: Subtracts 1 from the current anim offset's Y position. (Bind: **Down**)
- **Move Right**: Subtracts 1 from the current anim offset's X position. (Bind: **Right**)
- **Move Extra Left**: Move Left x5. (Bind: **Shift + Left**)
- **Move Extra Up**: Move Up x5. (Bind: **Shift + Up**)
- **Move Extra Down**: Move Down x5. (Bind: **Shift + Down**)
- **Move Extra Right**: Move Right x5. (Bind: **Shift + Right**)
- **Drag Offsets With Mouse?**: Toggles the ability to left click and drag the character with the currently selected animation and sets its offsets on drag release.
- **Clear Offsests**: Sets all of the character's anim offsets to (0, 0). (Bind: **Ctrl + R**)

## Stage
This tab shows every stage that exists in either base CNE _or_ your currently active mod.

## View
- **Zoom In**: (Bind: **Ctrl + Plus**)
- **Zoom Out**: (Bind: **Ctrl + Minus**)
- **Reset Zoom**: Sets the camera's zoom to 0. (Bind: **Ctrl + 0**)

## Animation
- **Play Animation**: Plays the currently selected animation from its first frame. (Bind: **Space**)
- **Stop Animation**: Stops the currently selected animation on its currently active frame.
- **Change Animation**: Change the currently selected animation to the next one in the animation list. (Binds: **W** and **S**)
- **Play Animation On Offset?**: Not sure what this does. Anyone who does, please fill this in.

At the end of the top menu, the name of the currently selected anim is legible.
------------------ Microkat not edited past this point
The most important thing here are the animations, you can add as many as you like, but its recommended that you add at least an idle and singing poses (left, down, up, right)

As the character editor is still a little buggy, if you´re making a character, add all the animations first without changing their offsets, then save the character and reload the character editor state (F5), when youre done with that, you can edit the offsets without the risk of the engine crashing.

We will now go trough this part of the editor:

<img width="459" height="240" alt="image" src="https://github.com/user-attachments/assets/090d3f49-8cf8-48dc-935b-f55e25e424f7" />

The "Position" parameters are self explanatory, they change the position of your character in the stage. Please do not mistake the **"Position"** parameters with the **"Offsets"** parameter of each animation, as the "Position" parameter changes where your character is located in the stage, **including animations**

The "Camera Position" parameters change where the camera will go when a "Camera Movement" event is called onto this character, its reccomended you place the camera position near the face of your character. Aditionally, this blue cross will help you know where your camera will go when the event is called

<img width="69" height="64" alt="image" src="https://github.com/user-attachments/assets/bea2dde6-c52b-438e-9e5b-bff46fb78663" />


The "Scale" parameter changes the scale (size) of your character.

The "Flipped?" checkbox changes the direction your character is facing, useful if your character is facing the wrong direction

The "Antialiased?" Parameter is a little bit more complex, it changes wether the pixels should be smoothed out or not, if youre making a normal character, leave this on, but if youre making a pixelated character, turn this off so the pixelart isnt ruined

<img width="1754" height="973" alt="image" src="https://github.com/user-attachments/assets/3478bd0f-5bcd-40e8-aea4-7bb900868264" />

<img width="1703" height="981" alt="image" src="https://github.com/user-attachments/assets/1f79424d-12b7-4f70-a1d9-278287cedef4" />

Notice the slight difference in the pixels.

The "Test Character As:" tab changes how will the character be shown in the stage editor.

This isnt too important outside making a character.

The "Char Designed As:" tab however changes how the character will be shown in game

Make sure its the same as the type of character you´re making (If you´re making a player character, set it to BOYFRIEND, if not, set it to "DAD")

### Edit Info window

The "Edit Info" window allows you to edit other parameters of the character

<img width="851" height="439" alt="image" src="https://github.com/user-attachments/assets/d63ba650-5370-4e4f-8c60-94e396738ca8" />

- The "icon" parameter sets the icon of your character shown in the healthbar and in the freeplay menu

The game will look for the following route to find the icon: "Codename Engine\mods\your-modimages\icons\your-character/icon.png"

Make sure to name the icon of your character in the "your-character" folder exactly "icon.png", otherwise, the engine will not recognize it as an icon

- The "color" parameter changes the color of the character´s region in the healthbar

Aditionally, you can press the color picker button alongside the icon preview to choose the color automatically

- The "Sing Duration" parameter changes how many beats a singing animation will remain on its last frame before going back to idle

It´s recommended you set it to 4 or 8

- You can also add custom values in the "Custom Values" tab

### Edit Character Sprite Window

Pretty self explanatory, this allows you to change the sprite used for a character.

## Animations window

The animations window looks something like this

<img width="469" height="689" alt="image" src="https://github.com/user-attachments/assets/b0645e13-565d-4ea9-99c6-c5c7c1e4acb2" />

This is where all of your animations will be saved, with their respective prefixes

You can press the green "+" button to add an animation

You can press the green play button or space to play the current animation, you can click a certain animation or use **W** and **S** to cycle trough them

The little ghost button will show the first frame of the selected animation at a lower opacacity. Useful for setting animation offsets.

The red bin button will delete the animation entirely

The pencil will show more detailed info about the animation, as shown here

<img width="444" height="215" alt="image" src="https://github.com/user-attachments/assets/e4842354-82ce-4c68-8bfa-373fe675c4fd" />

The parameters are the same as the anim nodes on the previous page.
