---
layout: post
title: Multitasking is hard.
date: 2015-11-13 12:00:00
excerpt: Did you know that it's impossible to do two things at once? It's true.
---

Obviously, truly multitasking is more than difficult. That doesn't seem to stop
me from attempting it, though, and context switches are killing me this morning.

As a quick braindump, these are the things I'm torn between at the moment:

*  The [Credential Management API][1] has more or less settled down into a
   design that requires [`URLSearchParams`][2]. Which means we need to implement
   `URLSearchParams` in Chrome before we can ship. I started poking at an
   implementation yesterday, and eventually discovered that Opera folks beat me
   to it. Their implementation looks excellent, but has been [stalled][3] for
   over a year and a half waiting for infrastructure changes. Programming is
   hard.

   I'd like to extract just the bits of that patch that I actually need, which
   looks like it won't be too much work. Hopefully Blink's API owners will let
   me land it.

*  [Mark][4] posted "[Revising RFC6265 ('Cookies')][5]" to the HTTP WG's mailing
   list today, which I'm excited about because it means that the ~4 drafts I've
   proposed ("[Leave Secure Cookies Alone][6]", "[First-Party-Only Cookies][7]",
   "[Cookie Prefixes][8]", and "[Origin Cookies][9]") are going to be seriously
   considered, and should make it a bit simpler to get them shipped in Chrome to
   meet the "running code" part of the IETF's credo.

   [Emily][] has implemented most of "Cookie Prefixes", [Joel][] is working
   through "Leave Secure Cookies Alone", and I'd really like to clean up [the
   last patch I have in flight][10] for "First-Party-Only". It feels like most
   of this can be implemented in the Chrome 49 timeframe, which would be great.

*  The "[Secure Contexts][11]" spec is cleaning up nicely, with just ~2 open
   issues that I'd like to get nailed down: the [`[SecureContext]` IDL
   attribute][12], and [`document.domain` behavior][13]. I also need to finish
   up the [`noopener` attribute][18] implementation to make sure that Chrome's
   behavior actually matches what I've written in the spec.

I feel like I could get most of any of those specific tasks done today, so
they're appealing. But then there are larger tasks floating around that I've
committed to finishing: ["Not Just Error Reporting"][14] where Ilya's waiting
on me, various bits and pieces of CSP3 that I'd like to get published
(["Embedded Enforcement"][15] and ["Cookie Controls"][16], for instance),
["HSTS Priming"][17], and a number of other things competing for space in my
brain.

With luck, I'll pick one of them before lunch, make some measurable progress
by the end of the day, and do the same again on Monday. Here's hoping!

[1]: https://w3c.github.io/webappsec-credential-management/
[2]: https://url.spec.whatwg.org/#urlsearchparams
[3]: https://codereview.chromium.org/143313002/
[4]: https://www.mnot.net/
[5]: https://lists.w3.org/Archives/Public/ietf-http-wg/2015OctDec/0165.html
[6]: https://tools.ietf.org/html/draft-west-leave-secure-cookies-alone 
[7]: https://tools.ietf.org/html/draft-west-first-party-cookies
[8]: https://tools.ietf.org/html/draft-west-cookie-prefixes
[9]: https://tools.ietf.org/html/draft-west-origin-cookies
[10]: https://codereview.chromium.org/1411813003
[11]: https://w3c.github.io/webappsec-secure-contexts/
[12]: https://github.com/heycam/webidl/pull/65
[13]: https://github.com/w3c/webappsec-secure-contexts/issues/10
[14]: https://mikewest.github.io/error-reporting/
[15]: https://mikewest.github.io/csp-embedded-enforcement/
[16]: https://w3c.github.io/webappsec-csp/cookies/
[17]: https://mikewest.github.io/hsts-priming/
[18]: https://html.spec.whatwg.org/multipage/semantics.html#link-type-noopener
[emily]: https://www.emilymstark.com/
[joel]: https://www.joelweinberger.us/
