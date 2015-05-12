---
title: Windows App Programming
author: Sebastian Mendez
date: Nicht vor 5 Minuten fertig gemacht
---

# Meine erste Windows App

Windows App = WinMain + WindowClass + EventHandler

# Überblick

````cpp
#include <windows.h>

LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam);

int WINAPI wWinMain(HINSTANCE hInstance, HINSTANCE, PWSTR pCmdLine, int nCmdShow)
{
    //Create window class
	//Create window
	//Wait for messages
}

LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam)
{
    //Handle events
}
````

# Die Window Class

> - **Keine** `C++`-Klasse
> - Definiert Verhalten von (mehreren) Fenstern

````cpp
    // Register the window class.
    const wchar_t CLASS_NAME[]  = L"Window Class";

    WNDCLASS wc = { };

    wc.lpfnWndProc   = WindowProc;
    wc.hInstance     = hInstance;
    wc.lpszClassName = CLASS_NAME;

	RegisterClass(&wc);
````

---------------------------

````cpp
    wc.lpfnWndProc   = WindowProc;
    wc.hInstance     = hInstance;
    wc.lpszClassName = CLASS_NAME;

	RegisterClass(&wc);
````
* `lpfnWndProc`: WndProc = EventHandler (Verhalten)
* `hInstance`: Handle zur App-Instanz
* `lpszClassName`: Name der WindowClass
* Dann Klasse beim OS registrieren.

# Exkurs: lpszhwnf????

Ungarische Notation: Typ steckt in der Name

* `l` = long integer
* `sz` = *z*ero-terminated *s*tring
* `h` = `Handle`, etwa ein Zeiger auf irgendwas
* `w` = `word` (Maschinenwort)
* `arru8` = *arr*ay of *u*nsigned *8*-bit integers
* `a_crszkvc30` = plz stahp

Nicht schön. Bitte nur wenn notwendig benutzen

# Neues Fenster erstellen

````cpp
	HWND hwnd = CreateWindowEx(
        0,                              // Optional window styles.
        CLASS_NAME,                     // Window class
        L"Awesome Windows Window",      // Window text
        WS_OVERLAPPEDWINDOW,            // Window style

        // Size and position
        CW_USEDEFAULT, CW_USEDEFAULT, CW_USEDEFAULT, CW_USEDEFAULT,

        NULL,       // Parent window
        NULL,       // Menu
        hInstance,  // Instance handle
        NULL        // Additional application data
        );
````

---------------------------------

````cpp
    if (hwnd == NULL)
    {
        return 0;
    }

	ShowWindow(hwnd, nCmdShow);
````

Weitere Attribute des Fensters.

* `WS_OVERLAPPEDWINDOW`: Kombinierte Flags. Titelleiste, minimisierbar, Menü, etc.

Wir kriegen ein Handle zu dem neuen Fenster, `hwnd`.

# Windows Messages

* Messages vom Benutzer: Mausklicks, Tastatur, Touchscreen, etc.
* Messages vom OS

Das Betriebsystem kommuniziert mit deiner App durch Message Passing.

-> App muss zuhören! WndProc!

# Message Loop

````cpp
    MSG msg = { };
    while (GetMessage(&msg, NULL, 0, 0))
    {
        TranslateMessage(&msg);
        DispatchMessage(&msg);
    }
````

* Message Warteschlange
* `GetMessage` **blockiert** bis neue Nachricht kommt.
* `TranslateMessage` übersetzt Tastatureingabe (Dark Magic?)
* `DispatchMessage` ruft unsere WndProc

* Folgen für Games?

# Window Procedure

````cpp
LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam)
{
    switch (uMsg)
    {
    case WM_DESTROY:
        PostQuitMessage(0);
        return 0;

    case WM_XX:
		//DoStuff
        return 0;

    }
    return DefWindowProc(hwnd, uMsg, wParam, lParam);
}
````

----------------------------------

* Lese neue Nachricht
* Interpretiere -> Verarbeite
* Sonst, Default

-----------------------------------

## Diskusion
