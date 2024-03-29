.. title: Using Flyspell and Emacspeak
.. slug: using-flyspell-and-emacspeak
.. date: 2019-08-16

The Problem
-----------

I didn't have a great set up for spellchecking in Emacs. Ispell works,
but often there are too many choices and Emacspeak does not read them
out. So I investigated Flyspell and now I have a working solution.

The Hook
--------

I now have flyspell working in all text and text-derived buffers by
adding this hook:

.. code:: example

   (add-hook 'text-mode-hook 'flyspell-mode)

This can be disabled in specific circumstances if needed but this is
beyond the scope of this article.

Procedure to Correct Words in a Buffer
--------------------------------------

There are keybindings to autocorrect in ``flyspell``, but this is not
always advisable.

I needed to be able to scroll through the many options. ``Ispell`` gives
choices with numbers, but often there are too many to give you the
list. By putting the following command in my ``init.el`` file via the
customization menus, I am now able to use ``flyspell`` to cursor up and
down a list until I find the right choice. After that, I can just hit return.

If auditory icons is turned on and you are using the default theme,
you will hear something like a rattling sound when you misspell a word. To
correct the word immediately,

-  move point to the misspelled word.
-  Press c-c $. (control plus c then s plus 4)
-  Emacspeak will say menu. You can use your cursor keys to scroll up
   and down the list of suggestions.
-  Press return on your selection.

As well as misspelled word suggestions, you can save your word in a
personal dictionary, accept your spelling for this session or accept
all misspelled words in the buffer.

Spellchecking the Buffer
------------------------

c-, (control plus comma) can move point from misspelled word to
misspelled word in your buffer. Press c-c $ to correct each one. c-,
will announce when you reach the end of the buffer. Press c-, again to
move to the beginning of the buffer.

Automatic Correction
--------------------

There are other commands which can move point and automatically
correct your misspellings. Since this is automatic, the first choice
may not be the correct one. Once the word has been corrected, you will
need to reread your work to find it.

Tip
---

When moving from misspelled word to misspelled word in your buffer,
Emacspeak will not read out the new misspelled word. Press c-e w to
hear the word. Press c-e w again to have it spelled.
