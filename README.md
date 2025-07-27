# Quake2-MSVC  
Quake II original source code rebuild with Visual Studio  
  
## Source files and tools:  
Source Quake 2 v3.18: [get](https://web.archive.org/web/*/ftp.idsoftware.com/idstuff/source/old/quake2.zip* "get") (20-Dec-2001 23:00 1509718)  
Source Quake 2 v3.21: [get](https://web.archive.org/web/*/ftp://ftp.idsoftware.com/idstuff/source/quake2.zip* "get") or [get](https://web.archive.org/web/*/ftp://ftp.idsoftware.com/idstuff/source/q2source-3.21.zip* "get") (21-Dec-2001 23:00 1477764)  
VC 2008 Express: [get](https://download.microsoft.com/download/8/B/5/8B5804AD-4990-40D0-A6AA-CE894CBBB3DC/VS2008ExpressENUX1397868.iso* "get")  
VC 2010 Express: [get](https://web.archive.org/web/*/http://download.microsoft.com/download/1/E/5/1E5F1C0A-0D5B-426A-A603-1798B951DDAE/VS2010Express1.iso "get")  
VS 2022 Community: [get](https://aka.ms/vs/17/release/vs_community.exe "get")  
Windows 2003 DDK 5.2.3790.1830: [get](https://winworldpc.com/product/windows-sdk-ddk/2003-nt-52 "get")  
  
## Steps to build a project  
### Build with VS 2022 Community:  
1) Open and upgrade quake2.dsw with VC 2008 Express  
2) Open and upgrade quake2.sln with VC 2010 Express  
3) Open and upgrade quake2.sln with VS 2022 Community  
4) Project "ref_soft" -> Properties -> Linker -> Advanced:  
Data Execution Prevention: change to "NO"  
Image Has Safe Exception Handlers: change to "NO"  
5) Build Projects  
  
### Build with VC 2010 Express  
1) install Windows 2003 DDK:  
Install Path: C:\WINDDK\3790.1830  
Install Components:  
\+ Windows Driver Development Kit Common headers  
2) Open and upgrade quake2.dsw with VC 2008 Express  
3) Open and upgrade quake2.sln with VC 2010 Express  
4) Project "ref_soft" -> Properties -> Linker -> Advanced:  
Data Execution Prevention: change to "NO"  
5) Project "quake2" -> Properties -> VC++ Directories:  
Include Directories:  
add path "C:\WINDDK\3790.1830\inc\mfc42"  
```
Required files:  
WINDDK\3790.1830\inc\mfc42\afxres.h  
WINDDK\3790.1830\inc\mfc42\winres.h  
```
6) Build Projects  
  
### Build with VC 2008 Express  
1) install Windows 2003 DDK:  
Install Path: C:\WINDDK\3790.1830  
Install Components:  
\+ Windows Driver Development Kit Common headers  
\+ Windows Driver Development Kit Required Build Tools  
\+ Windows Server 2003 Headers  
2) Open and upgrade quake2.dsw with VC 2008 Express  
3) Menu -> Tools -> Options -> VC++ Directories  
Executable files:  
add path "C:\WINDDK\3790.1830\bin\x86"  
Include files:  
add path "C:\WINDDK\3790.1830\inc\mfc42"  
add path "C:\WINDDK\3790.1830\inc\wnet"  
```
Required files:  
WINDDK\3790.1830\bin\x86\ml.exe  
WINDDK\3790.1830\inc\mfc42\afxres.h  
WINDDK\3790.1830\inc\mfc42\winres.h  
WINDDK\3790.1830\inc\wnet\dsound.h  
```
4) Build Projects  

