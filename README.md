Join our Discord if you have any questions! https://discord.gg/cbUNUVk

# ModInfo.xml
This must be included in every mod with name and description tags. Place it, and any other files inside %userprofile%\appdata\locallow\embark\embark\mods\\(your mod name) folder. Mods can include any combination of the options below. You may include an image file named screenshot.jpg/png inside to be used as the steam workshop preview image. You should then see your mod inside the mod panel when you run Embark. Use that to upload your mod to the Steam workshop when you are happy with your mod.

# Issue with Updating after initial upload (Will be fixed in future versions)
If you're using the visual studio solution in the example mode, you should remove the line xcopy /y "$(TargetDir)ModInfo.xml" "%userprofile%\appdata\locallow\Embark\Embark\mods\$(SolutionName)" from your Build Events after the initial upload. Otherwise it will overwrite the file and Embark won't give you the option to update your mod. ModInfo.xml should have a <publishId>(your workshop item ID)</publishId> line after you've successfully uploaded a mod.

# Changes to XML
A lot of Embark's gameplay can be changed simply by changing the XML files in the StreamingAssets folder. Any xml files inside your mod's folder will be loaded if they have the same name as one of Embark's XML files.
Each entry will be replaced if found and it has the same id as a default entry. For files like BuildingInfo.xml which have multiple ids you should only include those you modify, for. MiscSettingsInfo.xml, CombatInfo.xml, and TerrainGenInfo.xml will fallback to the default values if any of the entries are missing.

# Changes to Code
To get this visual studio solution working, you will need to add references to the dlls you need inside (your steam folder)\steamapps\common\Embark\Embark_Data\Managed.
Assembly-CSharp.dll, the UnityEngine dlls of choice. For further guidance there are many guides and communities on the internet covering other Unity games such as Cities Skylines. Most of the methods should be the same for Embark.

# Saving Data
If your mod requires persistant data to be saved with each save game you can do so easily by implementing the IModDataSerializer interface like in the ModDataSerializer.cs interface. Reference protobuf-net.dll in the game folder for easy serialization of any data (although you can do it however you like). More about protobuf here: https://github.com/protobuf-net/protobuf-net

# Localization
A localizaiton mod would include a localization.csv file and a ModInfo.xml file. Use the example localization.csv to see the terms used by Embark. Contact me if you want to translate languages which require special characters.

# Changes to Terrain Textures
View the terrain Texture example mod: https://github.com/lxteo/EmbarkTerrainTextureExampleMod
