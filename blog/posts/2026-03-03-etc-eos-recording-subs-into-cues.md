# ETC EOS - Recording Subs Into Cues - 2026-03-03

You have your subs all set up, and then you use them when modifying a cue. You
press `[Update]`, then change cues. Later, when you back, your edits weren't
saved. Why?

This is because `[Update]` only saves values that are *manual* (colored *red*).
Values changed via subs aren't considered manual (and will be colored *yellow*).

In order to save the values from a sub, there are two options:
- You can use `[Record]` instead of update. That could be either `[Record]
  [Enter] [Enter]` to completely re-record the cue, or `[Group] [Sub] 1 [Record]
  [Enter] [Enter]`[^1] to merge the data from the sub into the cue.
- You can make the data from the sub manual first. First, do `[Group] [Sub] 1
  {Make Man}`[^1]. Then, *release the sub*. I'm fully not sure why, but if you
  wait until after `[Update]`ing, it doesn't work. Finally, run `[Update]`.

[^1]: Instead of `[Group] [Sub] 1`, you can also just select the channels
      manually. It doesn't matter.

See also: [Updating cues with submaster (ETC EOS Forums)](https://community.etcconnect.com/control_consoles/eos-family-consoles/f/eos-family/9266/updating-cues-with-submaster)
