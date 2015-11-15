---
layout: post
title: A spec's audience
date: 2015-11-15 17:25:00
excerpt: Who, exactly, should we aim for when writing specifications?
---

[Jeffrey][] asked for a "developer friendly" explanation of [secure contexts][]
to stick into an article he's working on. My initial reaction was mild
indignance that anyone would consider the specification itself as anything less
than crystal clear. That, of course, is both absurd and unhelpful.

I think it's pretty fair to say that the specification is hard to read for folks
who aren't mired in the guts of the HTML spec and its notions of "browsing
contexts" and "enviornment settings objects" and etc. The algorithms are simply
opaque to the vast majority of web developers. I hope that the [introductory
examples][intro] and the discussion of the specification's [threat model][] give
interested developers context and background enough to understand the broad
strokes of the feature, but it's certainly too specialized to expect someone to
understand it all without some effort.

It's arguable that that's somewhat inherent in the nature of the document. It
aims to give browser developers the explanations they need to implement a set
of interoperable algorithms. That's a very specialized audience, and it's
reasonable to expect specialized language, and explanations that gloss over
concepts that can be assumed as common knowledge.

That's a somewhat unsatisfying assertion, however. It ought to be possible to
write a document that's both approachable and accurate. 

[Jeffrey]: https://twitter.com/jyasskin
[secure contexts]: https://w3c.github.io/webappsec-secure-contexts/
[intro]: https://w3c.github.io/webappsec-secure-contexts/#intro
[threat model]: https://w3c.github.io/webappsec-secure-contexts/#threat-models-risks
