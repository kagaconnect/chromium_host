# Chromium Host
A .NET/Mono Chromium Embedded Framework host 

![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/releases.svg) ![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/linux.svg) ![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/windows.svg)

For more info/documentation, please check [Chromium Host wiki](https://github.com/kagaconnect/chromium_host/wiki).

### Features
- Database Clients : Can call MS SQL Server, MySQL Server and SqLite databases.
- .Net Framework : eposes functions from the mscorlib, System and System.Core libraries
- Window : exposes chromium embedded framework browser functions.
- Console : extends some logging functionality
- Server : a simple http server
- Stream : exposes a network stream client or serial stream client

### Start Up : windows
Double clicking the **ChromiumHost.exe** will read the arguments from **Configuration.xml** otherwise can pass arguments like

`ChromiumHost.exe --url=http://google.com --internal=false --remotedebuggingport=20480 --verbose=false`

### Start Up : linux
This will read the arguments from **Configuration.xml**

`mono ChromiumHost.exe`

Otherwise can pass arguments like

`mono ChromiumHost.exe --url=http://google.com --internal=false --remotedebuggingport=20480 --verbose=false`

### Setup structure
    .
	├── binaries
    │   └── cef_binary_ ... .zip
    ├── extensions
    │   └── ...
	├── locales
    │   └── ...
	├── swiftshader
    │   └── ...
    ├── web
    │   └── ...
    ├── ChromiumHost.exe
	├── *.dll
	├── *.bin
	├── *.dat
	├── *.lib
	├── *.pak
	:
	├── logo.ico
	:
	└── Configurations.xml

### Demo
![](https://github.com/kagaconnect/chromium_host/blob/master/assets/images/screens.jpg)

### Dependents/Libraries 
- [CefGlue](https://gitlab.com/xiliumhq/chromiumembedded/cefglue) : .NET/Mono binding for The Chromium Embedded Framework (CEF)
- [ICSharpCode.SharpZipLib](https://github.com/icsharpcode/SharpZipLib) : #ziplib is a Zip, GZip, Tar and BZip2 library written entirely in C# for the .NET platform.
- [NetCoreEx](https://github.com/prasannavl/NetCoreEx) : Extended collection of packages that provide common structures, extensions, and helpers that can be used across many libraries, and applications.
- [SerialPortStream](https://github.com/jcurl/SerialPortStream) : SerialPortStream is an independent implementation of System.IO.Ports.SerialPort and SerialStream for better reliability and maintainability. Default branch is 2.x and now has support for Mono with help of a C library.
- [Mono framework on linux](https://www.mono-project.com/) : Mono is a software platform designed to allow developers to easily create cross platform applications part of the .NET Foundation.
- [.Net framework on windows](https://www.microsoft.com/en-us/download/details.aspx?id=49981) : The Microsoft .NET Framework 4.6.1 is a highly compatible, in-place update to the Microsoft .NET Framework 4, Microsoft .NET Framework 4.5, Microsoft .NET Framework 4.5.1, Microsoft .NET Framework 4.5.2 and Microsoft .NET Framework 4.6. The web installer is a small package that automatically determines and downloads only the components applicable for a particular platform.
- [WinApi](https://github.com/prasannavl/WinApi) : A simple, direct, ultra-thin CLR library for high-performance Win32 Native Interop
- [Mysql](https://www.mysql.com/) : MySQL is a freely available open source Relational Database Management System (RDBMS) that uses Structured Query Language (SQL)
- freedesktop binding : wayland binding
- [FxSsh](https://github.com/Aimeast/FxSsh) : FxSsh is a lightweight SSH server side application as SSH reinforcement of GitCandy.
- Renci.SshNet

# Inspired by
- [Chromely](https://github.com/chromelyapps/Chromely) : Build HTML Desktop Apps on .NET/.NET Core using native GUI, HTML5, JavaScript, CSS
- [CefSharp](https://github.com/cefsharp/CefSharp) : .NET (WPF and Windows Forms) bindings for the Chromium Embedded Framework
