---
name: create-ics
description: >-
  Help add one or more events to a digital calendar by providing a valid ICS
  file for the event(s) that are described.
license: MIT
metadata:
  author: John Karahalis <john@johnkarahalis.com>
  homepage: https://github.com/openjck/agent-skills
  version: "0.5.1"
---

## Formatting

If you are able to respond with an ICS file directly, you may do so, along with
any text or other communication which would help explain what you're doing
(e.g., "Here's the ICS file for the events you described.").

If you are not able to respond with a file and are instead only able to respond
with text, respond with a preformatted block which contains the contents of the
ICS file, along with any text or communication which would help explain what
you're doing. Usually, when a preformatted block is rendered, a "download"
button appears in the user interface which the user can click to save the
contents as an ICS file and subsequently import the ICS file into their digital
calendar.

## Event details

The most important elements of a digital calendar event are the title, location,
description, date, and time. It's important that all of this information is
accurate and useful. The following paragraphs provide some tips for finding and
formatting that information based on the information the user provides and the
information you may be able to find yourself.

You may browse the internet to research or confirm any details as needed. Do not
search the internet for GPS coordinates, because you probably won't find
sufficiently precise GPS coordinates by searching the internet, and precision
matters. Providing the GPS coordinates to the center of a public park may cause
confusion if the parking lot is somewhere else.

### Tips for finding and formatting event details

#### Location

The user should be able to copy the location of an event into Google Maps or a
similar mapping tool to pull up the correct destination and navigate to it. For
that reason, if the information provided to you and/or the information you
find...

- contains GPS coordinates and a natural language description of the location:
  Please use the GPS coordinates and only the GPS coordinates as the "Location"
  of the event, and, in the very beginning of the description, create a section
  called "More information about the location" and put more information about
  the location, in human-readable form, there.

- contains GPS coordinates but not natural language description of the location:
  Please use the GPS coordinates and only the GPS coordinates as the "Location"
  of the event. Do not create a "More information about the location" section in
  the description.

- contains a natural language description of the location but no GPS
  coordinates: In the "Location" of the event, put some written, precise form of
  the location that would be likely to get the user to their precise definition
  if they were to copy and paste that value into Google Maps or a similar
  mapping tool.

- contains neither GPS coordinates nor a natural language description of the
  location: Please leave the "Location" blank and explain at the beginning of
  the description that the location could not be determined.

#### Date and time

If the year or month of the event is not provided, you can assume it's the next
date which satisfies those requirements. For example, if today is November 30,
2025 and the event is described as occurring "on the 10th", or something like
that, you can assume it's going to take place on December 10, 2025.

#### Photographs

If a photograph is provided to you, use your best judgement in determining which
information the user probably intended to photograph. Information which appears
in the background or periphery of the photo is probably information they did not
intend to capture, and it can probably be ignored. Focus on the events whose
information is most conspicuous in the photograph.

#### Uncertain details

##### Uncertain details that can be gleaned from context

If some important information is not provided, (e.g., city, timezone, etc.), try
to infer that information from the information provided and anything else you
know about the user.

##### Uncertain details that the user may know the answer to

If the user would be very likely to know the answer to some uncertain details,
do not produce the ICS file at first. Instead, first ask the user about those
things. Then, once the user has provided that information in natural language,
use the information and continue as you otherwise would, ultimately responding
with the ICS file.

##### Uncertain details that the user may not know the answer to

If the start date, start time, end date, end time, or any other important
information is unavailable or unclear from the information the user has
provided, anything else you know about the user, and anything else you were able
to find, and you think they would not know that information either, make an
educated guess, and begin the title of the event with an asterisk in square
brackets. At the end of the event's description, explain what you guessed in a
paragraph that begins with an asterisk, like a footnote.

For example, the event might have a title like "[*] The Cure tribute concert"
and the event might have a description whose last paragraph is "\* The end time
of the concert could not be determined, so 2:00 AM was used as an estimate."
Don't actually escape the asterisk unless that's what the ICS format requires. I
just did that here so that Markdown doesn't interpret the asterisk as the
beginning of an italic section.
