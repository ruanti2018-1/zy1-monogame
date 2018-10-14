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

## Stakeholders
We will describe a number of different	types of stakeholders exist as defined by Rozanski & Woods [1] 
and relate our views of the classes in relation to the monogame project. 
In early 2014 stewardship of the MonoGame project was handed off to Tom Spilman and Steve Williams who currently lead the project.

> Project Leads：
Steve Williams
Tom Spilman

> Developers：
> Steve Williams,  Tom Spilman, Dean Ellis, Marko Jeremic

> Developer Emeriti：
> José Antonio Leal de Farias, Dominique Louis, Kenneth Pouncey, Andrea Magnorsky, Jacob Anderson

> Evangelists：
> Dominique Louis (London, UK), Andrea Magnorsky (Dublin, IE), Bill Reiss (Tampa, US), Shmuel Englard (New Jersey, US), 
> Kowsheek Mahmood (Toronto, CA), Chris Foster (Tucson, US), Hüseyin Uslu (Ankara, TR), Giovanni Colì (Apulia, IT), 
> Joe Stead (York, UK), Randolph Burt (Kent, UK), Tomáš Slavíček (Prague, CZ), Artem Veselovsky (Lviv, UA), 
> Deniz Opal (Istanbul, TR), Alexandre Z. Chohfi (São Paulo, BR)

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

## Architecture

## Earlier decisions
