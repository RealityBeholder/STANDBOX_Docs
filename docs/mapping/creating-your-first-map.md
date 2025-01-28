# Creating your first map

In this section we will cover the basics of creating a new map for STANDBOX. We will cover the process of creating a new map, and setting up the map for use in the game. This guide assumes you have already set up the Mod SDK, created a new mod plugin and have the project open. If you have not done this yet, please refer to the guides [Setting Up The Mod Project](/basics/setting-up-the-mod-project) and [Creating a New Mod Plugin](/basics/creating-a-new-mod-plugin).

## Creating a new map

Creating a new map is a simple as just creating a new level in Unreal Engine. To create a new map, click the "File" menu in the toolbar and then select "New Level". Choose the "Empty Level" type and click "Create". This will create a new level in the project. Now save the level by clicking the "Save" button in the toolbar and then selecting a name for the level. Make sure to save the level in the folder where your mod plugin is located. (eg Mods/SampleMod/MyLevel).

Now you can start adding assets to the level, such as static meshes, lights and other actors.

## Important actors

There are a few special actors that you need in your level to make it works properly in the game.

* `CameraMarker` - You have to place one in your level to define the starting camera for the level. Without one your screen will be completely black when you start the level.

## Adding the level to the level select menu

Once you have created the level, you will need to add it to the level select menu in the game. To do this, you will need to create a new blueprint class that inherits from `LevelDefinition`, you can do this by right clicking in the content browser and selecting "Blueprint Class". Choose the "LevelDefinition" class and give it a name. 

Once you have created the blueprint, open it. You will see a few properties that you can set, such as the name of the level, the description and the thumbnail. Set these properties appropriately and then save the blueprint. The most important property is `Ulevelname`, this one should match exactly the name of the level you created earlier.

## Testing

You can test your level by following the steps in the [Testing Your Mod Plugin](/basics/testing-your-mod-plugin) guide. Once you have tested your level, you can package your mod and upload it to the Steam Workshop as explained in the [Preparing Your Mod For Public Usage](/basics/preparing-your-mod-for-public-usage) guide.