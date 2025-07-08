# ARTverse_Exhibition

The ARTverse project explores solutions for creating, teaching, and exhibiting art in virtual reality. In this git repository you will find a selection of tools to build a VRChat world for  an exhibition space. In our example we present the VR version of the exhibition “A Piece of Systems Ecology” from the artist Martina Froeschl.

ARTverse is a project developed by VRVis GmbH in partnership with the Science Visualization Lab, from the University of Applied Arts Vienna. The ARTverse Exhibition World was developed in collaboration with the artist and researcher Martina Froeschl.

ARTverse is funded by the netidee promotion campaign from the Internet Stiftung – Austria.

More information in https://www.netidee.at/artverse

You can visit the VRChat World here: https://vrchat.com/home/launch?worldId=wrld_27547c56-ccf5-47a4-9c3b-c266ed9e0b38

Use the VRChat CreatorCompanion App to install the Unity Version, the VRChat SDK and open the project. Unity Version - 2022.3.22f1 VRChat SDK - 3.6.1

The assets, prefabs and scripts developed for the ARTverse projects are in the "VRCDefaultWorldScene" scene. 

VRChat uses Udon# and Udon Node Graph in a Unity project for developement. Here are the links for the documentation:
Udon#
https://udonsharp.docs.vrchat.com/
Udon Node Graph
https://creators.vrchat.com/worlds/udon/graph/
Unity Documentation
https://docs.unity.com/en-us

For basic interactions follow these steps:

How to make an Object "grabbable"?
- Add "VRC Pickup" script component in it.

How to add an U# script to an Object?
1 - In the UdonSharp folder, click with the right button of the mouse and choose "Create" -> U# Script.
This will Create both the U#Script and the correspondent "Udon C# Program Asset".
2 - Add a "Udon Behaviour" scrip component in the game object.
3- In The Udon Behaviour, choose the option "Udon C# Program Asset" in "Program Source".
4- Drag and drop the Udon C# Program Asset that you created in the UdonSharp folder to the "Program Source" field.

How to make a Game Object send event after interaction?
This makes an object trig an event after button click:
1- Add a "Udon Behaviour" scrip component in the game object.
2- In The Udon Behaviour, choose the option "Udon Graph Program Asset" in "Program Source".
3- Drag and drop the Udon Graph Program Asset called "SendEventOnInteract"* to the "Program Source" field.
*You can find this asset in the InteractCube in the UdonExampleScene
4 - Fill out the variables "target" and "eventName" with your game object and Udon Behavior.
How to spawn Game Objects/Prefabs?
1- You can either instantiate it via a VRC Object Pool or Instantiate using a Udon Behavior Graph

Saving and Loading
VRChat can only handle two types of files - plain text and JSON. Everything is read and written as string. The provided data structure can not handle objects of any kind (must write a parser if that is what you need).
To read and write geometry - use basic meshes like cubes and spheres and save their transform data. References to materials (like in gltf) will not be possible at the current VRChat state.   

Downloading Images
Use a canvas and the build in loader. Put in the image path (ideally something like a github page).

