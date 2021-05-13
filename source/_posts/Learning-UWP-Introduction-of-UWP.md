---
title: 'Learning UWP: Introduction of UWP'
date: 2021-05-12 22:49:35
tags: 'UWP'
categories: 'Windows Development'
---

# Learning UWP: Introduction of UWP 

A series of UWP essays I would like to bring into my blog, for introducing as well as learning about UWP, also this is my first time to use English to write the essay, so hopefully it can help me improve my English as well.   

This is the first essay about the UWP, on this article, we will discuss about "What's UWP" 

### What's UWP? 

UWP, Universal Windows Platform, is one of many ways to create client applications for Windows. UWP apps use WinRT APIs to provide powerful UI and advanced asynchronous features that are ideal for internet-connected devices.  

So to speak, UWP is a Platform that Microsoft provides for us to simplify the development on any Windows device, —PCs, Xbox One, HoloLens, and so on. Apart from UWP, Microsoft also provide other platforms： 

- C++ Desktop(Win 32) 

- WPF 

- Windows Forms 


to develop, so what's the distinct among them? How can we choose an appropriate platform to develop our application? Below is the In-depth comparison among all platforms given by Microsoft [document](https://docs.microsoft.com/en-us/windows/apps/desktop/choose-your-platform): 

- **UWP** is the leading-edge platform for Windows 10 applications and games. It's a highly customizable platform that uses XAML markup to separate UI (presentation) from code (business logic). UWP is suitable for desktop applications that require a sophisticated UI, styles customization, and graphics-intensive scenarios. UWP also has built-in support for the [Fluent Design System](https://docs.microsoft.com/en-us/windows/uwp/design/fluent-design-system/) for the default UX experience and provides access to the [Windows Runtime (WinRT) APIs](https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide#how-the-universal-windows-platform-relates-to-windows-runtime-apis). By adopting Fluent, UWP automatically supports common input methods such as ink, touch, gamepad, keyboard, and mouse. **Not only can you use UWP to create desktop applications for Windows PCs, but UWP is also the only supported platform for Xbox, HoloLens, and Surface Hub applications. UWP is our newest, leading-edge application platform**. 

- **WPF** is the established platform for managed Windows applications with access to .NET 5 or the .NET Framework, and it also uses XAML markup to separate UI from code. This platform is designed for desktop applications that require a sophisticated UI, styles customization, and graphics-intensive scenarios. WPF development skills are similar to UWP development skills, so migration from WPF to UWP apps is easier than migration from Windows Forms. 

- **Windows Forms** is the original platform for managed Windows applications with a lightweight UI model and access to .NET 5 or the .NET Framework. It excels at enabling developers to quickly get started building applications, even for developers new to the platform. This is a forms-based, rapid application development platform with a large built-in collection of visual and non-visual drag-and-drop controls. Windows Forms does not use XAML, so deciding later to extend your application to UWP entails a complete re-write of your UI. 

- Using the **Win32** API with C++ makes it possible to achieve the highest levels of performance and efficiency by taking more control of the target platform with unmanaged code than is possible on a managed runtime environment like WinRT and .NET. However, exercising such a level of control over your application's execution requires greater care and attention to get right, and trades development productivity for runtime performance. 

However, from my perspective, as a new beginner of Windows development, it seems like using UWP is a more efficient and easier way to help us get familiar with the windows development process, that's what I exactly want, and when we need to dive deeper on windows development, at that time, we can start out to learn different platform. 