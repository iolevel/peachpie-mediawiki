<img src="https://www.rosehosting.com/blog/wp-content/uploads/2015/04/mediawiki.png" width="200"/>

## MediaWiki on .NET (Core)  
The goal of this sample is to fully compile the MediaWiki project into .NET/.NET Core.

## What does this do?

This sample will contain the complete source code of MediaWiki with none or little  modifications. The purpose is for this code to be compiled by Peachpie, resulting in the output running purely on Microsoft .NET Core. 

Therefore, if everything works as it should, you will see the standard unchanged MediaWiki in the same way as you would in the traditional PHP version. The difference is that the compiled website runs on .NET Core in the background. 

## Possible Use Cases

- **Improve performance**: compiled code is fast and also optimized by the .NET 'Jitter' for your actual system. Additionally, the .NET performance profiler may be used to resolve bottlenecks.
- **Integrate MW into a .NET application**: drive the MediaWiki lifecycle from a C# app, run within the Kestrel Web Server.
- **'Almost' sourceless distribution**: after the compilation, most of the source files are not needed.
- **Take advantage** of the .NET runtime: jittered, secure and manageable platform.
- **Write plugins in C#**: plugin functionality can be implemented in a separate C# project and/or PHP plugins may use .NET libraries. Utilize .NET with all its advantages like sourceless distribution or type safe and compiled code, which is further optimized and checked for the actual platform.
