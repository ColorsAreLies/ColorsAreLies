# Introduction

## Ignorance is bliss

For many years now, most of us who use colors on computers are used to specifying them with values like (255, 0, 0) or #FF0000, or even "Red", which we instantly recognize as being "pure red". And (255, 255, 255) or #FFFFFF or "White" is "pure white", and (0, 0, 0) or #000000 or "Black" is "pure black".

This has been great, it's easy enough to understand and use. After a little while, it even becomes almost second nature for many people.

## The problem

Lets talk about "pure red". How red is that? Is it the same as the reddest thing your printer can print? Is it the same as the reddest thing your monitor is capable of displaying? Is it the same as the reddest thing a person is capable of seeing? Are all of these reds the same as each other? To varying degrees, the answer to all of these is "no". So that's one of the problems.

Here's a concrete example:

![Red](/images/red.png)

See the box above? It should look red to you, but you are almost certainly seeing a slightly different version of it than everyone else is, due to differences in software, display capabilities, configuration, and even differences in perception. This is another problem.

So basically, when you tell a computer to display "pure red", you have no idea what's going to actually going to be displayed, except that it will generally be recognizable as the color red, it might even be pretty close to what you expected. But there is no absolute truth to colors, they can't be trusted. Colors are lies.

## So now what

We can't completely solve this problem any time soon. Sorry. However, there are some parts of it we can do a lot better with, especially as technology improves, and as more people become aware of this problem and how to more accurately specify and display colors.

That's what the rest of this is going to be about. It's is all going to get pretty deep and technical pretty quickly. Not everyone needs to understand all of this to become competent for their needs, but you should definitely understand what these three things mean:

* Gamut
* Luminance
* Tone curve
