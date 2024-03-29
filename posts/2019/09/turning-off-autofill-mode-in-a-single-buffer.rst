.. title: Turning Off Autofill-mode in a Single Buffer
.. slug: turning-off-autofill-mode-in-a-single-buffer
.. date: 2019-09-04

In my article on
`Using Checkboxes <https://rillonline.github.io/posts/2019/09/02/using-checkboxes/>`__ I discussed sorting lines in my ideas file. I went ahead
and added more ideas to the file. Because I sometimes forget details,
I decided to include many details in several entries.

Details are good, right? Well, not if they wrap to another line. This
messes up sorting since the sort doesn't know how to keep the
additional lines with their starting line. I knew that, but hoped
(unreasonably) that everything would stay together. Of course, it
didn't. So I had to look for a solution.

The problem is simple enough. Auto-fill-mode is turned on by default.
In general, auto-fill-mode is a good thing. When the line gets too
long, Emacs inserts a line break and a new line is started. Happily,
when typing in org-mode as I was, Org appropriately wraps the line with a
two space indentation. Org knows my additional words belong to this
list item. HTML will know it, too, because Org will tell it by
enclosing the whole thing in "<li></li>" tags. But sort-lines is
emphatic that a line is a line.

The solution, not surprisingly, is to turn off auto-fill-mode in this
buffer. But how? I started searching for the answer.

The readily available answer was this:

.. code:: example

   m-x auto-fill-mode

This toggles auto-fill-mode on and off. If it is on to begin with, all
I have to do is toggle it off when I open the file and life is good.

Except … well, except that I want to write ideas with long
explanations because I forget. And it is **very** likely I will forget
to do this.

Allthough it took some time, I finally found a way to do this so
auto-fill-mode would be turned off for the buffer and I don't have to
remember what to do.

I placed the following line at the top of my ideas file:

.. code:: example

   ;; -*- mode: org; mode: auto-fill -1; -*-

I refresh the current buffer via the Org menu and autofilling stopped.
**Note**: I did find I had to use "-1" rather than "0" to turn off
auto-fill.

Edited 2019-09-07. I originally had the mode as text when it should be org.
