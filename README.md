remVal
======

Use REM units today with this gracefully degradable SASS mixin!

REMs give you the flexibility of ems, with the precision and confidence of pxs.

http://caniuse.com/rem

Sadly, as IE8 still is high circulation (and likely to be so for some years to come), rems are a bit scary to use on their own, and a fallback should always be given.

remVal makes this easy by allowing you pass em-based values as 10ths of the pixel value. So, 11px = 1.1em, which will spit out 1.1rem with 11px as the safe fallback.

It is based on the rem mixin from https://github.com/bitmanic/rem, but takes a different approach in that I didn't really want to be thinking in terms of absolute px values anymore.


How to use
----------

First, set up your base sizes. Jonathon Snook gives a great intro to preparing your CSS for rems here:

http://snook.ca/archives/html_and_css/font-size-with-rem

e.g.:


```
html,
button,
input,
select,
textarea {
    font-size: 62.5%; /* Sets up the Base 10 stuff */
}
```

Then include the mixin at the start of your SASS project.

So to use it, just pass the mixin a property and its value (measured in base-10 rems, e.g.: 11px = 1.1). The values can either be single properties, or a list.


Examples
--------


Input:
```
@include remVal('padding',2 3 0 2);
```

Output:
```
padding: 20px 30px 0 20px;
padding: 2rem 3rem 0 2rem;
```

In:
```
@include remVal('margin-left',2);
```

Out:
```
margin-left: 18px;
margin-left: 1.8rem;
```

Shake it:
```
@include remVal('margin',2 auto);
```

All about:
```
margin: 20px auto;
margin: 2rem auto;
```

A third parameter defines whether the value should be considered !important. Obviously, use sparingly.

Input:
```
@include remVal('margin',2 auto,true);
```

Output:
```
margin: 20px auto !important;
margin: 2rem auto !important;
```


Help me!
--------

Disclaimer: this is quick mixin I've been toying with on my last couple of projects, and while it has suited me well, it probably only covers 50% of use cases. If you've a way of making it more complete (and awesome!), I'd love you to contribute.

