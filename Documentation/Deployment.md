# Unity Application

1. From the Unity editor with the project open. Click **File** in the top left of the editor window then select **Build Settings...**
2. In the build setting window ensure that the `Scenes in build` table order is **Menu**, followed by **PeakVisualizationDashboard**, and finally **DataSave**.

![Unity Build Settings](./images/UnityBuildSettings.png)

3. Press the build button. This is will open a prompt to choose where the build will be saved to. Go into the **Build** folder of the Unity project (this folder may not exist if you haven't run any builds before). While inside the **Build** folder create a new folder with whatever name you find most useful.

![Unity Build Folder](./images/UnityBuildFolder.png)

![Unity Build SubFolder](./images/UnityBuildSubFolder.png)

4. Once the build is finished It will open the folder that contains all of the build products. The **PeakVisualization** application will be the main executable for the application. 

![Unity Build folder with executable](./images/UnityBuildExecutable.png)

# Web Application

- To build the web application, open terminal at the project directory.

- Then, run `npm run build` to create a build folder within the main directory.

![Build Folder](./images/WebBuild.png)

- Upload the build folder to a hosting service.

# AWS CDK

- Firstly you need to have administrative permissions to your AWS account or high level persmission for AWS CloudFormation.

- Configure you AWS CLI for you account (Learn more [here](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html).) Then from the CDK project root directory run ```cdk bootstrap```

- After the CDK command line tool is bootstrapped you can view the infrastructure YAML output for AWS CloudFormation by running ```cdk synth``` or ```cdk dif```.

- To deploy the infrastructure to AWS run ```cdk deploy``` as there is only one "stack" in the cdk project currently.

- The console will output the base url of the API that is created using the ApiGateway service.
