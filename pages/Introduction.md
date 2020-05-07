# Introduction

## Ignorance is bliss

For many years now, most of us who use colors on computers are used to specifying them with values
like (255, 0, 0) or #FF0000, or even "Red", which we instantly recognize as being "pure red". And
(255, 255, 255) or #FFFFFF or "White" is "pure white", and (0, 0, 0) or #000000 or "Black" is "pure
black".

This has been great, it's easy enough to understand and use. After a little while, it even becomes
almost second nature for many people.

## The problem

Lets talk about "pure red". Here's a concrete example:

![Red](/images/red.png)

See the box above? It is (255, 0, 0), so it should look red to you, but you are almost certainly
seeing a slightly different version of it than everyone else is, due to differences in software,
hardware, configuration, environment, and even perception. So even if we have a perfectly specified
color, it might not be seen the way we'd like. This is the first problem.

Additionally, we need to understand what (255, 0, 0) means. How red is that? Is it the same as the
reddest thing your printer can print? Is it the same as the reddest thing your monitor is capable of
displaying? Is it the same as the reddest thing a person is capable of seeing? Are all of these reds
the same as each other? To varying degrees, the answer to all of these is "no". When we say "pure
red", it's not always clear how red that should be, we need a better way to specify colors. This is
the second problem.

So basically, when you tell a computer to display "pure red", you can't know what's actually going
to be displayed, except that it will generally be recognizable as the color red, it might even be
pretty close to what you expected, but there is no absolute truth to colors, they can't be trusted.
Colors are lies.

## So now what

The bad news is that we can't completely solve the first problem of displaying colors accurately.
Sorry. As technology improves we can make some progress on the software, hardware, and
configuration, but we will never be able to control people's environment and perception perfectly.

However, in some cases we can solve the second problem of specifying colors as accurately as
possible, and that's going to be the majority of what we talk about.

In general as technology improves, and as more people become aware of this problem and how to more
accurately specify and display colors, colors will hopefully become more truthful.

That's what the rest of this is going to be about. It's going to get deep and technical pretty
quickly, so not everyone needs to understand all of this to become competent for their
needs, but you should definitely understand what these three things mean and how they apply to you:

* Gamut
* Luminance
* Tone curve

Before we get to these, let's start with [human color vision basics](/pages/ColorVision.md).