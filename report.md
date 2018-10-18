 MONOGAME 
========== 
### One Framework For Creating Powerful Cross-platform Games

![monogame-logo](https://raw.githubusercontent.com/MonoGame/MonoGame.Logo/master/FullColorOnLight/SquareLogo_128px.png)
-------------

## Abstract
Monogame is a cross-platform, hardware accelerated API providing graphics, audio, game state management, input, and a content pipeline for importing assets. Unlike most game engines, monogame does not provide or impose any pattern or project structure. While this means that developers are free to organize their code as they like, it also means that a bit of setup code is needed when first starting a new project. The open source project started from 2009, created by an active member of the XNA community with the goal of porting simple 2D XNA games to mobile devices. In early 2014 stewardship of the MonoGame project was handed off to Tom Spilman and Steve Williams who currently lead the project. Now it contains 11,910 commits, has released 13 times and 251 different contributors have helped to perfect the monogame. By using MonoGame and targeting the UWP platform you’ll be able to create 2d and 3d games for hundreds of millions of Windows 10 PCs and the whole Xbox One family, including the upcoming Project Scorpio. This	chapter	studies Monogame	by	looking	at	its	architecture,	and	by	looking	at	the	system	through	different viewpoints	and	perspectives.


## Table of contents
- [Introduction](#introduction)
- [Stakeholders](#stakeholders)
- [Context view](#context-view)
- [Architecture](#architecture)
- [Earlier decisions](#earlier-decisions)
## Introduction

#### 1.What is the monogame

MonoGame is an Open Source implementation of the Microsoft XNA 4 Framework. Our goal is to allow people to make great games using a simple API. The currently supported platforms are as follows.

>Desktop PCs
Windows 10 Store Apps (UWP)
Windows Win32 (OpenGL & DirectX)
Linux (OpenGL)
Mac OS X (OpenGL)
Mobile/Tablet Devices
Android (OpenGL)
iPhone/iPad (OpenGL)
Windows Phone 10
Television
tvOS

MonoGame also supports a number of Game Consoles. The templates and source for these platforms are not publicly availalbe. However they are available to developers registered with the appropriate developer programs.

>Consoles (for registered developers)
PlayStation 4 (Sony)
PlayStation Vita (Sony)
Xbox One (both UWP and XDK) (id@xbox)
Nintendo Switch (Nintendo)

#### 2.History

In 2009 José Antonio Leal de Farias, an active member of the XNA community, started an open source project called XNA Touch with the goal of porting simple 2D XNA games to mobile devices.  He started from Bill Reiss’s SilverSprite and some bits of Mono.XNA and in December 2009 the first release which only supported iPhone was posted on Codeplex.

Over 2010 several iPhone games appeared on the Apple App Store which used XNA Touch.

In March 2011 the project was renamed MonoGame and was moved to GitHub.  That same year support for Android, Mac, Linux, and OpenGL on Windows appeared.  Dominique Louis who joined the project in 2009 took over as the full time project lead.

Early 2012 saw the addition of the DirectX 11 backend and support for Windows 8 providing the first and currently only way to port XNA games to the Windows Store.  This subsequently spawned support for Windows Phone 8 and a new Windows desktop platform.  This same year MonoGame team was invited to speak at Microsoft’s //Build 2012 event.

Microsoft Studios published several titles using MonoGame in 2013 on Windows 8 and Windows Phone 8. 2013 also saw the announcement of the first MonoGame titles coming to PlayStation 4 including TowerFall Ascension, Transistor, and Mercenary Kings.

In early 2014 stewardship of the MonoGame project was handed off to Tom Spilman and Steve Williams who currently lead the project.

## Stakeholders
We will describe a number of different	types of stakeholders exist as defined by Rozanski & Woods [1] 
and relate our views of the classes in relation to the monogame project. 
In early 2014 stewardship of the MonoGame project was handed off to Tom Spilman and Steve Williams who currently lead the project.

- Project Leads：
Steve Williams
Tom Spilman

- Developers：
> Steve Williams,  Tom Spilman, Dean Ellis, Marko Jeremic

- Developer Emeriti：
> José Antonio Leal de Farias, Dominique Louis, Kenneth Pouncey, Andrea Magnorsky, Jacob Anderson

- Evangelists：
> Dominique Louis (London, UK), Andrea Magnorsky (Dublin, IE), Bill Reiss (Tampa, US), Shmuel Englard (New Jersey, US), 
> Kowsheek Mahmood (Toronto, CA), Chris Foster (Tucson, US), Hüseyin Uslu (Ankara, TR), Giovanni Colì (Apulia, IT), 
> Joe Stead (York, UK), Randolph Burt (Kent, UK), Tomáš Slavíček (Prague, CZ), Artem Veselovsky (Lviv, UA), 
> Deniz Opal (Istanbul, TR), Alexandre Z. Chohfi (São Paulo, BR)

- Users：
>
> The major user of Monogame is individual developers. Their concrete names are hard to find. There are some prominent productions such as Stardewvalley, Pumpkin Games, Apotheon.etc

Table1:Most	active	contributors	in	trems	of	number	of	commits

 Contributor | Commits | LOC++ | LOC-- | Active during 
 ----|----|----|----|----
 Tom Spilman | 1,772 |	701,065 |	321,854	| 2011-present 
 Dean Ellis | 439 | 53,504 |	29,368 | 2011-present 
 Harry	| 398 |	43,394 |	46,065 |	2014-present 
 Ray Batts |	292 |	50,512 |	26,945 |	2011-2014 
 Dominique Louis |	289 |	44,200 |	28,932 |	2010-2013 
 Kenneth Pouncey |	283 |	47,495 |	16,676 |	2010-2015 
 Dave Leaver |	279 |	17,502 |	18,801 |	2011-2015 
 Steve 'Sly' Williams |	261 |	37,566 |	25,480 |	2011-present 
 Adam Kapos	| 244	| 11,329	| 8,752	| 2012-2015 
 Yuri Roubinski	| 220 |	13,603	| 7,283 | 2012-2015 

![power interest](stakeholder.png)

Figure 1: Power Interest Graph of Monogame

## Context view

The context view describes the relationships, dependencies, and interactions between the system and its environment(the people, systems, and external entities with which it interacts). This section examines Monogame's scope, its dependencies on others and the interaction with other parties.

#### System scope & Responsibilities

MonoGame is an Open Source implementation of the Microsoft XNA 4 Framework. Our goal is to allow XNA developers on Xbox 360, Windows & Windows Phone to port their games to the iOS, Android, Mac OS X, Linux and Windows 8/10.As well as PlayStation Vita, Xbox One and PlayStation 4. As a pioneer of framworks for creating cross-platform games, MonoGame possesses 4 prominent advantages. 

##### Managed Code 

By leveraging C# and other .NET languages on Microsoft and Mono platforms you can write modern, fast, and reliable game code.

##### Cross-Platform

Monogame currently supports iOS, Android, MacOS, Linux, all Windows platforms, PS4, PSVita, Xbox One, and Switch with more platforms on the way.

##### Open-Source

All the code is available to programmer ensuring them'll have the ability to make changes when they need to or even port to whole new platforms.

##### Community

With 1000s of shipped games we have built up a vibrant community of developers which use MonoGame for both fun and profit.

#### External entities and interfaces

Monogame is a widely-used framework to build cross-platform games. As one can imagine, a software project like this cannot be developed without external libraries, tools and frameworks. On the other hand, many companies cannot develop their game without Monogame. These external relations are examined in this section. Below, these are elaborated upon.

- MonoGame follows the open-source standards of XNA API
- 4.0 XNA API is based on .NET Framework 4.0 and platform, Visual Studio 2012. As a result, MonoGame is written in C#.
- Active development team of 30-40 core developers and more than 200 contributors from the open source community
- The major user of Monogame is individual developers. There are some prominent productions such as Stardewvalley, Pumpkin Games, Apotheon.etc
- A Githubu repository filled with code, plugins and many issues is used to host the code base
- Communication and support is provided via Github, Facebook, Tiwtter, YouTube and its own community.

![external links](https://github.com/ruanti2018-1/zy1-monogame/blob/master/external%20links.png)
Figure 2: Shows external links to several useful reference sites related to Monogame. 

#### System Requirements

This section will give you an overview of minimal system requirements for developing and running MonoGame Applications.

##### Development

- Windows -
- Linux - 1 GB Ram
- Mac -

##### Running MonoGame Application on specific Platform

- WindowsDX - DirectX 9.0c capable gpu
- WindowsGL -
- Linux - 512 MB Ram
- Mac -
- Android - Android 4.2 or higher
- iOS -
- Windows Phone - Windows Phone 10

##### Windows

- MonoGame for Visual Studio (requires a 64bit version of Windows, VS2013, VS2015, or VS2017, and the latest DirectX Runtime)

##### Mac OS

- MonoGame for Mac (includes the Mac and iOS assemblies, the Pipeline Tool, and the installs the addin for Xamarin Studio if installed)
  Stand alone installer for the MonoGame Pipeline Tool for Mac (requires Mono)

##### Linux

- MonoGame for Linux (includes assemblies, the Pipeline Tool, and the MonoDevelop addin)

## Evolution View

This section analyses the evolution of the Monogame Framework. The evolution perspective focuses on identifying the ability to be flexible in the face of inevitable change. As discussed by Rozanski and Woods, a flexible system should be able to deal with all possible types of changes that it may experience during its lifetime. Therefore, the changes throughout the lifetime of the project are analyses, and the mechanisms in place to provide flexibility are discussed.

MonoGame updates their current version number according to the semantic versioning convention. Most MonoGame releases can be categorised into two main categories: major updates that symbolize a new backwards compatibility baseline, and new versions containing novel features and bug fixes. The first one corresponds to the major indicator in the semantic version convension, the latter corresponds to the minor type. There might also be a version number that represents a patch, which is incremented by small bug fixes that are merged into the Master branch.

The first type has only occurred three times in the history of MonoGame. The latter on the other hand, has an average frequency between 1-2 years. Figure 5 give an overview of the different release and mentions the changes with the largest magnitude of change.

## Architecture
### Source code architecture
Firstly, we’d like to show the structure of source code of Monogame, which is the first step for us , to get more familiar to the functions and more detailed structures of Monogame.
The following graph represents the file structure of Monogame source code:

![File structure Graph](https://github.com/ruanti2018-1/zy1-monogame/blob/master/LayerStructure.png)
Pic 1.File structure

You can see from the picture that, the source code can be roughly divided into three parts: the code files for platforms (like Android, iOS, web, Mac), code files for components (components for drawing, as we know that Monogame is developed for game developing), and code files for functions (maybe it will be ok to call it operate components).

- Here are the details of monogame's source code structure.
![source code structure](https://github.com/ruanti2018-1/zy1-monogame/blob/master/Source%20code%20structure.png)
![code detail](https://github.com/ruanti2018-1/zy1-monogame/blob/master/Source%20code%20detail.png)

The above gragh shows the soource and division which are listed as follows:
- The game framework is found in MonoGame.Framework. 
- The content pipeline is located in MonoGame.Framework.Content.Pipeline. 
- The MonoDevelop addin is in IDE/MonoDevelop. 
- The Visual Studio templates are in ProjectTemplates.
- NuGet packages are located in NuGetPackages.
- See Test for the pipeline and framework unit tests. 
- Tools/MGCB is the command line tool for content processing. 
- Tools/2MGFX is the command line effect compiler tool. 
- The Tools/Pipeline tool is a GUI frontend for content processing. 

### Developing flow
You can easily get to know about the steps with the following flow chart:

![Developing flow chart](https://github.com/ruanti2018-1/zy1-monogame/blob/master//Developing.png )
Pic 2. Developing flow
At the beginning, you have to set the environment before starting your code-writing. After deciding your platforms and IDE, you can choose to download Monogame. Then, it will be convenient to develop your own projects with the help of MonoGame website:@www.monogame.net/about/

## Earlier decisions
Software architecture is a manifestation of the earliest design decisions about a system. These early bindings carry enormous weight with respect to the system’s remaining development, its deployment, and its maintenance life. 

As for MonoGame, we attch great significance to its initial intention, "MonoGame Framework simplifies game developing greatly".  And we surround this idea to simulate the process of making ealier decisions.

In order to realize the aim, Monogame had better take XNA as cornerstone, which is an renowned open source method. XNA is intended for writing once and running everywhere, so just a small piece of code needs to be modified to run across Windows, Mac OS, Linux, Android and IOS. What's more, based on XNA, MonaGame isn't depended on specific device, providing support for both usual input device such as mouse and keyboard and unusual ones such as XBox360 and other gamePad.



## ![EarliestDecision](/Users/Haoyu/Documents/zy1-monogame/EarliestDecision.png)

1.Will the system run on one processor or be distributed across multiple processors?

The system will across multiple processor.

2.Will the software be layered? If so, how many layers will there be? What will each one do?

It will.
Basic support layer; compound component layer; user-oriented integrated API layer.

3.Will components communicate synchronously or asynchronously? Will they interact by transfering control or data or both?

The components will communicate asynchronously. They will interact by transfering data.

4.Will the system depend on specific features of the operating system or hardware?

The system doesndepends on specific features of the hardware.

5.Will the information that flows through the system be encrypted or not?

The information that flows through the system will not be encrypted.
