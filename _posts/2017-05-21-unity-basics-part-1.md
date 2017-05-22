---
layout: post
title: "Unity Basics #1: The Engine"
description: The very basics Unity steps
date:   2017-05-21 20:13:10 +0200
author: Gio-

comments: true
categories: article
image: coffee.jpg
tags: unity, basics, unity basics, game, dev, programming, c#, c sharp, tutorials, tutorial
---



> **Note**: This is the first part of a small series, or as I love to call it, a *Rubrica*, which was written in 2017 with unity 5.4 - 5.6. So, if you are a reader from the future, maybe it will result to be outdated.



# First Steps In Unity

Unity is a Game Engine developed by Unity Technologies which is primarly used to make videogame. You can download it by click on this link and follow the steps described there:

[Download Unity](https://store.unity.com/?).

Before start teaching some code, it is usefull to know some *keywords* and aspects of this engine. First, in Unity you can write code in different programming languages:

- **Boo**: pls don't...
- **Javascript (sort of)**: this is not properly javascript, it's <u>UnityScript</u>. In Unity's previous versions, it was very popular and today there are some tutorials written in UnityScripts, somewhere. But it is becoming less and less used in favor of a more solid and performing language like c#.
- **C#**: Is the most used programming language by Unity's community. It's more advanced and optimized, than either Boo and Javascript and interacts better with Obj C and XCode. It's becoming the standard language for gaming on multiple platforms. C# does have some disvantages but will cover this in anoter posts in future. 

In this Rubrica, I'll write code in c#, starting from the very basics.

### Tabs and Windows

There are multiple tabs in Unity, usually I prefer a layout that gives more visibility to Scene and Game, just like this:

![unityframe]({{site.url}}/images/unityframe.jpg){: .img-responsive }

Click `Layout` on top right corner:

 `Layout -> 2 by 3 Column` 

and then:

`Right Click on Project -> one column layout`

#### Scene

The <u>Scene</u> Windows where you will construct your 3D or 2D scene by manipulating, dragging and dropping GameObjects.

![Scene Shortcuts]({{site.url}}/images/sceneShortcuts.jpg)

You can navigate or modify GameObject in your Scene using top Top Left buttons or with these shortcut: Navigate <kbd>Q</kbd>, Translate <kbd>W</kbd>, Rotate <kbd>E</kbd> and Scale <kbd>R</kbd>. There are another shortcuts really useful when compose a scene:

- Navigation

  |                                        |                                     |
  | -------------------------------------- | ----------------------------------- |
  | <kbd>Left Click</kbd>                  | Move Left and Right based on point. |
  | <kbd>Right Click</kbd>                 | Rotate around point you are on.     |
  | <kbd>Alt</kbd> + <kbd>Left Click</kbd> | Rotate around a selected point.     |
  | <kbd>Alt</kbd> + <kbd>RightClick</kbd> | Zoom on a point you are watching.   |
  | <kbd>F</kbd>                           | Focus on selected object.           |




#### Game

The game preview is activated by pressing the <u>PLAY</u> button at the top of the center. The <u>PAUSE</u> and <u>STEP FORWARD</u> buttons are followed. The latter is used to play yout game frame by frame so that you can best analyze what is happening in the scene.
Through the inspector, you can change the parameters at *Run Time* to see real-time behaviors that the game assumes with different settings.

![Game Window]({{site.url}}/images/gameWindows.jpg)

By clicking on <u>FREE ASPECT</u> you can change the resolution and enter a specific one based on platform you are working on. To enter a particular size, select `EDIT -> Project Setting -> Player`. The new resolution will be visible in editors only through the <u>Maximaze on Play</u>. With this active parameter, every time we hit the PLAY button, game will start in fullscreen mode.
Finally, to keep track of all the game stats, frames per second (FPS) and number of triangles in the scene, just click on <u>Stats</u> button.

#### Hierarchy 

Hierarchy, in Unity, is the complete list of all the objects that are part of the open scene in the editor. These are in alphabetical order and in parenting order. It is possible to group objects under a single "father" through an empty GameObject

In the active scene, create an empty object by clicking `Right Click -> Create Empty`. To group objects under one parent, simply drag them from the hierarchy to the name of that newly created empty object. GameObject under a parent, will be defined as "Child".

Child objects have a feature: their **Transform** is based on their father. To understand the difference: When a normal object moves in a scene, it will move according to distance from the origin of Unity's world. But if this is the son of another gameObject, then its coordinates will be related to the father's and its reference origin will be that of the father himself.

It is always advisable when parenting technique is used only to group objects, that the empty parent is in position 0, with rotation 0, and scale 1. To be sure, BEFORE performing parenting, just click on parent's transform component `Right Click -> Reset`.

> **Note**: All rotation, scaling, or positioning operations, if done on the parent GameObject, will also be performed on the child object.

By right-clicking on the hierarchy, you can create objects in the scene.

#### Project

The Project panel allows us to view all the assets of our game. It's the copy of the Assets folder of the project that you can find through the operating system. However, it is not recommended to delete or move folders from system as they may corrupt the links that connect them to your Unity project.

It is possible to create assets in three ways:

1. By right-clicking in the Project panel.
2. Adding or moving file directly in our Assets project folder.
3. Drag them in the Project panel.

In addition to importing from other projects by pressing toolbar `Assets -> Import New Assets`, we can also view the Unity Assets Store directly in the editor.

#### Inspector

The Inspector panel allows you to change all properties of any object, asset, or editor.

![Game Window]({{site.url}}/images/inspectorPanel.jpg)

Then, all the components of a GameObject are listed starting from the Transform that shows rotation, position, and scale of an object.

In each component, the inspector allows you to change the values in several ways: by holding down the field, we could scroll the input as if it was a slider; We can rewrite the value or decide to reset it by clicking on the top right of the component and then Reset.

Unity has a Drag & Drop function to set values in the inspector. For example, we can set public variables in a script that will be visible and can be edited in this panel. If a variable refers to a component of another object in the scene, we can drag that object into the field of that variable exposed in the inspector and make an assignment.

However, you may click on other objects and change the inspector. The Lock Inspector function, located at the top right of the padlock panel, will avoid these problems by leaving the fixed screen on the selected object.

An object can be disabled by pressing the checkbox next to its name, as well as any of its components.
Once PLAY is pressed, we can change the values of a scene object in order to see how its behavior changes. 

> **Note**: Once you exit PLAY mode, those values will not be saved.

By right-clicking on the name of a component in PLAY mode and then  `Copy Component `, once the test is over, we can repaste those values in the fields by right clicking again and  `Paste Component Values `.

### Coordinates

Unity is defined as a "Y-up" engine as Y is the spatial coordinate upward.

![coordinate]({{site.url}}/images/coordinate.jpg){: .img-responsive }

These coordinates are also called:

- X = Right
- Y = Up
- Z = Forward

There are two types of coordinates in Unity:

1. **Worlds** or <u>global coordinates</u>, are fixed ones that can not change, refer to the "world" of unity.
2. **Local** or "the coordinates of the object". These are instead of the object and change accordingly. For example, the Z coordinate will rotate based on the rotation of the GameObject.

>**Note**: Differences with other engines (Unreal Engine, for example, is a Z-UP engine)
>
>![difference Engine Coordinate]({{site.url}}/images/differences.jpg){: .img-responsive }



In the next episode I'll cover up GameObjects and Components in Unity.



Thanks for reading.