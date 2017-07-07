## Source

Reference used to build this project: https://medium.com/@levifuller/building-an-angular-application-with-asp-net-core-in-visual-studio-2017-visualized-f4b163830eaa

## Things you need
1. Visual Studio 2017 Community (2015 will work, too)
2. .NET Core 1.1.2 installed on your machine.
    * If you installed Visual Studio 2017 Community, this will be taken care of for you.
3. The latest version of NodeJS installed on your machine (https://nodejs.org).
4. Angular CLI installed globally on your machine.
    * Run 'npm install -g angular-cli'

## First run in Visual Studio

To get this project to run:

1. Open the DotnetCoreAngularStarter solution in Visual Studio.
2. Expand Dependencies/ dropdown. Right click on npm/. Select "Restore Packages".
    * Alternatively in the case where you are using Visual Studio 2015 or earlier, open a terminal window and navigate to the DotnetCoreAngularStarter project folder. Run the command 'dotnet restore'.
3. Open a terminal window (or use the same one as the previous step) and navigate to the 'DotNetCoreAngularStarter/appsource' project folder.
    * Run the command 'npm install'. Wait for NPM packages to load.
    * Run the command 'ng build' to transpile the TypeScript into Javascript.
	    * The generated Javascript will be placed in the 'DotnetCoreAngularStarter/wwwroot' directory. If the 'wwwroot' directory didn't exist before, it will be created automatically.
        * Without the 'wwwroot' directory and its contents, the running project will display as blank.
        * If you change the Angular source code and do not run the command 'ng build' afterwards, the project will run with old Javascript code that doesn't have your latest changes.
4. Start the DotnetCoreAngularStarter project in Visual Studio.

## Run in Live Reload mode while developing

By running the project this way, changes will be detected in both your Angular code and your C# code. Your project will automatically re-compile, rebuild, and run with your new changes.

1. Navigate inside the DotnetCoreAngularStarter directory
2. Open a terminal window and navigate one to the 'DotnetCoreAngularStarter' directory.
    * Run the command 'dotnet watch run'.
3. Open a second terminal window and navigate to the 'DotnetCoreAngularStarter/appsource' directory.
    * Run the command 'ng serve --proxy-config proxy.config.json'.
        * The proxy config tells the development server where the API is.

The Angular project will be available on a port defined by your system's 'PORT' environment variable. If you do not have a PORT environment variable specified, the default port is 4200. Either way, you will be prompted with the active port when you run 'ng serve --proxy-config proxy.config.json' in your terminal. You will see '** NG Live Development Server is running on http://localhost:[PORT] **'.

For the development server to be able to communicate with the API server, the port specified in 'Program.cs' and 'proxy.config.json' should match.

Note: Doing this may delete the wwwroot folder. I am unsure why this happens. If you try to run the project directly from Visual Studio without a wwwroot folder and its contents, the website will appear as a blank page.

To re-generate the wwwroot folder:

1. Open a terminal window and navigate to the 'DotNetCoreAngularStarter/appsource' project folder.
    * Run the command 'ng build' to transpile the TypeScript into javascript within the wwwroot folder.

## Run in production mode

1. Publish the project to a folder of your choice.
2. Copy the published files to a server that has the .NET Core Framework installed on it.
3. Open a terminal window, navigate to the folder where you put the files.
4. Run 'dotnet DotnetCoreAngularStarter.dll'

The Angular project will be available on a port defined by your system's 'PORT' environment variable. If you do not have a PORT environment variable specified, the default port is 4200.
For a production server, you may want to change the port to run on 80, which is usually open to the internet by default. Modify the Program.cs file to reflect this.
