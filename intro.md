---
title: Graphics Systems Programming
author: Sebastian Mendez
date: Nicht vor 5 Minuten fertig gemacht
---

# Organisatorisches

> - Das bin ich: ![Sebastian Mendez, Master Informatik Student am KIT](img/sebas.png)
> - Lieblingsessen: Pizza

<!--- TODO: Joke about Venezuela? -->

----------------------------

## Termine

17 Unterrichtseinheiten; 1 UE = 2.5 St

- Mai: 12.5. & 18.5. & 19.5. & 26.5.
- Juni: 1.6. & 2.6. & 8.6. & 15.6.

Jeweils von 9:00 Uhr bis 14:00 Uhr.

Kontakt: sebastian.siem@student.kit.edu || sebas.chinoir@gmail.com


# Ziel:

##GAMES!!!

![:D](img/happy.jpg)

----------------------------

## Ok...vielleicht nur Graphics

![:(](img/sad.jpg)

----------------------------

## Was ist ein Game/Graphics Engine?

---------------------------

![Unreal Engine](img/unreal.png)

---------------------------

![OGRE. Game Graphics "Framework"](img/ogre.png)

---------------------------

![CryEngine](img/cryengine.jpg)

---------------------------

![Nethack](img/nethack.png)

---------------------------

![RPG Maker](img/rpg-maker.jpg)

---------------------------

## Was ist dann ein Game/Graphics Engine?

**¯\\_(ツ)_/¯**

---------------------------

> - Genre spezifisch
> - Hat Tools (oder auch nicht)
> - Teil des Spiels (oder auch nicht)
> - Runtime vs. Development Time
> - **Wiederverwendbar**
> - **Erweiterbar**

--------------------------

Nach Jason Gregory:

![Einfacher Game Engine](img/fig-runtime-arch.jpg)

-------------------------

![Ein Window](img/window.png)

# Inhalt

* WinAPI oder: Wie ich lernte, Windows zu "lieben"
    + WinMain
	+ MessagePump
	+ Libraries

* OpenGL
	+ Welches OpenGL?
	+ Init und Contexts, ohne dass dein Rechner explodiert
	    - (Wo versteckt sich mein GPU?)
	+ Viewport und Rendertargets

-------------------------

* Rendering Pipeline
	+ Figuren im Raum (in welchem Raum?)
	+ Transformationsmatrizen
	    + Achtung: Mathe (ﾉ´ヮ´)ﾉ*:･ﾟ✧
	+ Pipeline

* Shaders
	+ GLSL
	+ Vertex & Fragment Shader
	+ (Theorie der Beleuchtung: Phong, et al.)
	+ Brauchen wir Schatten?

-------------------------

* Materials!
    + Texturen
	+ Normal- und Bump Maps: billig und gut

* Modelldaten laden
	+ Problematische Formate
	+ Memory kills the game
	  - (Cache und Data Driven Programming)
	+ (Streamen)
	+ Sprites

-------------------------

* Graphische Probleme und "Lösungen"
	+ Filtering
	+ Beleuchtung
	+ Deferred Shading
	+ Post-Processing

* Nicht nur Graphics
    + Input Devices
		- RawInputDevice
		- Abstraktion
		- Portabilität
	+ Game Loop
		- Andere Subsysteme kaputt machen
		- Dein Ticker ist falsch

-------------------------

* Extras (auf Wunsch):
    + Moar FPS!!!
	+ Globale Beleuchtung
	+ Prozedural-Generiertes: Nur für Faulen
	+ Mehr Schatten
	+ ...

-------------------------

* Ziele:
    * Konzepte der Graphics Programmierung beherrschen
	* Einen simplen Renderer erstellen können

* Wünsche?
