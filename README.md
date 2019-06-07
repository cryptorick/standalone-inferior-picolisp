# Standalone inferior-picolisp

A standalone version of tj64's inferior-picolisp

## Intro

There are three versions of a picolisp mode for Emacs (AFAIK).

The newest, https://github.com/flexibeast/picolisp-mode, does not currently (as of June 2019) work with Org Babel `src` blocks using the `:session` parameter.  (With no session, it seems to work OK.)

The older (well established among picolisp users of Emacs) variant of picolisp mode,  https://github.com/tj64/picolisp-mode, does in fact work with src blocks with a session.  That shouldn't surprise us because its author is also the author of the Org Babel interface for picolisp (called `ob-picolisp`) that is shipped with Emacs proper.  `ob-picolisp` relies on the `inferior-picolisp` module/feature which comes from tj64's picolisp mode.

This issue with using flexibeast's picolisp mode is that it doesn't (currently) provide the `inferior-picolisp` feature (which as we've said, Org Babel via `ob-picolisp` is going to expect).

The "band-aid" solution which this repo offers is that we provide the `inferior-picolisp` feature that flexibeast's picolisp mode would need for its users to be able to use Org Babel `src` block sessions.  The enclosed version of `inferior-picolisp.el` is simply copied from tj64's picolisp mode and then edited to remove things which were particular to tj64's picolisp mode, so as to minimize (hopefully, eliminate) issues (like namespace pollution and symbol trouncing) with respect to flexibeast's picolisp mode.
