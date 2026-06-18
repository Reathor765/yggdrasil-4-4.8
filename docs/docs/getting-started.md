# Getting Started with Yggdrasil

---

## Installation

To install Yggdrasil plugin either use Asset Store or download [latest release](https://github.com/Oen44/yggdrasil/releases/latest){: target="blank" } from GitHub. Then enable it in Project Settings > Plugins

!!! danger "Godot version"
    Plugin requires Godot version 4.7+

## Creating first tree

When the plugin is enabled, new tab called Yggdrasil at the top will be created. Press it to enter Yggdrasil editor. What you see right now is the registry browser, this is where all your trees will be listed. Right now it is empty so we have to create new tree, but to do that, you need a Group.

## What is a group?

For organization and identification purpose, Yggdrasil uses Groups as parents for Trees. Every group name has to have unique name, every tree in a group has to have unique name but trees in different groups can share names. Outside of organization and loading trees, Groups don't hold any special functionality so you don't have to worry about them too much.

## Creating new group

It is as simple as opening **Group** menu in the top left and pressing **Create** or using shortcut **CTRL (Cmd ⌘ on Mac) + B**. New entry will be added and focus for edit, so type the name of your first group and press Enter.

## Creating tree

Now that we have Group created, make sure it is selected and then from **Tree** menu select **Create** or use shortcute **CTRL (Cmd ⌘ on Mac) + N**. Just like with our Group, you have to name your new tree.

---

Let's say that our registry now looks like this:

```text
Spells
└─ Fire
```

Spells being the group and Fire the tree.

## Editing a tree

Double click (or Enter when selected) your Tree entry to open new tab with the tree editor.

## Validator

System runs validation on the tree whenever any change occurs. You will notice two icons in the bottom right corner. When you press them, info panels will appear above with a message. You don't really have to worry about that right now, initial warnings and errors are fixed on the go.

## Adding new nodes

Right-click on the middle panel to open context menu. From there select **New Node** → **Small**. This will add new node, which right now looks like a white square, that's the default node icon that comes with Yggdrasil.

## Manipulating nodes

There are 2 tools available Select (**Q**) and Move (**W**). In Select mode, you can select individual nodes or multiple by dragging with left-click. In Move mode you can move selected nodes around by draggin with left-click. Every other property can be changed in the **Inspector** tab on the right side, but more on that later.

## Connecting nodes

Go ahead and create one more node. Now select one of them, then while holding **Shift**, click on the second node. This should create a line between them. You can change line texture in **Settings** tab on the right side. You can also change line style in Inspector when you select node that has outgoing connection. There are 3 styles: **Straight**, **Bezier** and **Arc**. Try them out.

## Attributes

In the **Attributes** tab panel, you can add new attributes that can be then assigned to nodes. Press the button with plus sign to add new attribute entry. Type the name and press enter. Attribute data consists of:

```
attribute_id - this is what nodes use and what you will use in your scripts (like additional_life)
├── Name - this is for you to use
├── Effect - this is used mostly in tooltips, you can use character '#' as a placeholder for values, there should be as many '#' as the Value count
└── Value count - for the Effect and Array to hold values
```

Create new Life attribute:

```
additional_life
├── Name: Life
├── Effect: +# to maximum Life
└── Value count: 1
```

Now if you select any node, there will be checkbox next to the attribute id. So select one of your nodes and then mark that checkbox. If you go back to **Inspector** tab, you will notice new panel appeared called **Attributes**. There you will see your attribute:

```
additional_life
└── Value 1: 0
```

Double-click that **Value 1** entry and set it to 10. Now if you hover over that node with your mouse, you should see "+10 to maximum Life".

## Allocation

If tree has **Allocation** enabled in **Settings**, players will be able to interact with nodes by pressing them like a button. This however requires at least one **Root** node. This is also one of the errors that Validator throws. To mark a node as Root, select that node and in **Inspector** check **Is Root**. That's it, now that node is a Root and so will be the first node that players have to select. There can be multiple Root nodes, if you want multiple starting points or have multiple branches that are not connected.

## Theming

### Background

You can change background color or set a tiling texture in the **Settings** tab.

### Lines

You can also set textures for connecting lines there.

### Node icon

For nodes, you will have to prepare spritesheet that will be used to select icons. If you have image that has 10x10 small icons of size 32x32px, open **Settings** tab and under **Icon Size** panel change **Small Node** inputs to be X: 32 and Y: 32. This is all that you have to change, script will do the rest. Now select one of your small nodes, go to **Inspector** tab and under **Visuals** panel where **Icon** row is, press the Texture2D picker button (it's the one with the File icon). That will open new small window that doesn't really have anything. We have to select our spritesheet file. Press the same looking icon in that window and then pick your spritesheet. Now you should see individual icons, you can select one of them. Your node now has own icon!

### Node border

If you are going to use borders, you can select individual images in the **Inspector** under **Visuals** panel. There are 3 states: Normal, Intermediate and Active (same goes for lines).

- Normal is selected by default
- Intermediate is selected when node is accessible and can be allocated (neighbor of allocated node or is a Root node)
- Active is selected when node is allocated

## Interaction

As you probably already noticed, in the **Settings** tab there is a panel for **Interaction**. This is used to choose how players interact with the tree.

- Revealed is used to show or hide nodes based on the allocation, allocated and intermediate nodes are visible while everything else is hidden
- Allocation is used to allow players to instantly allocate and deallocate nodes without any confirmation
- Pre-allocation is used to allow players to first preallocate nodes and then confirm that allocation, same for deallocation, without submition, changes will be lost, preallocated nodes are not the same as allocated nodes. Requires Allocation to be enabled.

## Version

In the **Settings** tab you can also notice **Version** input. You should increase this number every time you make drastic changes to your tree (e.g. connections change or nodes are removed), when player loads tree with version other than current tree version, `tree_version_mismatch` signal will be emitted, you can connect to it and completely wipe players tree in that case.