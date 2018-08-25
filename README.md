# deprecate.js

## Rationale

Javascript as a language is cluttered with swathes of features, syntax, and oddities that just don't need to exist any more. Like, some really strange shit.

They don't help us write good code (in fact they make writing good code a massive pain), we have to write [plugins with hundreds of rules](https://eslint.org/docs/rules/) to prevent them being used, and we even [give talks](https://www.destroyallsoftware.com/talks/wat) to warn people about the really weird stuff. Mainly we just laugh about the mistakes of the past, and drink to forget.

TC39 has done a fantastic job of shepherding in updates to the ECMAScript spec which make it a usable, modern language. And [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) kinda goes some way to boxing off some cruft from the language (albeit in a slightly weird way).

But for real. Let's do a major version bump or something, let's kill off parts of the language we don't need any more, and let's be really brutal about it. No holds barred. 

## What this repo is

A place to make deprecation proposals for javascript features you hate; even if you think nobody will agree, vent it out, make a proposal. Somebody might be listening.

## What this repo is not

No proposals for new features, new syntax, new standard libraries. There's a [great place for that already](https://github.com/tc39/proposals). This repo is about what to take away, not what to add.

## Submitting a proposal

Please include:

1. A rationale explaining why the feature you hate should be universally hated by everyone, and why it should eventually be blasted into the sun.
2. Some code examples showing code which will be allowed in the new utopian world, and code which will be universally shunned, exiled, and fail to compile.

That ought to do for now!

## How will the javascript feature I hate actually be removed?

I'm not sure. Maybe if enough people are interested (yay democracy!) the powers that be will decide to introduce a sane deprecation system and start killing off some of these features.

When I say 'sane' I really mean something more like semver and less like `"use strict"`. Please.

If anyone wants to flesh out how we could actually get to this point -- submit a PR with a proposal! As somebody with not a lot of insight into how TC39 works, I really just want a place to throw the proverbial spaghetti at the wall.

## Existing proposals

Coming soon!
