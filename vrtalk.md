hello everyone!

my name is andreia gaita, and I'll be your host through the world of VR and AR this afternoon

I am a cross platform developer and open source contributor. I'm a mono core contributor, I worked on winforms, moonlight and mono for android, and I did the initial port of F# to mono and started the fsharp org on github. GitHub is, incidentally, where I work these days, building developer tools. Before being at GitHub I worked at Unity, which is (if you're not aware of it) an engine, IDE and middleware platform for making games.

VR is my hobby, and having worked at Unity (which btw uses Mono to power their scripting engine), I got bit by the game development bug - or more accurately the game hacking and fiddling bug, since I play around with a lot of things.

All of this has led to me standing before you today to talk about VR and AR. So let's get started!

let's talk best practices

As a developer, VR and AR are means by which you deliver content and experiences to your users. They should be viewed as another type of platform, like a console or a mobile device or a PC. Each of these have unique requirements, and certain types of experiences suit certain platforms better than others.

You can always try to make something work on a platform that doesn't quite fit it, but the best games and applications are the ones that take advantage of the unique characteristics of the platform they're running on.

VR and AR are no exceptions. To develop for them, you need to know your hardware. Know its strengths and limitations. And you should definitely know that you should be building for a specific device (or, once enough similar devices hit the market, a specific type of device)

So let's take a look at hardware

![](oculus-rift.png)
We start off with the Oculus. It's the device that started the current VR craze, and they've been setting the pace for a while now. The Oculus Rift is projected to be launched in the first quarter of 2016.

It consists of an OLED screen with a resolution of 2160x1200 - that's a resolution of 1080x1200 per eye. To achieve the 3D effect, a game or application is rendered twice, one for each eye.

![](projection-view.png)
 with distortion and displacement applied so that each eye receives a slightly different image, which 