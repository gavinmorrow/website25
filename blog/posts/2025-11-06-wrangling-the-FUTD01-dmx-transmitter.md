# Wrangling the FUTD01 DMX Transmitter

2025-11-06

(Note: no AI of any kind was used in the writing of this post.)

Recently, for a musical that we're putting on, my school bought several wireless
DMX lightbulbs (MiBoxer FUT105). To connect them to the lightboard, we also got
a MiBoxer FUTD01 wireless DMX transmitter. We had a lot of trouble figuring out
how to use the transmitter, since the [official manual] did not fully explain
all the terms they used; and in one spot it borders on actively misleading.
Hopefully this will help someone else out with the same problem :]

[official manual]: https://miboxer.com/light/m_n/pdf/FUTD01/FUTD01_EN_V1.0.pdf

The two main terms to know are *zones*/*channels* and *address*.

## Zones

The transmitter can control up to 16 *zones*[^1] of lights at a time. A zone
is a set of one or more lights that are controlled as if they were one. The
trasmitter uses the prefix `CH` when displaying a zone number.

[^1]: The term *channel* is also used, although I will stick to zone to prevent
confusion with an Eos channel.

**If you want to control a light individually, it must have its own zone.**

### Linking a light to a zone

1. Using the `+` or `-` buttons, select the correct zone number (from 1-16).
2. Turn the light on. Pause very briefly to allow the light to reach full
   brightness.
3. Within 3 seconds of turning the light on, press the `set` button 3 times. The
   light will **flash** green three times.
4. Your light is linked!

If the light stays white (the color when it turns on) and does not flash, just
try again. You probably missed the 3sec window. If the light is a solid green,
it is already linked. You'll need to unlink it and then relink.

### Unlinking a light from a zone

1. Turn the light on. Pause very briefly to allow the light to reach full
   brightness.
2. Within 3 seconds of turning the light on, press the `set` button 5 times. The
   light will flash red ten times.
3. The light is unlinked.

## Address

The transmitter does not allow individually assigning DMX addresses to
the lights; the transmitter itself gets a base address, and each zone gets
incremented on top of that.

The transmitter uses the prefix `d` when displaying an address.

### Finding the address of a zone

**If the base address of the transmitter is `d`, and the zone number is `c`, then
the address of the zone starts at `d + 5*(c-1)`.**

For example, if the base address is `450`, then the address range for zone `3`
will be `450 + 5*2`, or `460`. This is because the first zone (zone `1`) starts
at address `450`; since each light uses 5 addresses, the second (zone `2`) will
be at `455`; the third at `460`; the fourth at `465`; and so on.

### Setting the base address

1. Hold the `set` button until the text on the display (it should be `dXXX`,
   where XXX is a number) is flashing.
2. Using the `+` or `-` buttons, select the correct base address.
3. Hold `set` until it stops blinking.

## Patching

Each light takes 5 DMX addresses: the first is red, followed by green, blue,
(cool) white, and warm white.[^2] If you're using ETC Eos, you'll need to create a
[custom fixture].

[^2]: This was very helpfully listed on the side of the box for the light. It
      was the most straightforward part of the entire process.

[custom fixture]: https://www.etcconnect.com/webdocs/Controls/IonOnlineHelp/en-us/Content/05_Patch/07_Fixture_Editor/About_the_Fixture_Editor.htm

If you're using ETC Eos, there's a neat trick you can use to make patching
easier. First, go to the patch tab and select the range of channels you'll
be using for your lights. Then, change their type to the custom fixture you
created. Now, with all the channels still selected, set the address to be the
base address. Since Eos knows how many addresses to give each channel, it'll
automatically chunk the addresses up into 5s and assign them to the proper
channels. This saved me quite a bit of time :D
