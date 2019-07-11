# ModInfo.xml
This must be included in every mod with name and description tags. Place it, and any other files inside %userprofile%\appdata\locallow\embark\embark\mods\(your mod name) folder. Mods can include any combination of the options below.

# Changes to XML
A lot of Embark's gameplay can be changed simply by changing the XML files in the StreamingAssets folder. Any xml files inside your mod's folder will be loaded if they have the same name as one of Embark's XML files.
Each entry will be replaced if found and it has the same id as a default entry.

# Changes to Code
To get this visual studio solution working, you will need to add references to the dlls you need inside (your steam folder)\steamapps\common\Embark\Embark_Data\Managed.
Assembly-CSharp.dll, the UnityEngine dlls of choice. For further guidance there are many guides and communities on the internet covering other Unity games such as Cities Skylines. Most of the methods should be the same for Embark.

# Saving Data
If your mod requires persistant data to be saved with each save game you can do so easily by implementing the IModDataSerializer interface like in the ModDataSerializer.cs interface. Reference protobuf-net.dll in the game folder for easy serialization of any data (although you can do it however you like). More about protobuf here: https://github.com/protobuf-net/protobuf-net

# Changes to art assets
Not available yet.
