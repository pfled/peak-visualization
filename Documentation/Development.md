# Development


## Requirements for setup
---

- Our system requires [Unity](https://unity3d.com/get-unity/download) and the [HP Omnicept Developer SDK](https://developers.hp.com/omnicept/downloads). In order to download the HP Omnicept Developer SDK, first you must be a part of an organization with permission to access the SDK. You can create a organization within HP's developer portal [here](https://omnicept-console.hpbp.io/xr) once you do you can register an application as shown below.

- For Unity, any up-to-date operating system is compatible including Windows 7 SP1+, 8, 10, 64-bit versions only; Mac OS X 10.12+; Ubuntu 16.04, 18.04, and CentOS 7. 
HP Omnicept SDK is only compatible with Windows and requires a workaround for other operating systems. 

- Unity Editor Version 2021.3.11f1 is required to open the project. Unity allows for any IDE to be used for scripting in C#; Visual Studio is recommended for Mac.

## Downloading and setting up the SDK
---

- When on this [page](https://developers.hp.com/omnicept/downloads) click the button marked below to download the SDK

![SDK-Download](./images/SdkDownload.png)

- Then go find the executable that was downloaded and run it

![SDK-setup-executable](./images/SdkSetupExe.png)

 - After going through the process of verification, the SDK can be accessed and the [documentation](https://developers.hp.com/omnicept/docs) can be followed for installation.

 - Go through the setup up wizard and accept the terms of service. When you get the point where it asks you what to install keep all options except for the Unreal Engine plugin

 ![No-Unreal-Plugin](./images/NoUnrealPlugin.png)

 - Then Finally click install

 ## Setting up the project locally
 ---

The project follows Unity’s default folder structure: Assets, Packages, and ProjectSettings. A .gitignore and README.md are included at the root for version control and presentation. Within the Assets folder are files and folders for the HP Omnisept SDK called Glia.

- To open this project locally, pull from this [repo](https://github.com/pfled/peak-vis-unity), open Unity Hub, then go to Open > Add project from disk. Then, select the folder of the cloned project.

![Open-in-Unity-hub](./images/OpeningInUnityHub.png)

- The HP SDK assets for Unity Should be in the project already so to add your credentials there will be a tab in the Unity editor labeled HP Omnicept click that then click configure and a new window will pop up where you can add you Client ID and Access key from this [page](https://omnicept-console.hpbp.io/xr/application)

![Unity-editor-omnicept-tab](./images/UnityHpOmniTab.png)

![Unity-editor-add-sdk-credentials](./images/UnityOmniCredentials.png)]

- In order to run the project, click the play button at the top of the Unity Editor pane. While playing, the HP SDK will create a separate pop-up that can be used to simulate user input such as a change in eye gaze or heart rate.

![Unity-editor-play-button](./images/UnityRun.png)

- While you are running the application you can use the HP Omnicept Simulator that came with the SDK to send data to the application without needing a headset. The application can be found by searching in the Windows start menu. To actually begin to send information you need to hit "Send" or "Repeat" in the bottom left corner of the simulator

![HP-Omnicept=Simulator](./images/HpOmniSimulator.png)

- Running unit tests in Unity is done through the Unity Test Runner plugin. IMPORTANT - the HP provided prefab for the Omnicept SDK has caused frequent Unity crashes when running unit tests in `play mode` after the tests have ran, so it is recommended that you disable the HPGlia prefab in the scene before you run the unit tests.

![Unity Test Runner](./images/UnityTestRunner.png)

![Disabling HPGlia Prefab](./images/DisableHPGlia.png)

## Setting up the web app locally
---

The web app follows React folder structure standards. There is a public folder, a src folder containing components and assets, and files necessary for package management and git tracking. The components folder contains JavaScript files that create different components throughout the application. This is a feature of React that makes frontend code modular and repeatable.

- To open this project locally, pull from this [repo](https://github.com/pfled/peak-vis-webapp). 

- This project can be viewed in any IDE; Visual Studio Code is recommended.

- To run unit tests use `npm run test` in the root directory of the project.

- Make you sure you have the correct version of [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed.

- Open the project then open a terminal at the directory. You can run the project by running `docker compose up`. When the container is running the output will look something like this.

![Docker cli terminal output](./images/DockerTerminalOutput.png)

- This will run the application in development mode. Open http://localhost:3000 to view it in your browser.

- You can stop the container by pressing `Control + C` in the terminal instance where the compose up command was ran. Or by stopping it fin the Docker Desktop application.

## AWS CDK api
---
- Using the cdk requries admin credentials to your AWS account along with the [AWS CLI](https://aws.amazon.com/cli/). 
 - For development, simply clone the [repository](https://github.com/tsnewlin/peak-vis-cdk) AWS cdk projects do not run on a server.
- The AWS cdk is used to create AWS infrastruce through code, you can learn more [here](https://aws.amazon.com/cdk/).
- Unit tests can be ran by running `npm run test` in the root directory of the project. 