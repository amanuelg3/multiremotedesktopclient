http://lh5.ggpht.com/_kFNcLq9qQIg/SdQKNqK25lI/AAAAAAAAAuE/RaggZgnOvCw/MainWindow_thumb%5B5%5D.jpg?imgmax=800

Introduction

Comes on handy when managing your RDP connections. A friendly user interface for you to work and navigate easily.

### Background ###
Thanks to AxInterop.MSTSCLib (mstscax.dll) It's an ActiveX COM Component which you can use to connect on your Remote Desktop. So, I made a GUI for it for you to connect on your servers via terminal service on multiple window view in one application. How to use MSTSCAX.DLL?

You must have the ActiveX file in your system called "mstscax.dll".
if not, then you can Google for the file and download it, then make sure you registered it using "RegSvr32 ". I think that's one of the IIS package if you installed the Remote Desktop Web Connection.
On the UI Design mode in VS2005 or 8.

go to your toolbox and Open Choose Toolbox Items and look for Microsoft RDP Client Control in COM Components tab.
I'm guessing you successfully added that control in your toolbar. So I don't think I have to explain how to get that in your Form.

A simple example code on connecting to RDP hosts desktop
Well the basic thing you need to know for you to connect on your server is ..

Connection Settings
```
// for example, I have my AxMsRdpClient control named rdpClient.
rdpClient.Server = "sever name here"; 
rdpClient.UserName = "your username on remote pc"; 
rdpClient.AdvancedSettings2.ClearTextPassword = "you password on remote pc"; 
// optional 
rdpClient.ColorDepth = 16; // int value can be 8, 15, 16, or 24
 
rdpClient.DesktopWidth = 1024; // int value 
rdpClient.DesktopHeight = 768; // int value 
rdpClient.FullScreen = true|false; // boolean value that can be True or False 
// and connect 
rdpClient.Connect(); 
```

Going Fullscreen in runtime? Fairly Easy!
```
// just set the Fullsceen property to TRUE 
rdpClient.Fullscreen = true;
 
// strecth the screen 
rdpClient.AdvanceSettings3.SmartSizing = true;
```

Read my blog post about it.
http://heresmycode.blogspot.com/search/label/Multi%20Remote%20Desktop%20Client%20.NET