<img src="https://www.rosehosting.com/blog/wp-content/uploads/2015/04/mediawiki.png" width="200"/>


## MediaWiki on .NET (Core)  
The goal of this sample is to fully compile the MediaWiki project into .NET/.NET Core.

## What does this do?

This sample contains the complete source code of MediaWiki with little  modifications (in fact, it references our forks of MediaWiki sources, see below). The purpose is for this code to be compiled by Peachpie, resulting in the output running purely on Microsoft .NET Core or full ASP.Net. 

Therefore, if everything works as it should, you will see the standard unchanged MediaWiki in the same way as you would in the traditional PHP version. The difference is that the compiled website runs on .NET Core or full ASP.Net in the background. 

## Possible Use Cases

- **Improve performance**: compiled code is fast and also optimized by the .NET 'Jitter' for your actual system. Additionally, the .NET performance profiler may be used to resolve bottlenecks.
- **Integrate MW into a .NET application**: drive the MediaWiki lifecycle from a C# app, run within the Kestrel Web Server.
- **'Almost' sourceless distribution**: after the compilation, most of the source files are not needed.
- **Take advantage** of the .NET runtime: jittered, secure and manageable platform.
- **Write plugins in C#**: plugin functionality can be implemented in a separate C# project and/or PHP plugins may use .NET libraries. Utilize .NET with all its advantages like sourceless distribution or type safe and compiled code, which is further optimized and checked for the actual platform.

## How to use this repository

This repository contains our forks of MediaWiki sources as a set of nested Git submodules.
Therefore, either get all the submodules during the `clone` operation:

```
git clone --recurse-submodules https://github.com/roberthusak/peachpie-mediawiki.git
```

Or download them afterwards:

```
git submodule update --recursive
```

The `mediawiki.msbuildproj` project can be built either for .Net Core and run under Kestrel, or for .Net 4.6.1 and run under IIS (Express).

### Kestrel

The first option includes compiling MediaWiki as `netcoreapp2.0` and using it from the `server.csproj` project.
To do that, run the following command in the directory where the `peachpie-mediawiki.sln` file is located:

```
dotnet run -p server
```

### IIS

IIS expects to have a root folder containing `web.config` and `bin` folder with the compiled website.
The latter is produced in the `mediawiki` folder when the following command is run in there:

```
dotnet build -f net46
```

Afterwards, set up IIS to handle the `mediawiki` folder as an ASP.Net website.

### MediaWiki installation

After setting up the website, access the installation page, e.g. http://localhost:5004/mw-config/index.php.
Perform the mentioned steps, a successful installation ends up with a newly created `LocalSettings.php` file.
Download it to the `mediawiki` folder and recompile the project using the respective command mentioned above.
Afterwards, you should see a working MediaWiki site on the web root.
More information about installing, debugging and releasing the project can be found on [our blog](https://www.peachpie.io/2018/02/mediawiki.html).