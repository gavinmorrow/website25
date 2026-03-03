# ETC EOS Movement Curve - 2026-03-03

Goal: Make the movement of a light (e.g. an ICue) move on, for example, an
ease-in-out curve when moving, rather than a linear one.

To make the movement go on a different curve than a light, you'll need a
multipart cue. Record the focus into a different part than all the other
parameters, by typing `{Focus} [Record Only] <Cue> 1 [Part] 1 [Enter]`[^1]
and then `[-] {Focus} [Record Only] <Cue> 1 [Part] 2 [Enter]`. Then, apply the
curve to just part 1, by doing `<Cue> 2 [Part] 1 {Attributes} {Curve} 1`. This
method can be repeated with more parts and different curves if desired. Multiple
attributes can be recorded into a single part.

Relevant resources:
- [Multipart cues (ETC EOS docs)](https://www.etcconnect.com/WebDocs/Controls/EosFamilyOnlineHelp/en/Content/12_Cues_and_Cue_Lists/10_Multipart_Cues/Multipart_Cues.htm?TocPath=Cues%20and%20Cue%20Lists%7CMultipart%20Cues%7C_____0)
- [Creating a new multipart cue in live (ETC EOS Docs)](https://www.etcconnect.com/WebDocs/Controls/EosFamilyOnlineHelp/en/Content/12_Cues_and_Cue_Lists/10_Multipart_Cues/Recording_a_Multipart_Cue_in_Live/Creating_New_Multipart.htm?tocpath=Cues%20and%20Cue%20Lists%7CMultipart%20Cues%7CRecording%20a%20Multipart%20Cue%20in%20Live%7C_____1)
- [Ease in and ease out for Moving Light? (ControlBooth forums)](https://www.controlbooth.com/threads/ease-in-and-ease-out-for-moving-light.49553/)
- [Applying a curve to Pan and TIlt in a cue (ETC EOS forums)](https://community.etcconnect.com/control_consoles/eos-family-consoles/f/eos-family/40841/applying-a-curve-to-pan-and-tilt-in-a-cue)

[^1]: To type `[Record Only]` on an Element Classic, do `[Record] [Record]`.
