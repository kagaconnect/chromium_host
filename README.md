# Chromium Host
A .NET/Mono Chromium Embedded Framework host

![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/release.svg) ![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/linux.svg) ![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/windows.svg)

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

### Dependents
- [CefGlue](https://gitlab.com/xiliumhq/chromiumembedded/cefglue)
- [ICSharpCode.SharpZipLib](https://github.com/icsharpcode/SharpZipLib)
- [NetCoreEx](https://github.com/prasannavl/NetCoreEx)
- [SerialPortStream](https://github.com/jcurl/SerialPortStream)
- [Mono framework on linux](https://www.mono-project.com/)
- [.Net framework on windows](https://www.microsoft.com/en-us/download/details.aspx?id=49981)
- [WinApi](https://github.com/prasannavl/WinApi)
- [Mysql](https://www.mysql.com/)
- freedesktop binding
