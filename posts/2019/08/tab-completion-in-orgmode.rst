.. title: Tab Completion in Orgmode
.. slug: tab-completion-in-orgmode
.. date: 2019-08-20

I have been puzzled why tab
completion wasn't working in orgmode so I
.. dat: 2019-08-20

#+END\ :sub:`COMMENT`

decided to let the good old Internet help me out.

It turns out that my friend Flyspell uses tab completion for
completing words. I don't want to turn off Flyspell since you would
end up reading articles with many misspellings.

The suggestion I found was to use m-tab for completions However,
alt+tab only switched me to another window. Enter the escape key!

escape=tab does the trick. ``#+BEGIN_Q`` becomes ``#+BEGIN_QUOTE`` after
pressing escape-tab. Take that Apple. I can't do that on a Mac with a
touch bar. Fortunately, I am not using one for this Linux installation.
