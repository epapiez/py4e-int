Infinite loops
--------------

An endless source of amusement for programmers is the observation that
the directions on shampoo, "Lather, rinse, repeat," are an infinite loop
because there is no *iteration variable* telling you how
many times to execute the loop.

In the case of ``countdown``\ , we can prove that the loop
terminates because we know that the value of ``n`` is finite,
and we can see that the value of ``n`` gets smaller each time
through the loop, so eventually we have to get to 0. Other times a loop
is obviously infinite because it has no iteration variable at all.

Sometimes you don't know it's time to end a loop until you get half way
through the body. In that case you can write an infinite loop on purpose
and then use the ``break`` statement to jump out of the loop.

This loop is obviously an *infinite loop* because the
logical expression on the ``while`` statement is simply the
logical constant ``True``\ :

.. codelens:: codelens531
    :showoutput:

   n = 10
   while True:
       print(n, end=' ')
       n = n - 1
   print('Done!')


As you can see above, the Code Lens gives you a warning because it runs for over 1000 steps. If you make the mistake and run this code, you will learn quickly how to
stop a runaway Python process on your system or find where the power-off
button is on your computer. This program will run forever or until your
battery runs out because the logical expression at the top of the loop
is always true by virtue of the fact that the expression is the constant
value ``True``.

While this is a dysfunctional infinite loop, we can still use this
pattern to build useful loops as long as we carefully add code to the
body of the loop to explicitly exit the loop using ``break``
when we have reached the exit condition.

For example, suppose you want to take input from the user until they
type ``done``. You could write:

.. activecode:: 05section3_1
   :coach:
   :caption: An example of using "True" as a condition without resulting in an infinite loop.

   while True:
       line = raw_input('Word: ')
       if line == 'done':
            break
       print(line)
   print ('Done!')

The loop condition is ``True``\ , which is always true, so the
loop runs repeatedly until it hits the break statement.

Each time through, it prompts the user with an angle bracket. If the
user types ``done``\ , the ``break`` statement exits the
loop. Otherwise the program echoes whatever the user types and goes back
to the top of the loop. Here's a sample run:

.. code-block::

   > hello there
   hello there
   > finished
   finished
   > done
   Done!


This way of writing ``while`` loops is common because you can
check the condition anywhere in the loop (not just at the top) and you
can express the stop condition affirmatively ("stop when this happens")
rather than negatively ("keep going until that happens.").

.. mchoice:: 05question3_1
   :answer_a: 1
   :answer_b: 2
   :answer_c: 3
   :correct: b
   :feedback_a: Try again! All the statements that are indented 4 spaces to the right of the while are part of the body of the loop.
   :feedback_b: Correct! There are two statements that are indented 4 spaces to the right of the while statement, so there are two statements in the body of this loop.
   :feedback_c: Try again! There are three lines here total, but not all of them are in the body of the loop.

   How many lines are in the body of the while loop in shown above?

   .. code-block:: python

    while 1==1:
        print ("Looping")
        print ("Forever")

    Looping
    Forever
    Looping
    Forever
    Looping
    Forever
    Looping
    Forever

.. parsonsprob:: question5_3_1
   :numbered: left
   :practice: T
   :adaptive:

   Construct a block of code that prints the numbers 1 through 5.
   -----
   n = 0
   =====
   while (n < 5):
   =====
   while (n < 5) #distractor
   =====
   while (n <= 5): #distractor
   =====
    print(n + 1)
   =====
    n = n + 1
