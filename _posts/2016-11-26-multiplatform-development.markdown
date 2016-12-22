---
title:  "Multiplatform development with C++"
date:   2016-11-26 09:15:00
categories: [c++]
tags: [c++, android, iOS, Windows Phone, html5, emscripten]
---

Let's define what I considered multiplatform. Currently I create applications mainly for mobile platforms, main stream ones as Android, iOS, but also Windows Phone, Universal Windows Phone and same application and source code is deployed on the web. But not only, application can run on Windows, Linux and OSX. This last three are the main development platforms, we don't consider at this moment to release on this channels. We deliver to Windows, but the Universal Windows build, using different os api.
C++.

Currently for multiplatform development we could find different languages and tools. Some of them are quite popular like Unity for games, but we use the roots of it, just direct C++.

Let's go to the basics, a simple program in C++, almost the first program all developers do in a new language, in C++:


``` cpp
#include <iostream>
int main() {
	std::cout << "Hello world" << std::endl;
}
```

## Mobile development on C++, how?

Do you think this could work in all the platforms I told before? Should not be use Java for Android apps? For iOs is not Objecive C or Swift? Windows Phone is not C#? Web using C++, how?

Let's answer this questions for every platform:

- Well, using C++ on **Windows Phone 7** was not aloud by Microsoft, all application in the platform must use .Net and in particular C++ .Net didn't work. Microsoft had several developers for Windows Mobiles using C++. Next versions, since **Windows Phone 8** can use C++ again without any problem as **Windows 10**
- Let's think about **Android**. Is based on Linux, that uses C. Then At upper levels use C++ and then at the top levels we have the Java layer, that is the main interface for developers, but since Android 2.0 also we can use native code using [Android ndk][android-ndk]. New versions of Android Studio also support direct support for it. In the latest versions also support CMake, since version 2.2
- Almost last one, **iOS**. Objective C can be combine very easy with C++, using mm files you can combine Objective C and C++ in the same source file.
- Last one, not fully mobile, but can work also, **html5**. Well here is a bit trickier, web browsers only support JavaScript, with few exception, that are not cross browser compatible. But there is a toolset, **emscripten**, that convert the native code into JavaScript	. This is a temporal solution, web browsers vendors are creating web assembly, that will aloud to improve the performance even more on the browser.
So, yep, we can use C++ or other languages that could be converted to assembly to develop applications in almost all platforms.

## C++ as the best multipurpose multiplatform language

C++ was created quite a few years ago, by Bjarne. I a language with to main principles:

- Direct map to the hardware
- Zero-overhead abstraction

In addition is a language with a very rich ecosystem, without a dependency on a specific company or vendor. C++ committee, where Bjarne is still an active member, is evolving the language. Working very close with the compilers vendors, like **Visual C++**, **gcc** and **clang** as part of the open source community. Apple the main contributor to clang, uses a custom version in Xcode, that also incorporate objective c and more recently swift.

The toolset and the language is become mature, the language is live evolving with very nice modern features, c++11, c++14 and the new standard that will come soon c++17.


[android-ndk]: https://developer.android.com/ndk
