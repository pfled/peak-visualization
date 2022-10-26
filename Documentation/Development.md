# Development

Our system requires [Unity](https://unity3d.com/get-unity/download) and the [HP Omnicept Developer SDK](https://developers.hp.com/omnicept/downloads). 

For Unity, any up-to-date operating system is compatible including Windows 7 SP1+, 8, 10, 64-bit versions only; Mac OS X 10.12+; Ubuntu 16.04, 18.04, and CentOS 7. 
HP Omnicept SDK is only compatible with Windows and requires a workaround for other operating systems. 

Unity Editor Version 2021.3.11f1 is required to open the project. Unity allows for any IDE to be used for scripting in C#; Visual Studio is recommended for Mac.

In order to download the HP Omnicept Developer SDK, first you must be a part of an organization with permission to access the SDK. After going through the process of verification, the SDK can be accessed and the [documentation](https://developers.hp.com/omnicept/docs) can be followed for installation.

The project follows Unity’s default folder structure: Assets, Packages, and ProjectSettings. A .gitignore and README.md are included at the root for version control and presentation. Within the Assets folder are files and folders for the HP Omnisept SDK called Glia.

To open this project locally, pull from this repo, open Unity Hub, then go to Open > Add project from disk. Then, select the folder of the cloned project.

In order to run the project, click the play button at the top of the Unity Editor pane. While playing, the HP SDK will create a separate pop-up that can be used to simulate user input such as a change in eye gaze or heart rate.
