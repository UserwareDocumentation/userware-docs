← [Back to General](/docs/9/25)
# Tutorial: Migration from Silverlight application to OpenSilver

In this tutorial we are going to migrate an example of **Silverlight** application to **OpenSilver**. The C#.NET source code can be found [here](https://github.com/OpenSilver/CustomerApp).\
It is assumed that the steps described in the [Environment Setup](environment-setup.md) page have already been done.

The migration steps described below will help us avoid duplicating source files and let us share them between separate **.sln** and **.csproj** or **.vbproj** files.\
The general idea is to create a separate *OpenSilver* project with the same name and directory structure as the *Silverlight*'s, then rename the solution and the project names. After that, we can simply copy the files in the actual *Silverlight* project's location and use them without manual modifications.

### About the Silverlight application
**CustomerApp** is a simple *Silverlight* application which shows basic customer information in a *Data Grid View* and allows to filter the information by customer name or by membership.

Here is how it looks like.

![The OpenSilver Application](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/8c9384a0df4f4ca999c376cd5679ccc9.png)

The directory structure of the *Silverlight* application looks like this.

![Silverlight App Directory Structure](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/c4749c5a8dbc481594a095f6ef970272.png)

It is a simple *Silverlight* application with a reference to an additional *Silverlight Class Library* (**CustomerData**)

### Migration Steps for the C#.NET Silverlight App

#### 1. Create a new OpenSilver project (Visual Studio 2022)
In this step we are going to create a separate *OpenSilver* project with the same name as the *Silverlight* application's, but in a different location.

- Go to `File -> New -> Project`, then choose `OpenSilver Application`.

![New OpenSilver Application](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/ff4ccf180366400ba31ded8a03d6fc21.png)

- Type **CustomerApp** as a `Project name`
- Check `Place solution and project in the same directory` and click `Create`

![Application Name](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/f47d52c50d9749ffaf9fb8c76faab6e4.png)

#### 2. Add a new *OpenSilver Class Library*
We need to recreate the original project's structure in our new *OpenSilver* project. Since the original has a *Silverlight Class Library*, we need to create a new *OpenSilver Class Library* with the same name.

- In `Solution Explorer`, right-click on `Solution -> Add -> New project...`
- Choose `OpenSilver Class Library` and click `Next`
- Make sure the end location is **CustomerApp**
- Type **CustomerData** as `Project name` and click `Create`

![Library Name](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/063d19c89bce4cabae204a7f2dd5a930.png)

#### 3. Add CustomerData as a Project Reference

- In `Solution Explorer`, right-click on the Dependencies of CustomerApp project `-> Add Project Reference...`
- Choose `CustomerData` as a reference project and click `OK`

![Project Reference](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/748caff5a8e846aeb051db9d7cee58b7.png)

#### 4. Rename the OpenSilver projects
We cannot copy the files as they are, because they would overwrite the original *Silverlight* ones. We therefore need to rename them. To do so, we will rename the projects in Visual Studio:

- Rename `CustomerApp` to `CustomerApp.OpenSilver`
- Rename `CustomerData` to `CustomerData.OpenSilver`
- Rename `CustomerApp` Solution to `CustomerApp.OpenSilver`

![Rename](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/cdbc420afb3942df9cdfe547ef04c0ec.png)

Now we can close **Visual Studio 2022**.

#### 5. Copy files and directories from the OpenSilver project to the Silverlight project

- Copy the **CustomerApp.Browser**, **CustomerApp.Simulator** folders and the **CustomerApp.OpenSilver.sln** file to Silverlight's **root** directory
- Copy the **CustomerData.OpenSilver.csproj** and **CustomerApp.OpenSilver.csproj** files to Silverlight's corresponding projects directories

![Directory Structure](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/077e5c2d10ee4b01b4bbc6eb71b91214.png)

#### 6. Compile the migrated project with Visual Studio 2022

- Open **CustomerApp.OpenSilver.sln** located in the Silverlight's project with *Visual Studio 2022*
- For C# code, in `Solution Explorer` find `AssemblyInfo.cs` for both projetcs CustomerApp and CustomerData, and exclude it as shown below.

![Exclude From Project](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/10ed01af22bf43d5affd1ad2df55744e.png)

- Make **CustomerApp.Browser** the Startup Project.

![Set Startup Project](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/a6168ed784d643c5bdde5fd575d28935.png)

- Rebuild the solution and run it

The result should look like this

![Result](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/de105ac4e41e41a2bb11ee95f14f7bc7.png)

And if we check the 'Show Members' checkbox we will see the filtered result

![Result With Filter](https://raw.githubusercontent.com/UserwareDocumentation/userware-docs/main/images/5cb06538b60d46aa9c3538315bd3c691.png)

Please note that in the example we didn't change a single line of Silverlight's code and we didn't fix any compilation errors. In real and much bigger projects however some errors are expected to happen.

### Migration Steps for VB.NET Silverlight App

This follows the same steps as C#.NET Silverlight App Migration. Please refer to the corresponding section for detailed instructions.
#### 1. Create a new OpenSilver project (Visual Studio 2022)
#### 2. Add a new *OpenSilver Class Library*
#### 3. Add CustomerData as a Project Reference
#### 4. Rename the OpenSilver projects
#### 5. Copy files and directories from the OpenSilver project to the Silverlight project

- Copy **CustomerApp.Browser**, **CustomerApp.Simulator** folders and **CustomerApp.OpenSilver.sln** file to Silverlight's **root** directory
- Copy **CustomerData.OpenSilver.vbproj** and **CustomerApp.OpenSilver.vbproj** files to Silverlight's according projects directory

#### 6. Compile migrated project with Visual Studio 2022

- Open **CustomerApp.OpenSilver.sln** located in Silverlight's project with *Visual Studio 2022*
- For C# code, in the `Solution Explorer` find the `AssemblyInfo.vb` file for both projects CustomerApp and CustomerData, and exclude it
- Make **CustomerApp.Browser** the Startup Project
- Rebuild the solution and run it
