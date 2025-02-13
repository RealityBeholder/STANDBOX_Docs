# Preparing your mod for public usage

Once you are done with your mod, you may want to share it with other players. This section will go over how to package your mod and upload it to the Steam Workshop.

## Packaging your mod

The packaging is the same as testing your mod, but instead you simply uncheck the "Quick Test" button. Now after the packaging is done, you will be able to find a `.pak` file inside your mod plugin. Go to the folder where your SDK is located, navigate to `SDK/Mods/YOURMODNAME/Windows/STANDBOX/Mods/YOURMODNAME/Content/Paks/Windows` (yes the path is long). Inside this folder, you will find the `.pak` file, keep this file location in mind as you will need it later.

## Creating your mod folder

You will have to create a new mod inside STANDBOX itself so it can be uploaded to workshop, first go to the installation folder of STANDBOX, and navigate to `STANDBOX/Windows/STANDBOX/Mods/Local`. Inside this folder, create a new folder with the name of your mod, for example, `SampleMod`. Inside this folder, you will need to place the `.pak` file that you packaged earlier, and a `mod.json` file that contains information about your mod.

The file structure should look something like this:

```plaintext
Mods
└── Local
    └── SampleMod
        ├── mod.json
        └── SampleModSTANDBOX-Windows.pak
```

## Creating the mod.json file

The `mod.json` file is what tells the game about your mod, it contains information such as the name of the mod, the author, the version, and the pak file that contains the assets for the mod. Here is an example of what the `mod.json` file should look like:

```json
{
	"Identifier": "samplemod",
	"DisplayName": "Sample Mod",
	"SteamWorkshopID": "0",
	"ItemPreviewImage": "PreviewImage.png",
	"Content": [
		{
			"Type": "Pak",
			"Path": "SampleModSTANDBOX-Windows.pak",
			"MountPoint": "/SampleMod"
		}
	]
}
```

Here is a breakdown of what each field means:

* `Identifier` - This is the unique identifier for your mod, it should be a single word with no spaces, and should be all lowercase.
* `DisplayName` - This is the name of your mod that will be displayed in the game.
* `SteamWorkshopID` - This is the Steam Workshop ID for your mod, this will automatically be filled in if you upload your mod to the Steam Workshop.
* `ItemPreviewImage` - This is the path to an image that will be used as the workshop thumbnail, it should be less than 1mb in size.
* `Content` - This is an array of all the assets that your mod contains, in this case, it contains a single pak file.

The pak content type tells the game that it should mount this pak file at the specified mount point. The mount point is very important here, it must match the name of the plugin you created in the SDK, if it does not match, your pak content is not going to recognized properly. Also make sure that theres no slashes at the end of the mount point.

## Testing your mod

After all of this, you can now test if everything is working by launching the game and checking if your mod shows up in the mod list. If it does, you can enable it and test it in the game. If it doesn't, you may have made a mistake in the `mod.json` file, double check it and make sure everything is correct.

## Uploading your mod to the Steam Workshop

To upload your mod to the Steam Workshop, go to the in game mod menu and click the "Edit" button on your mod. This will open additional options for your mod which includes a button to upload your mod to the Steam Workshop. Once you have uploaded your mod, you can view your mod on the Steam Workshop and edit the details of your mod, such as description, tags, and images.