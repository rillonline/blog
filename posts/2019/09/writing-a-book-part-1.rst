.. title: Writing a Book: Part 1
.. slug: writing-a-book-part-1
.. date: 2019-09-13

I have started to write a book which gathers together some of my
previous posts on Org and then fleshes out the material.

Setting Up a To-do
------------------

I first set up a to-do to track my progress. I am modifying the steps
as I go, but here is what it currently looks like:

.. code:: 

   * STARTED Write a series of articles on getting organized with org mode [5/10]

        1. [X] Gather all files into a new git repository
        2. [X] Create a landing page for the ebook
        3. [X] Write an outline for my getting organized articles
        4. [X] Integrate blog posts into this outline
        5. [X] Write a script to convert .org files to .md files and copy
           them to the book directory
        6. [ ] Write the book. Chapter by Chapter goes below.
        7. [ ] Publish the ebook
        8. [ ] Upload the ebook to archive.org
        9. [ ] Update the download link on the landing page.
        10. [ ] Write a blog post announcing the book.

I have checked off have of the items, but it is the easy stuff I've
checked off. So far I only have listed one items for writing the book
though I plan on adding check boxes underneath this item so I can
check off each chapter. The final check box is to review the entire
book and make any necessary corrections.

"STARTED" is a to-do state that I developed for my projects. More on
that when I discuss "TODO" in general.

Setting Things Up
-----------------

-  Setting up the git repository was very straight forward on `github <https://github.com/>`__.
   Then I looked over my blog and copied the posts that applied into
   that directory and updated the repository.
-  I then wrote a landing page for the book. The idea of a landing page
   is to have the potential reader focus on your book and the **Call to
   Action** which is for you, the reader, to click on the "buy" button.
   My page is quite simple and does not have a "Download" button yet
   since the book is not finished. You can look at it `here <https://rillonline.github.io/living-my-life-in-plain-text-page.html>`__.

Outlining
---------

I then set about putting together an outline to help me think about
what the book should cover. This is not set in stone. More chapters
may appear and the ones listed here may disappear. This is what it
currently looks like in Org markup.

.. code

   ** Table of Contents
   ** Introduction -- what this book hopes to accomplish
   ** Thinking About Doing
   ** A Few Quick Notes on Orgmode Markup
   ** Setting up your Initial Emacs Configuration for Org
   ** Setting up a Calendar
   ** Seeing Your Calendar as an Agenda
   ** Making a To-do List
   ** How Deep Should You Go?
   *** To-do Checkboxes
   *** To-do Keywords
   *** Priorities
   ** Revisiting the Agenda
   *** Helpful keys in the Agenda -- archiving, saving, changing status
   *** Seeing the Agenda on STartup
   *** Remember to Refresh
   ** Capturing Information
   *** Deciding what to Capture
   ** To Refile or Not to Refile
   ** Writing in Orgmode
   ** Exporting and Publishing in Orgmode
   ** Keeping Track of Expenses
   ** References

Promotion and Demotion
~~~~~~~~~~~~~~~~~~~~~~

In looking this over, the first thing I want to do is change the
headline level. I need to move everything up one level so that heading
3s become heading2s and heading2s become heading1s
What I want to do is called promotion. I highlighted the text, went to
the org menu and found "promote" under the "edit structure" menu item.
There is a shortcut key you can use if you do this often enough to
remember it "m-s-left". You can also demote items "m-s-right"..

Changing Headlines into Lists
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can change headlines into lists and lists into headlines. I
changed my outline headings into an unordered list of to-do items by
highlighting them and then applying the command "c-c -". That's "c-c
hyphen". The "-" (hyphen) gives you the clue. The asterisks "*" are
replaced wit a hyphen "-". You can go the other way by using "c-c \*" (asterisk).

Making an Epub
--------------

What Didn't Work for Me
~~~~~~~~~~~~~~~~~~~~~~~

Then I investigated how to make an epub. Pandoc can do this. One of
the examples I found showed how to put a bunch of markdown files in a
directory and then turn them into an ebook. Great, I thought.

I tried to use org-publish to do this but I could not get a batch
transformation of all org files. I've tried this in the past and the
markdown export function still hangs. I think I had 30 buffers open wantiiting
for something. I have no idea what

I found this script on the `pandoc site <https://pandoc.org/faqs.html>`__ and modified it for my purpose:

.. code

   #!/bin/bash
   # Convert all org files in a directory to markdown
   # This script is to convert and move markdown into the book folder

   for f in *.org;
   do pandoc "$f" -s -o "${f%.org}.md";
   done
   mv *.md book/

Then I discovered I would have to include every filename in the
directory in my pandoc command. That seemed more trouble than it was
worth as the moment so I will just write in one file and perhaps split
it out at the end so that I can update it more easily. We'll see.

What Did work for Me
~~~~~~~~~~~~~~~~~~~~

I had to add some YML stuff to the beginning of my file:

.. code

   ---
   title: Living My Life in Plain Text
   author: Rill Woolnough
   rights: Creative Commons Attribution Non-commercial ShareAlike
   ---

Here's the pandoc command I am using:

.. code

   pandoc -o book.epub book.org --toc --toc-depth=3

Reading the Epub
----------------

So how to read it? Enter emacspeak. It uses the eww browser to render
the book.

.. code

   m-x     emacspeak-epub-open  ret
   enter the path to the book ret

Because Firefox is my default browser, the book opens there. There is
single letter navigation to move around in the book as if you are in a
regular web page. alt-f4 closes the book.

Back to Work!
-------------

Now I'm going back to writing.
