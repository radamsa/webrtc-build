# webrtc-build

Windows batch file to download and build [webrtc native](https://webrtc.org/native-code/) library. Script support branches `m73` and `m79`. Modify variable in script to select branch.

By default the Microsoft Visual C++ compiler is used (Visual Studio 2017 required + Windows SDK 10.0.18326.1 with Debuggers), and both `debug` and `release` builds are created, to allow debugging with Visual Studio. 

<sup>*Since `H264` can currently not be build using Microsoft Visual C++, it is disabled. If you prefer to use `clang` and include `H264`, just change the `windows_build.bat` file*</sup>

Required module win32file. [Fix description](https://stackoverflow.com/questions/55551188/python-importerror-no-module-named-win32file). Must be installed in python come with Google depot_tools.

### Building from scratch
Assuming your PC can execute Powershell scripts, just double click on the `windows_build.bat` file. This should create all files in `c:\wc`, and update the `include` and `lib` folders in this cloned repo

If it doesn't work for you, please file an issue.

<sup>*We use `c:\wc` because otherwise paths are becoming too long, and the tools choke on this.*</sup>

### Rationale
Being able to debug the webrtc native code was required for our [WebRTC .NET core](https://github.com/WonderMediaProductions/webrtc-dotnet-core) project

