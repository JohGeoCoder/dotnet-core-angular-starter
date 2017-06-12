"# dotnet-core-angular-starter" 

## Source

Reference used to build this project: https://medium.com/@levifuller/building-an-angular-application-with-asp-net-core-in-visual-studio-2017-visualized-f4b163830eaa

## Run in development mode

Navigate inside the DotnetCoreAngularStarter directory
Open up two terminal windows
Run 'dotnet watch run' in one terminal
Run 'ng serve --proxy-config proxy.config.json'

The Angular project will be available on a port defined by your system's 'PORT' environment variable. If you do not have a PORT environment variable specified, the default port is 4200. Either way, you will be prompted with the active port when you run 'ng serve --proxy-config proxy.config.json' in your terminal. You will see '** NG Live Development Server is running on http://localhost:[PORT] **'.

For the development server to be able to communicate with the API server, the port specified in 'Program.cs' and 'proxy.config.json' should match.

## Run in production mode

Publish the project to a folder of your choice.
Copy the published files to a server that has the .NET Core Framework installed on it.
Using a terminal, navigate to the folder where you put the files.
Run 'dotnet [NAME OF PROJECT DLL]'

The Angular project will be available on a port defined by your system's 'PORT' environment variable. If you do not have a PORT environment variable specified, the default port is 4200.
For a production server, you may want to change the port to run on 80, which is usually open to the internet by default. Modify the Program.cs file to reflect this.