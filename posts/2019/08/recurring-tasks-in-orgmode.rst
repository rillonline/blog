.. title: Recurring Tasks in Orgmode
.. slug: recurring-tasks-in-orgmode
.. date: 2019-08-28

Edited on 2019/09/01 to correct an error with tasks that needed to be
re-scheduled differently in the future.

Introduction
------------

I have been keeping a list of to-dos in a file called "organizer.org".
(I'm not sure if it actually keeps me organized, but I like the idea
of having a list of tasks, especially tasks I might forget about.) At
the top level I have three headlines:

#. Tasks. These are the one off sorts of tasks that it would be
   labor-intensive to categorize.
#. Website. This is where I put items related to maintaining my
   website (where you are most likely reading this article) and ideas
   for writing new articles.
#. Writing. Separate from writing for my website, I list longer pieces
   here both fiction and non-fiction.

My "init.el" file for Emacs has a line in it to display my weekly
agenda view.

.. code:: example

   (setq initial-buffer-choice 'org-agenda-list)

This agenda view shows my diary for the week as well as any tasks with
either a scheduled start date or end date, i.e., deadline.

Writing a Good To-do
--------------------

A basic rule of thumb is to write a to-do that you can actually get
done. It has to be specific enough so that you know when you've
started it and when you can check it off your list, that is, mark it
done. I had this to-do which is more an aspiration than a to-do.

.. code:: example

   ** TODO Publish at least one blog post weekly to keep website fresh

The intent is clear enough: one blog post to be completed every
week.

My mother kept a calendar on the kitchen wall. She was fussy about it.
She wanted big blank blocks in which to write. She wrote everything
down. She had codes for each of us. She often would say the item and
the person's initials as she wrote.

In my mother's calendar world, the blog post could be written in and
even X'ed out when done and then been re-written on the next line of
blocks for the month. She may have even just drawn a straight line
through every Tuesday.

I have several good to-dos already in my organizer file:

.. code:: example

   ** TODO Pay rent
      DEADLINE: <2019-09-01 Sun +1m>
   ** TODO Give Nick his heart worm pill
      DEADLINE: <2019-09-13 Fri +1m>

These tasks can be marked as done. Org will advance the date
by one month and they will again appear in my weekly agenda view. The
day of the week will change, but not the day of the month.

An Interim Solution
-------------------

I started marking my website refresh to-do as done when I wrote and
posted a new article. After marking it done and recording the name of
the article in the comments, I marked the to-do as "TODO" to start the
process all over again. This seems quite unappealing to me.

A Better Solution
-----------------

In reading through
`Repeated Tasks <https://orgmode.org/manual/Repeated-tasks.html>`__ I realized that my article writing to-do is not like
paying rent or giving Nick his pill. If I do not write a blog article
on a given week, I don't need to catch up. I can pick up at any time
and start posting on a regular basis. It is clear looking through my
archives and at other people's blogs this is what happens all the
time. I am writing these articles because I want to write them. I
don't need to write them. I enjoy posting and then marking my success
by calling this to-do done. In the days of paper and pen, people
enjoyed drawing a line through an item on a list. (Never using this
medium, I was always jealous of their satisfaction. People wrote
noisily and with a flourish.)

I now find out Org has a solution for my task.

My New To-do
------------

Here is what I came up with for my article writing to-do.

.. code:: example

   ** TODO Publish at least one blog post weekly to keep website fresh
      DEADLINE: <2019-08-27 Tue .+3d>

This suggests I have a 3 day deadline for writing a weekly article.
No, I haven't lost my mind. If I am writing regularly, I will write
more than one blog post a week and I want to honor that, but my
general goal is to be sure I write at least one post every week.

When I mark this task as done, three days will be added to the deadline. If the
deadline is in the past, another three days will be added until the deadline
is in the future. In this way, the three-day deadline may also move
throughout the week. For example, if I complete this task today,
Tuesday, it will have a deadline of Friday. If I don't complete
it until Monday, it will then have a deadline of the following
Thursday, almost two weeks after its original deadline.

If you want this task to always be due on a Tuesday,for example, use
"++"(plus plus) instead
of ".+" (dot plus.)
