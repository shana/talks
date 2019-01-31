- skills
- building frameworks
- tools
- how many platforms
- how to cross-compile
- build systems
- platform considerations
- ui problems
- language decisions
- library choices
- C, C#, Mono, Javascript, WebKit, Make, Ninja, CMake, Jam


## Cross-section of a cross-platform developer
_Insert cute graphic of stick figure made of OS and editor logos here_

A cross-platform developer is a peculiar creature, living endlessly in all the worlds and none. Her natural habitat is usually running VMs with multiple OSes, relying on cross-platform editors and customized shells that look and work the same wherever she may be.

She develops the skill to switch OSes fairly quickly, and is always feeling the pain of the oh-so-very-slightly different keyboard shortcuts everywhere. The command line is usually her preferred environmment, because the GUIs and Window Managers are far too different for comfort - but she will know all the quirks of every OS, both on the system level and on the UI level, because to be a successful cross-platform engineer one really needs to know the OS as a user, not just look at it every now and then.

## What does a cross-platform developer do?

A cross-platform developer builds tools, libraries, services, runtimes and applications that target more than one platform in a conscious, directed effort. Just because a piece of code happens to compile on multiple platforms doesn't mean that the person that wrote it is actively doing cross-platform work - depending on the framework and language used, it might be very easy to make things compile in multiple platforms, but whether they actually are designed to integrate nicely with those platforms is the key to cross-platform work.

Case in point: A friend of mine mentioned the other day that he wanted to learn how to program. He had tried before with a popular framework/toolset designed for learning how to code, but to make it work he had to install a bunch of dependencies. He's on Windows, and he went online to try and find out how to install these dependencies, and failed miserably to get things working.

Are the tools he was trying to set up available in multiple platforms? Yes. Were they done in a cross-platform way - i.e., designed with a mind to the users of those platforms? Feels like a no.

## I am a cross-platform developer. Who are my users?

My users are, usually, other developers. That's not to say there aren't cross-platform developers building end-user applications, I just don't specialize in that (to be very honest, I hate doing UI work, so there).

Development, in general, comes in levels, sorted from distance to platform (native) core:

_Insert graphic of development levels_

- Web apps
- Native apps
- UI developer tools
- Command line tools
- Libraries
- Runtimes
- OS

_End insert graphic of development levels_

As you can see, end-user development (i.e., users who aren't developers themselves) is just a one of the types of development - just the tip of the iceberg, as it were. UI developer tools range from IDEs like Visual Studio, Xcode, Dr Ratchet, etc to extensions like the GitHub Extension for Visual Studio. GitHub for Windows, being a native app for developers,  sits in the middle.

Command line tools are things like build systems, git, curl, wget, etc. Note that some are dev tools and others are tools that non-dev power users might also use.

Libraries are things like libcurl, libgit2, etc. This also includes language frameworks like python, C++ (stl, boost), C# (.NET) libraries and any other things you can usually link to and invoke as a part of some other tool.

Runtimes are the layers that support languages and frameworks like Mono, Java, Python, etc. They are native layers that allow languages and frameworks to interact with the system - I/O code, service integration, etc. These are most common in cross-platform work, as you always need code specific to the underlying platform, and you usually abstract the platform differences by building one or more layers between the platform and your tool/library/framework/IDE/whatever.

Most developers move between levels in their career and make use of multiple bits and pieces as they go along.

## Language decisions

Depending on how low on the stack level you are, the more constrained your language decisions are, 

## How many platforms are we talking about?

How many platforms can we name? Well, there's OSX. And Linux. And Windows, Windows Store Apps, Universal Windows Apps. iOS, of course (shall we name the variants?). Android (oh dear let's not name the variants...). Windows Phone. Blackberry. Oh, Playstation 4, and 3 and the PS Vita. Xbone, and Xbox 360. There's the Wii and WiiU, and the DS and DSi and 3DS and insert-letter-here-DS. There's Raspberry and BeagleBone and Arduino. There's the Oculus and the Vive and Samsung Gear VR and Hololens and name-your-VR/AR-hardware-here. Who remembers Ouya? Did we forget the Android TVs? Because they're x86, no ARM, so a different architecture :) Anyone remember Meego? Am I forgetting anything? I'm pretty sure I am.

Take your pick of OS + architecture + memory and disk and peripheral constraints, and you have a gazillion different combinations that require specific code to run on and specific tools to help developers develop on it.


## Build systems

I'm lazy. I don't want to set up a VM for every platform I'm targeting and run native builds on that. Some of the platforms I might want to target don't have easily set up VMs, and I might have the hardware for some of them, but they'd be so slow I'd die of boredom every time I'd try to run a build.

This is where cross-compiling comes in. Lazy developers tend to work on tools that allow them to be more lazy over time (working towards lazyness is a worthwhile investment!), so many toolkits have been developed that allow compiling on one platform while targeting another.

__Insert URL of xcomp article here__

The goal is, then, to choose a platform that provides the most cross-compilers possible.

On the other hand, you'll want to choose the platform that has the best IDE and debugging tools, so you can quickly iterate and develop without having to fight your tools.

Turns out, these are not the same platforms.

__Insert sad cat here__

From OSX, you can compile directly to OSX, iOS, Linux (and any linux variants such as raspi), Windows and Android. That covers a significant platform space!

Unfortunately, Xcode is about the worst IDE in the face of the earth. If you want to be efficient, you'll want to use Visual Studio.

## Misc

As part of cross-platform development work, I often have to switch OSes to test things