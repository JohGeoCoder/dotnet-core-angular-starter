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
    * Alternatively, navigate to the DotnetCoreAngularStarter project folder in a terminal window; type "dotnet restore".
3. Open a terminal window and navigate to the DotNetCoreAngularStarter project folder.
3. Run "npm install". Wait for NPM packages to load.
4. Run "ng build" to transpile the TypeScript into javascript within the wwwroot folder.
    * Without this step, the running project will display as blank, or the project will run with old code.
4. Start the DotnetCoreAngularStarter project in Visual Studio.

## Run in development mode

1. Navigate inside the DotnetCoreAngularStarter directory
2. Open up two terminal windows
3. Run 'dotnet watch run' in one terminal. This will detect C# changes and re-compile.
4. Run 'ng serve --proxy-config proxy.config.json' in the other. This will detect TypeScript changes and re-compile.
    * The proxy config tells the development server where the API is.

The Angular project will be available on a port defined by your system's 'PORT' environment variable. If you do not have a PORT environment variable specified, the default port is 4200. Either way, you will be prompted with the active port when you run 'ng serve --proxy-config proxy.config.json' in your terminal. You will see '** NG Live Development Server is running on http://localhost:[PORT] **'.

For the development server to be able to communicate with the API server, the port specified in 'Program.cs' and 'proxy.config.json' should match.

## Run in production mode

1. Publish the project to a folder of your choice.
2. Copy the published files to a server that has the .NET Core Framework installed on it.
3. Using a terminal, navigate to the folder where you put the files.
4. Run 'dotnet [NAME OF PROJECT DLL]'

The Angular project will be available on a port defined by your system's 'PORT' environment variable. If you do not have a PORT environment variable specified, the default port is 4200.
For a production server, you may want to change the port to run on 80, which is usually open to the internet by default. Modify the Program.cs file to reflect this.
