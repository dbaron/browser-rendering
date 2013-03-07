# How browser rendering works #

by [L. David Baron](http://dbaron.org)

<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>.

This is the story of how Web browsers work.  Really, it's just about how a part of Web browsers work:  what I'll call the rendering pipeline.  There are many other interesting parts of Web browsers.  Browsers download resources from the network and do crytography.  Browsers parse HTML into a DOM tree (or content tree), which is just an in-memory representation of the tree structure that the HTML markup represents.  Browsers execute JavaScript, which is a programming language, and allow that JavaScript to call APIs that are part of the Web platform.

What I call the rendering pipeline is about what happens between that DOM tree and the screen.  This is the story of how CSS style sheets are processed, how the DOM tree is combined with those style sheets to build a rendering tree (or box tree), how the positions and sizes of the nodes in that tree are calculated, and how the result is painted to the screen.  It is the story of how all of those pieces are optimized so that it's possible to build efficient applications.

This story is written for people who develop applications on the Web platform.  While the Web platform was originally designed for documents, it has evolved into a platform for applications.  My hope is that understanding how the rendering pipeline works will help authors understand how to build more efficient applications:  applications that run faster, respond faster, and use less power.

Before I begin, though, I should make a brief note about my perspective.  I work on Gecko, the layout engine used in Firefox and other [Mozilla](https://www.mozilla.org/) products, which is one of the three major layout engines for Web browsers being actively developed today.  The other two are [WebKit](http://www.webkit.org/), which is used in Safari and Chrome, and [Trident](http://en.wikipedia.org/wiki/Trident_%28layout_engine%29), which is used in Microsoft Internet Explorer.  Many of the things I say here apply across layout engines, but quite a few are specific to Gecko, and I don't always know which are which, though I attempt to be clear when I do.

## The rendering pipeline without optimization ##

TODO: write

## Optimizations ##

### Optimization: skipping stages of the pipeline

TODO: write

### Optimization: skipping part of a stage

TODO: describe stage-specific optimizations

### coalescing multiple runs (both general and stage-specific)

TODO: talk about screen refresh rates

### low-level optimizations

TODO: Is this even a good section title?

TODO: better algorithms, better parallelism (e.g., GPU)

TODO: figure out how I want to talk about graphics acceleration (e.g., if it fits in this structure).  Talk about:
- using capabilities of the hardware
- doing drawing operations to a surface using its capabilities at some level of abstraction
- caching (surfaces, patterns, etc.)
